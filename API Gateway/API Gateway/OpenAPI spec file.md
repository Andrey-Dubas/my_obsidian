# openapi2-functions.yaml
swagger: '2.0'
info:
  title: test
  description: Sample API on API Gateway with a Google Cloud Functions backend
  version: 1.0.0
schemes:
  - https
produces:
  - application/json
#prefix after the static gateway URL. It tells the Gateway which function to call
paths:                              
  /hello:
    post:
      summary: Greet a user
      operationId: hello
      #actual address of the cloud function where the request is supposed to be forwarded
      x-google-backend:             
        address: https://GCP_REGION-PROJECT_ID.cloudfunctions.net/hello
      responses:
        '200':
          description: A successful response
          schema:
            type: string