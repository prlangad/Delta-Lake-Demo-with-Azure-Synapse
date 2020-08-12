# Delta-Lake-Demo-with-Azure-Synapse

This repository provides demo example of creating delta lake tables with Synapse Pipelines and then reading, updating data using Synapse notebook. The files are prefixed with numbers in the order of execution.
The demo illustrates the HRData information which gets updated time-to-time when employees update personal information, or they change departments. HR admin may need to audit data for analysis purpose. We will see in this demo how Synapse offers working on HR data with Delta Lake. This can be demonstrated in two ways:

## Option A: End-to-end delta lake exploration with notebook experience (This includes creating delta table and exploring it with Synapse Spark)
### Artifacts
For option A:
1.	[00 HRData.csv](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Sample%20Data/00%20HRData.csv)
2.	[06 Delta Lake Demo.ipynb](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/06%20Delta%20Lake%20Demo.ipynb)
### Execution Sequence:
1.	Save [00 HRData.csv](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Sample%20Data/00%20HRData.csv) in your storage account
2.	Import [06 Delta Lake Demo.ipynb](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/06%20Delta%20Lake%20Demo.ipynb) notebook in your synapse workspace.
3.	Replace placeholders in [06 Delta Lake Demo.ipynb](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/06%20Delta%20Lake%20Demo.ipynb) with appropriate details for storage_account_name, container_name, folder_names
4.	Publish notebook and run for delta table creation and exploration.

## Option B: Create delta lake with Synapse pipeline and then perform exploration using Synapse Spark
### Artifacts
For option B:
1.	[00 HRData.csv](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Sample%20Data/00%20HRData.csv)
2.	[01 hrdatacsv_adls.json](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/hrdatacsv_adls.json)
3.	[02 CodeFreeLoadDeltaTable.json](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/CodeFreeLoadDeltaTable.json)
4.	[03 DeltaLakePipeline.json](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/0601%20DeltaLakePipeline.json)
5.	[04 Delta Lake Exploration.ipynb](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/0602%20Delta%20Lake%20Exploration.ipynb)
### Execution Sequence
1.	Save [00 HRData.csv](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Sample%20Data/00%20HRData.csv) to your storage account. 
2.	Let’s start creating delta table from csv file using Synapse pipeline. Create dataset, data flow and Synapse pipeline as named below and then click on script and copy JSON code from link. Once validation is successful, publish these artifacts.
 **Note**: In this demo, linked service name is used as <>, replace this name with appropriate linked service name you have created for your storage account. These instructions also apply to storage account name, container name, folder name. <DeltaLake location edit>
  
  Artifact Type	|	Pipeline Name	|	Link to JSON file
  ---	|	---	|	---
  Dataset	|	hrdatacsv_adls	|	[hrdatacsv_adls.json](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/hrdatacsv_adls.json)	
  DataFlowName	|	CodeFreeLoadDeltaTable	|	[CodeFreeLoadDeltaTable.json](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/CodeFreeLoadDeltaTable.json)
  Pipeline	|	LoadDeltaTable	|	[DeltaLakePipeline.json](https://github.com/prlangad/Delta-Lake-Demo-with-Azure-Synapse/blob/master/Code%20Artifacts/0601%20DeltaLakePipeline.json)

3.	Run the pipeline with Manual Trigger and verify the delta table is created at location provided by you.
4.	Import [04 Delta Lake Exploration.ipynb]() notebook in your synapse workspace.
5.	Replace placeholders in [04 Delta Lake Exploration.ipynb]() with appropriate details for storage_account_name, container_name, folder_name
6.	Publish notebook and run notebook for delta table exploration.

## Resources
[What is Delta Lake?](https://docs.microsoft.com/en-us/azure/synapse-analytics/spark/apache-spark-what-is-delta-lake)

[Delta Lake Documentation Page](https://docs.delta.io/latest/delta-intro.html)
