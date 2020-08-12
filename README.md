# Delta-Lake-Demo-with-Azure-Synapse

This repository provides demo example of creating delta lake tables with Synapse Pipelines and then reading, updating data using Synapse notebook. The files are prefixed with numbers in the order of execution.
The demo illustrates the HRData information which gets updated time-to-time when employees update personal information, or they change departments. HR admin may need to audit data for analysis purpose. We will see in this demo how Synapse offers working on HR data with Delta Lake. This can be demonstrated in two ways:

##Option A: End-to-end delta lake exploration with notebook experience (This includes creating delta table and exploring it with Synapse Spark)
### Artifacts
For option A:
1.	[00 HRData.csv]()
2.	[06 Delta Lake Demo.ipynb]()
### Execution Sequence:
1.	Save [00 HRData.csv]() in your storage account
2.	Import [06 Delta Lake Demo.ipynb]() notebook in your synapse workspace.
3.	Replace placeholders in [06 Delta Lake Demo.ipynb]() with appropriate details for storage_account_name, container_name, folder_names
4.	Publish notebook and run for delta table creation and exploration.
