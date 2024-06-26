When you use an API key to authenticate to an API, the API key does not identify a [principal](https://cloud.google.com/docs/authentication#principal), nor does it provide any [authorization](https://cloud.google.com/docs/authentication#authorization) information. Therefore, the request does not use Identity and Access Management (IAM) to check whether the caller has permission to perform the requested operation.

The API key associates the request with a Google Cloud project for billing and quota purposes. Because API keys do not identify the caller, they are often used for accessing public data or resources.

Once we have generated API keys we can use then either as query params of header param.