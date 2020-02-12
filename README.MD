# Webhooks with github

## Create github access token

Export token
```
export TOKEN="asdf-asdf-asdf-asdf"
``

## Create postbin

Go to https://postb.in/, create a bin. Export bin id:
```
export BIN_ID="1581493698910-3715858794748"
```

## Create webhook on repository

Edit webhook_create.json set url to postbin url.

Create webhook on repository
```
curl -u cretzel:$TOKEN -X POST -d @webhook_create.json https://api.github.com/repos/cretzel/github-webhooks-example/hooks
```

## Trigger push event
Commit to repository

## Get webhook calls from postbin

```
curl https://postb.in/api/bin/$BIN_ID/req/shift | jq
```