# openapi2-functions.yaml  
  swagger: '2.0'  
  info:  
    title: API_ID optional-string  
    description: Sample API on API Gateway with a Google Cloud Functions backend  
    version: 1.0.0  
  schemes:  
    - https  
  produces:  
    - application/json  
  paths:  
    /hello:  
      get:  
        summary: Greet a user  
        operationId: hello  
        x-google-backend:  
          address: CLOUD-FUNCTION-TRIGGER-URL  
        security:  
        - api_key: []  
        responses:  
          '200':  
            description: A successful response  
            schema:  
              type: string  
  securityDefinitions:  
    # This section configures basic authentication with an API key.  
    api_key:  
      type: "apiKey"  
      name: "key"  
      in: "query"