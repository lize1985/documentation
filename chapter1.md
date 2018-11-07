# How to Use Gandalf



Figure 1 below demonstrated 3 scenarios that you will interact with Gandalf

* You want to re-actively receive Email/ICM alerts

* You want to proactively monitoring Rollout KPI in Region/Cluster Level

* You want to proactively monitoring Rollout in Cross Cluster Level

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfD-IChe0_QPJ0Py4x%2F-LQflREqUiHqSXb-Kb_x%2FGandalfUseSenario.PNG?alt=media&token=25da9432-2e95-4531-bb47-8a9015e0915a)

**                                                                                              Figure 1 User Scenario**

# You Want to re-actively receive Email/ICM alerts {#you-want-to-re-actively-receive-email-icm-alerts}

After you onboarding with Gandalf, once Gandalf detects a spike of faults that correlated with the rollout, you will received an ICM/Emails that similar to the figures below. You can click on the Hyper links to navigate to the fault details

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQfw7D_XI4E4Py5j5Ez%2FEmailAlert.PNG?alt=media&token=a7b53572-c85c-46b0-a9bd-ae2a14ec9d96)

Figure 2. Example of Email Alert

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQfxLLTcxHET8_ndObR%2FICMAlert.PNG?alt=media&token=2ce11208-4fad-4168-bb5a-b4598d1ab905)

Figure 3. Example of ICM Alerts

# You Want to Proactively Monitoring Rollout KPI In Region/Cluster Level {#you-want-to-proactively-monitoring-rollout-kpi-in-region-cluster-level}

## Cluster/Region Level KPI monitoring {#cluster-region-level-kpi-monitoring}

* You need go to link[https://gandalfprod.corp.microsoft.com/ad/capacity/rolloutprogress.html](http://gandalfprod.corp.microsoft.com/ad/capacity/rolloutprogress.html)​

* Select appropriate Component, Version, Cluster type information

* The KPI dashboard currently support monitoring on the following KPI

  * Rollout coverage

  * Availability related metrics

  * Capacity related metrics

  * Cluster level Failures

## Cluster fault details {#cluster-fault-details}

By clicking on the hyper links of the Cluster Name in**Figure 4**, you can see all the faults that correlated with the deployment and happened on the clusters as shown in**Figure 5**below

* You can double click on the row in the table to check the trend of the faults

* You can double click on the row in the bottom table to check the fault details and RCA as shown in**Figure 6**

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQfz6J4pt7pJj0BSmFH%2FClusterLevelRollout.PNG?alt=media&token=ebcc2e25-e78e-4e72-8c41-0bf58efbb2b3)

**                                                                                         FIgure 4. Rollout KPI Dashboard**

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQg-dG0eCR2d-H6RwLY%2FClusterFaultDetails.PNG?alt=media&token=c881cf4f-776b-4813-af46-1b34bf5bf631)

**                                                                                         Figure 5. Cluster level faults**

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQg0__aQdjfu6PNg3q_%2FFaultDetails.PNG?alt=media&token=68d0e5f2-bc16-47ee-b0f8-bfd0511bc3e3)

Figure 6. Check Fault details and RCAs

# You want to proactively monitor rollout in cross cluster level {#you-want-to-proactively-monitor-rollout-in-cross-cluster-level}

## Decision Dashboard {#decision-dashboard}

