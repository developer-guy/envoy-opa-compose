# OPA Envoy proxy using docker-compose

Using Envoy's external authorization filter with OPA as the authorization service to enforce security policies for all API requests received by Envoy.

Based off [this OPA tutorial](https://www.openpolicyagent.org/docs/latest/envoy-authorization/) but using docker-compose instead of Kubernetes.

This is meant for dockerized services (in a non-k8s environment) to easily leverage OPA for authorization.

## Usage

Run `docker-compose up` to start services.

A toy `policy.rego` file is used to only permit GET request. `curl -X GET http://localhost:8080/anything` should work but `curl -X POST http://localhost:8080/anything` should fail.
