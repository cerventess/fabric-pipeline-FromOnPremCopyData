# fabric-pipeline-FromOnPremCopyData
💡Smart & Reusable Microsoft Fabric Pipeline to copy data from on-prem SQL Server to a Lakehouse – the efficient way!

🦺 In this setup, I built a dynamic pipeline that retrieves all table names from a SQL Server database and automatically loads them into Microsoft Fabric Lakehouse.

After Install and configure a Data Gateway (Standard or Personal mode, based on your use case) & Create a connection artifact in Fabric using that gateway to access your SQL Server; 
here are the steps to follow:

1- Start the pipeline with a Lookup activity to dynamically retrieve all table names using a SQL query :
(select schema_name(t.schema_id) as schema_name, t.name as table_name
from sys.tables t
order by table_name).

2- Use a ForEach activity to loop through each table name (use dynamic content ) returned from the Lookup.

3- Inside the ForEach loop, use the Copy Data activity:
 ->Source: SQL Server (use dynamic content for schema + table names)
 -> Sink: Fabric Lakehouse (dynamic table name for storage)

🔗 The result? A reusable and automated pipeline that keeps your Lakehouse synced with your on-prem SQL Server — with zero hardcoded values.

I’ve added screenshots of each step to help you replicate it in your own Fabric environment.

hashtag#MicrosoftFabric hashtag#DataEngineering hashtag#Lakehouse hashtag#SQLServer hashtag#OnPremToCloud hashtag#FabricPipeline hashtag#PowerBI hashtag#FabricTips hashtag#MVPSeries
