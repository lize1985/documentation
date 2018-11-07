# Gandalf Spatial and Temporal Algorithm

# Overview {#overview}

In the cloud infrastructure, it is often the case that many core components are updated simultaneously and independently. As the cloud infrastructure also has a variety of configurations \(both in hardware and software\), the initial impact of a bad rollout may typically be hidden as the entire cloud seems healthy, yet several specific configurations may be very severely impacted. In a traditional system, there is already a wide impact radius once such issues are detected, often after days of rollout. The Safe Deployment algorithm is an algorithm aims to

* monitor and auto-stop bad rollouts

* aid diagnosis by pinpointing the most severely impacted parts of the cloud infrastructure.

This is achieved through two processes:

1. a global correlation between failure events against rollout events, identifying which rollouts are suspicious

2. A decision process, which assess the quality of a rollout by looing at the overall customer impact and generate go/no-go decision for a rollout.

   **Figure 1 **shows the basic workflow of the gandalf safe deployment model​. The gandalf model consists of 5 steps.

3. Ensemble Voting

4. Temporal Correlation

5. Spatial Correlation

6. Exponential decaying

7. Binary decision/supporting evidence

   ![](/assets/GandalfModel.png)  

# Ensemble voting {#ensemble-voting}

In the ensemble voting step, we are trying to identify candidates attributing components for each fault signature. Each fault votes components deployed in the same nodes in a time window and Aggregate the votes and get candidate attributing components for each fault

![](/assets/temporal.png)

Ensemble voting

# Temporal Correlation {#temporal-correlation}

Filter out the ambient noise in last 72 hours and calculate a temporal correlation score

![](/assets/CorrelationFunction.PNG "CorrelationFunction.PNG")

w is the weight of the time segment; P is number of fault nodes after deployment and b is the number of fault nodes before deployment Then we identify the suspicious components by associatingthe faults to the component with the greatest temporal correlation![](/assets/ranking.PNG "ranking.PNG")​

![](/assets/spatial.png)

Temporal Correlation

# Spatial Correlation {#spatial-correlation}

![](/assets/spatial2.png)

Spatial Correlation

Given a rollout component i at time t

N\(i,j\) : Num of**rollout nodes**with a fault signature j for a component i

F\(j\) : Num of**all**nodes with fault signature j during the deployment period

Spatial correlation for a fault signature j is

P\(t│i,j\)=N\(i,j\)/F\(j\)

Filter out faults if P\(t\|i,j\) that is less than a threshold

# Exponential Time Decaying {#exponential-time-decaying}

![](/assets/expoentialdecay.png)

Exponential Time Decaying

In this step, gandalf will gradually forget the blaming on the old components exponentially and focus on new component Decay ratio are scaled to \[a, b\]

![](/assets/delaying.PNG "delaying.PNG")​

# Binary Decision {#binary-decision}

In the binary decision step, we evaluate the impact of the rollout based on the features such as \# of impacted nodes, \# of impacted clusters, fault sources, blaming components and \# of impacted nodes per cluster.

![](/assets/BinaryDecision.png)

