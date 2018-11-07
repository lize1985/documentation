# Gandalf Architecture

The Figure below shows the data architecture of the gandalf safe deployment. ​ Gandalf is using a lambda architecture to provide both the Near Real Time \(NRT\) ETL and Batch ETL.

## Gandalf Near Real Time ETL \(Speed Layer​\) {#gandalf-near-real-time-etl-speed-layer}

In the Gandalf NRT ETL pipeline, the data source of the Gandalf is Kusto. In this pipeline, we focus on faults 1 hour before and after the deployment. The delay of the kusto stream is in several minutes. The Gandalf NRT pipeline focus on the spike detection

## Gandalf Batch ETL \(Batch Layer\) {#gandalf-batch-etl-batch-layer}

In the Gandalf Batch ETL pipeline, the data source of the Gandalf is Cosmos. In this pipeline, we focus on faults 72 hours before and after the deployment. The delay of the cosmos stream is in several hours. As the Gandalf batch pipeline consumes more data with large computing powers from Cosmos, the pipeline focus on more on the latent issues that is not easily spotted by the spike detection.

## Gandalf Serving Layer {#gandalf-serving-layer}

​In the Gandalf serving layer, the data from NRT pipeline and Batch pipeline are served by the same data orchestrator, which provide the services such as streaming monitoring, batch monitoring, diagnosis, auto stop, restful API and email notification

![](/assets/Architecture.png)

