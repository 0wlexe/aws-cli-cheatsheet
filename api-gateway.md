## API Gateway
List API Gateway IDs and Names
```shell
aws apigateway get-rest-apis | jq -r ‘.items[ ] | .id+” “+.name’
```

List API Gateway keys
```shell
aws apigateway get-api-keys | jq -r ‘.items[ ] | .id+” “+.name’
```

List API Gateway domain names
```shell
aws apigateway get-domain-names | jq -r ‘.items[ ] | .domainName+” “+.regionalDomainName’
```

Find Lambda for API Gateway resource
```shell
aws apigateway get-integration --rest-api-id (id) --resource-id (resource id) --http-method GET | jq -r ‘.uri’
```
