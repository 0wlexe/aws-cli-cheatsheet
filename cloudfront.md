## CloudFront
List CloudFront distributions and origins
```shell
aws cloudfront list-distributions | jq -r ‘.DistributionList.Items[ ] | .DomainName+” “+.Origins.Items[0].DomainName
```

Create a new invalidation
```shell
aws cloudfront create-invalidation [distribution-id]
```
