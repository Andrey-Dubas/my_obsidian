The API gateway is made of 2 components:
- [[API config]]
- [[Gateway]] AN Envoy-based, high-performance, scalable proxy that hosts the deployed API config. When we deploy an API to a gateway it creates the external facing URL that our API clients use to access the API. Gateways are deployed to a specific GCP region.