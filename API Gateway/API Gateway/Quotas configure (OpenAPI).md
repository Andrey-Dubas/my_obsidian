#x-google-management  #x-google-quota
This page describes how to configure quotas for your API. At a high level, the steps are:

1. Add the information about the quota to your OpenAPI configuration file.
2. Deploy your OpenAPI configuration file.
3. Deploy the Extensible Service Proxy (ESP).

The following procedure describes adding the required extensions to your OpenAPI document to set up quotas. For simplicity, this page refers to the OpenAPI document as the `openapi.yaml` file and provides the OpenAPI extensions only in YAML format.

## Adding a quota to your OpenAPI document

You add the following three sections to the `openapi.yaml` file:

- `x-google-management.metrics`: A named metric that counts requests to your API. You provide a name that describes the counter. The name can be a category, such as `read-requests` or `write-requests`. Alternatively, if you are defining a quota for a specific method, you might want to include the method name, for example, `echo-api/echo_requests`
x-google-management:
  metrics:
    - name: "YOUR_METRIC_NAME"
      displayName: "YOUR_METRIC-DISPLAY_NAME
      valueType: INT64
      metricKind: DELTA

- `x-google-management.quota.limits`: Represents a single enforceable limit on a named metric. This is where you configure the allowed number of requests for a metric that you have defined. Currently, only per-minute, per-project limits are supported.

quota:
  limits:
    - name: "YOUR_LIMIT_NAME
      metric: "YOUR_METRIC_NAME
      unit: "1/min/{project}"
      values:
        STANDARD: VALUE_FOR_THE_LIMIT

- `x-google-quota.metricCosts`: The `metricCosts` maps methods to metrics (many-to-many). A request to a method allocates a counter for each of the mapped metrics. When you associate a method with a metric, you always specify a cost for the request. You can configure the cost of each method independently. This allows different methods to consume at different rates from the same named metric. If you don't have a complex quota requirement, you can configure the cost of every metric to 1.

x-google-quota:
  metricCosts:
    YOUR_METRIC_NAME

: YOUR_METRIC_COST

- Replace `YOUR_METRIC_NAME` with a previously defined `metric.name`.
- Replace `YOUR_METRIC_COST` with an integer. For each request, the request counter for the metric is incremented by the number you specify for the cost.
- 