* Through[http://gandalfprod.corp.microsoft.com/ad/safedeployment/dashboard.html](http://gandalfprod.corp.microsoft.com/ad/safedeployment/dashboard.html), you will go to the decision dashboard that present the overall rollout decision as shown in Figure 7. We can select different component versions for different rollout monitoring

  * You can**search**and**click**on the decision symbols to navigate to the details page

    * **Search:**in the search bar, the users can search key words in the table below. The results will be dynamically filtered

    * **Type of Decisions:**

      * Investigate![](https://microsoft.sharepoint.com/teams/Gandalf46/SiteAssets/Gandalf%20Safe%20Deployment/Home/warning.PNG "warning.PNG"): The faults are not significant. It worth the developers to investigate in it

      * Good![](https://microsoft.sharepoint.com/teams/Gandalf46/SiteAssets/Gandalf%20Safe%20Deployment/Home/Good.PNG "Good.PNG"): The build is ok

      * No-Go![](https://microsoft.sharepoint.com/teams/Gandalf46/SiteAssets/Gandalf%20Safe%20Deployment/Home/Capture.PNG "Capture.PNG"): The build fails. The rollout should be stopped

      * New fault![](https://microsoft.sharepoint.com/teams/Gandalf46/SiteAssets/Gandalf%20Safe%20Deployment/Home/NewFault.PNG "NewFault.PNG"): The fault does not seen in the last 30 days. The new fault will not cause a no-go, but just FYI

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQgXH6435YwETNRDj3H%2FDecisionDashboard.PNG?alt=media&token=8a691726-d03f-45eb-b0ac-886a61338934)

Figure 7. Decision Dashboard

## Rollout Dashboard \(Batch\) {#rollout-dashboard-batch}

* After you click on a decision, you will be directed to the rollout page for cross cluster monitoring. By default, it is in the batch mode

  * **Rollout Selectors:**

    * Currently the rollout selectors include

      * Component

      * Build Version

      * Swimlane

      * VE

  * **Rollout Progress:**

    * Rollout progress records the number of cluster and nodes that have been rolled out in time series

  * **Current Rollout Decision:**

    * Issue go/no-go issue based on the binary decision algorithm

  * **Worst Rollout Decision:**

    * If the current the decision is green, here will show the worst case decision

  * **Top Issues**

    * This table lists all the issues related to the rollout

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQg_MkJbAisD_uPVxpB%2FBatchRollout.PNG?alt=media&token=f0d10e83-6ff0-46de-8bed-998bd47c4aa1)

Rollout Page for the batch mode

## Rollout Page \(NRT\) \(Streaming\) {#rollout-page-nrt-streaming}

* From the panel tab, you can navigate yourself to the rollout page \(NRT\)

  * **Rollout Selectors**

  * **Rollout Progress**

  * **Long Term Fault Trends**

  * **Top Issues**

  * **Fault Segmentation**

  * **Fault Steaming Dashboard**

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQgcdv7Syb8xJvl6P7l%2FNRTRollout.PNG?alt=media&token=1ea74171-f653-4d2a-8199-59e9dea90428)

NRT rollout page

By double clicking on the rows in the "Faults over time in swimlane" table, you can see the fault details

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQgdTwPip3nU4lzlg5h%2FNRT%20Fault%20Details.PNG?alt=media&token=0ee707b5-fda9-42a4-bc51-ed51a3727d58)

Fault details for NRT

## Fault signature page {#fault-signature-page}

* By Clicking on the fault signature, you can navigate to the fault signature page

  * **Issue Selectors:**

    * Currently, the issue page support the following filters including

      * Component

      * Build Version

      * Swimlane

      * VE

      * Source

      * Signature

  * **Fault Trends in Virtual Enviroment**

    * The graph shows the fault trends in different VE over time

  * **Fault Trend in Top3 Prod Regions**

    * The graph shows the top 3 regions in prod has the highest faults

  * **Drilldown For Build Version**

    * The table here lists all the clusters and nodes has faults with the selected build version and fault signatures

  * **Attributed Components For Signature ​**

    * Here the are components that is affected by the signature

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQgeBZw47axaYNij1yU%2Fimage.png?alt=media&token=c5b8ee42-ebc6-4a97-a130-6d1d85a53546)

## Cluster Utilization During Rollout {#cluster-utilization-during-rollout}

During the cluster rollout, we can also monitoring the cluster utilization and peek some insights for the capacity related information in the cluster

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfqB1e3a8Bg5l2dwLb%2F-LQgeIfPKJB1di2H50lV%2Fimage.png?alt=media&token=8b364259-c7fd-4624-852a-4930bb2e387d)

