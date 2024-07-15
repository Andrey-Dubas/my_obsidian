
The pattern represents a remote service as if it is local one. F.e. we have a redis instances (mater for write and a few read replicas). The app sends requests to localhost:6379, ambassador gets it and redirects to redis read or write instance (depending on a command)
