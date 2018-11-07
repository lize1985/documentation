# Proactively monitor rollout in cross cluster level {#you-want-to-proactively-monitor-rollout-in-cross-cluster-level}

## Decision Dashboard {#decision-dashboard}

* Through [http://gandalfprod.corp.microsoft.com/ad/safedeployment/dashboard.html](http://gandalfprod.corp.microsoft.com/ad/safedeployment/dashboard.html), you will go to the decision dashboard that present the overall rollout decision as shown in Figure 7. We can select different component versions for different rollout monitoring

  * You can**search**and**click**on the decision symbols to navigate to the details page

    * **Search:**in the search bar, the users can search key words in the table below. The results will be dynamically filtered

    * **Type of Decisions:**

      * Investigate![](/assets/warning.PNG "warning.PNG"): The faults are not significant. It worth the developers to investigate in it

      * Good![](/assets/Good.PNG "Good.PNG"): The build is ok

      * No-Go![](/assets/Nogo.PNG "Capture.PNG"): The build fails. The rollout should be stopped

      * New fault![](/assets/NewFault.PNG "NewFault.PNG"): The fault does not seen in the last 30 days. The new fault will not cause a no-go, but just FYI

![](/assets/DecisionDashboard.PNG)

```
                                                                                     **Figure 7. Decision Dashboard**
```

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

![](/assets/BatchRollout.PNG)

```
                                                                          **Figure 8. Rollout Page for the batch mode**
```

## Rollout Page \(NRT\) \(Streaming\) {#rollout-page-nrt-streaming}

* From the panel tab, you can navigate yourself to the rollout page \(NRT\)

  * **Rollout Selectors**

  * **Rollout Progress**

  * **Long Term Fault Trends**

  * **Top Issues**

  * **Fault Segmentation**

  * **Fault Steaming Dashboard**

![](/assets/NRTRollout.PNG)

```
                                                                                          **Figure 9 NRT rollout page**
```

By double clicking on the rows in the "Faults over time in swimlane" table, you can see the fault details

![](/assets/FaultDetails.PNG)

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

![](/assets/signatures.png)

```
                                                                                               **Figure 10  Signature**
```

## Cluster Utilization During Rollout {#cluster-utilization-during-rollout}

During the cluster rollout, we can also monitoring the cluster utilization and peek some insights for the capacity related information in the cluster

![](/assets/cluster.png)

