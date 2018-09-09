# Azure Event Hubs

## Get Started

reference: https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-quickstart-cli

### Steps to do a quick hello world using azure event hubs and storage

Create a test resource group
```
az group create --name ming-test --location australiaest
````

Create the event hub namepsace
```
az eventhubs namespace create --name ming-eventhubs-test --resource-group ming-test -l australiaest
```

Create a event hub
```
az eventhubs eventhub create --name eventhub-test --resource-group ming-test --namespace-name ming-eventhubs-test --message-retention 1 --partition-count 1
```

Create a storage account
```
az storage account create --name mingstoragetest --resource-group ming-test --location australiaeast --sku Standard_RAGRS --encryption blob
```

List account keys and connection strings
```
az storage account keys list --resource-group ming-test --account-name mingstoragetest
az eventhubs namespace authorization-rule keys list --resource-group ming-test --namespace-name ming-eventhubs-test --name RootManageSharedAccessKey
```

Then follow the tutorial in the link to simulate the simple send and receive processor in JAVA

### Clean up
```
az group delete --resource-group ming-test
```