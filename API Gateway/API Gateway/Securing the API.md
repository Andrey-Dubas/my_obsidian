Most of our APIs were publicly available. We could, of course, make them private and use Google's JWT tokens to authenticate but The JWT tokens are short-lived and we didn't want to go thru the process of generating a new one every few hours.
Enter API keys, which are manually generated and a single key can be used on gateway to verify against tll the API's linked in the gateway. There are other ways to verify (JWT, Firebase, Auth0, Okta, Google Id tokens) but this is what we are going with.