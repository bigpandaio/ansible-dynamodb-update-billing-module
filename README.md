# DynamoDB Update Billing Mode

The built in dynamodb module in Ansible uses an old version of [boto](https://pypi.org/project/boto/), which isn't capable of specifying the wanted billing mode when creating/updating a DynamoDB table.

The newer [boto3](https://pypi.org/project/boto3/) library has those capabilities, but is a bit cumbersome to update in the main ansible repo.

## To overcome this

You can use this module!!1

```yaml
# Update dynamo db table to pay per request billing mode
- dynamodb_update_billing_mode:
    name: my-table
    region: us-east-1
    billing_mode: 'PAY_PER_REQUEST'

# Update dynamo db table to provisioned billing mode
- dynamodb_update_billing_mode:
    name: my-table
    region: us-east-1
    billing_mode: 'PAY_PER_REQUEST'
```

### License

[apache-2.0](./LICENSE])
