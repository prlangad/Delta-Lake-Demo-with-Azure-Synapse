# Delta-Lake-Demo-with-Azure-Synapse
This repository provides demo example of creating delta lake tables with Synapse Pipelines and then reading, updating data using Synapse notebook. The files are prefixed with numbers in the order of execution.

## Artifacts

## Execution Sequence
1.	Let’s start creating delta table from csv file using Synapse pipeline. Create Synapse pipeline and data flow as named below and then click on script and copy JSON code from link.
 **Note**: In this demo, linked service name is used as <>, replace this name with appropriate linked service name you have created or set up. These instructions also applies to storage account name, container name, folder name.
 
Artifact Type | Pipeline Name 	|Link to JSON file
---|  ---	  |---
Pipeline  | LoadDeltaTable	|[LoadDeltaTable.json]()
DataFlowName	|CodeFreeLoadDeltaTable |[CodeFreeLoadDeltaTable.json]()



## Resources
