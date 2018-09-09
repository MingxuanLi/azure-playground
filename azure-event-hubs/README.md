# Azure Event Hubs

## Get Started

reference: https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-quickstart-cli

```
az group create --name ming-test --location australiaest
az eventhubs namespace create --name ming-eventhubs-test --resource-group ming-test -l australiaest
az eventhubs eventhub create --name eventhub-test --resource-group ming-test --namespace-name ming-eventhubs-test --message-retention 1 --partition-count 1
````