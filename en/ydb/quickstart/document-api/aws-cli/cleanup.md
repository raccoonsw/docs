---
sourcePath: en/ydb/overlay/quickstart/document-api/aws-cli/cleanup.md
---
# Deleting created resources

If you don't need the `series` table any more, delete it:

{% list tabs %}

* AWS CLI

    Run the command by replacing `https://your-database-endpoint` with the endpoint of your DB:

    {% note warning %}

    To work with the AWS CLI from Windows, we recommend using the [WSL](https://docs.microsoft.com/ru-ru/windows/wsl/).

    {% endnote %}

    ```bash
    endpoint="https://your-database-endpoint"
    aws dynamodb delete-table \
        --table-name series \
        --endpoint $endpoint
    ```

   Output:

   ```text
   {
      "TableDescription": {
         "AttributeDefinitions": [
               {
                  "AttributeName": "series_id",
                  "AttributeType": "N"
               },
               {
                  "AttributeName": "title",
                  "AttributeType": "S"
               }
         ],
         "TableName": "series",
         "KeySchema": [
               {
                  "AttributeName": "series_id",
                  "KeyType": "HASH"
               },
               {
                  "AttributeName": "title",
                  "KeyType": "RANGE"
               }
         ],
         "TableStatus": "DELETING",
         "CreationDateTime": "2020-12-27T13:21:10+00:00",
         "TableSizeBytes": 0,
         "ItemCount": 0
      }
   }
   ```

{% endlist %}
