# triggers

### npm V2 templates
```
* C# Templates:
  * QueueTrigger
  * HttpTrigger
  * BlobTrigger
  * TimerTrigger
  * DurableFunctionsOrchestration
  * SendGrid
  * EventHubTrigger
  * ServiceBusQueueTrigger
  * ServiceBusTopicTrigger
  * EventGridTrigger
  * IotHubTrigger

* JavaScript Templates:
  * Blob trigger
  * Cosmos DB trigger
  * Event Grid trigger
  * HTTP trigger
  * Queue trigger
  * SendGrid
  * Service Bus Queue trigger
  * Service Bus Topic trigger
  * Timer trigger

* Python Templates:
  * Blob trigger
  * Cosmos DB trigger
  * HTTP trigger
  * Queue trigger
  * Timer trigger
```

### some command line notes

* why not just globally install the cli?
* npm package (https://www.npmjs.com/package/azure-functions)

```
# install npm azure because I couldnt get preview 2.0 runtime to work
npm i -g azure-functions-core-tools@core

# install azure functions with npm
npm install azure-functions

# create a project from template

mkdir triggers
cd triggers
func init --worker-runtime dotnet
func new -l C# -t HTTPTrigger -n basic_trigger

# test funcs locally
func host start --build

# trigger
curl http://localhost:7071/api/triggerdemo?name=world

# add a timer
func new -t TimerTrigger -n basic_trigger
(you need to edit the local.settings.json file with an actual storage connection string for this to work)
(you also need to change .csproj file to copy the local.settings.json file to output directory)

# add a blob trigger
func new -t BlobTrigger -n basic_blob_trigger
(add another connection to local.settings.json, for example, name it AzureWebJobsBlob)
(in the cs file, name the connection Blob)
(in the cs file, you need to set the name of the container to trigger from)
```

# featureswitchdemo

```
