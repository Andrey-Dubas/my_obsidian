==To identify a service== that sends requests to your API, ==you use a [service account](https://cloud.google.com/docs/authentication#service_accounts)==. The calling service ==uses the service account's private key== to sign ([[Digital signature]]) a secure [JSON Web Token (JWT)](https://jwt.io/) and sends the signed JWT in the request to your API.

- Create a service account and key for the calling service to use.
- Add support for authentication in the OpenAPI document for your [[Cloud Endpoints]] service.
-  Add code to the calling service that:
    - Creates a JWT and signs it with the service account's private key.
    - Sends the signed JWT in a request to the API.


This section shows how to use the Google Cloud console and the `gcloud` command-line tool to create the service account and private key file and ==to assign the service account the [**Service Account Token Creator**](https://cloud.google.com/iam/docs/understanding-roles#service-accounts-roles) role==. For information on using an API to do this task, see [Creating and managing service accounts](https://cloud.google.com/iam/docs/creating-managing-service-accounts).

==**Note:** Service account keys are a security risk if not managed correctly. You should [choose a more secure alternative to service account keys](https://cloud.google.com/docs/authentication#auth-decision-tree) whenever possible.==

One of the steps:
==Add the **Service Account Token Creator** role. Replace `SA_EMAIL_ADDRESS` with the service account's email address.==

gcloud projects add-iam-policy-binding PROJECT_ID
 \  --member serviceAccount:SA_EMAIL_ADDRESS
 \  --role roles/iam.serviceAccountTokenCreator
