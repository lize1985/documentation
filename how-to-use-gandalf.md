# Gandalf Spatial and Temporal Algorithm

# Overview {#overview}

In the cloud infrastructure, it is often the case that many core components are updated simultaneously and independently. As the cloud infrastructure also has a variety of configurations \(both in hardware and software\), the initial impact of a bad rollout may typically be hidden as the entire cloud seems healthy, yet several specific configurations may be very severely impacted. In a traditional system, there is already a wide impact radius once such issues are detected, often after days of rollout. The Safe Deployment algorithm is an algorithm aims to

* monitor and auto-stop bad rollouts

* aid diagnosis by pinpointing the most severely impacted parts of the cloud infrastructure.

This is achieved through two processes:

1. a global correlation between failure events against rollout events, identifying which rollouts are suspicious

2. A decision process, which assess the quality of a rollout by looing at the overall customer impact and generate go/no-go decision for a rollout.

_**Figure 1**_shows the basic workflow of the gandalf safe deployment model​. The gandalf model consists of 5 steps.

* Ensemble Voting

* Temporal Correlation

* Spatial Correlation

* Exponential decaying

* binary decision/supporting evidence

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQgej_ehJOzzXzelVNa%2F-LQgfO0NVNRj6a_W33Pe%2Fimage.png?alt=media&token=f6338257-e3cf-44f2-bae3-1a769e25b19b)

Figure 1 Gandalf Model for Safe Deployment

# Ensemble voting {#ensemble-voting}

In the ensemble voting step, we are trying to identify candidates attributing components for each fault signature. Each fault votes components deployed in the same nodes in a time window and Aggregate the votes and get candidate attributing components for each fault

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQgej_ehJOzzXzelVNa%2F-LQgg4F-InFI-h6ogIWV%2Fimage.png?alt=media&token=cbc8cc7d-bb97-4b4a-bc7a-8fe930747f95)

Ensemble voting

# Temporal Correlation {#temporal-correlation}

Filter out the ambient noise in last 72 hours and calculate a temporal correlation score

![](https://microsoft.sharepoint.com/teams/Gandalf46/SiteAssets/Gandalf%20Safe%20Deployment/Home/CorrelationFunction.PNG "CorrelationFunction.PNG")w is the weight of the time segment; P is number of fault nodes after deployment and b is the number of fault nodes before deployment Then we identify the suspicious components by associatingthe faults to the component with the greatest temporal correlation![](https://microsoft.sharepoint.com/teams/Gandalf46/SiteAssets/Gandalf%20Safe%20Deployment/Home/ranking.PNG "ranking.PNG")​

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQgej_ehJOzzXzelVNa%2F-LQggFhSr9HgTnAFQikU%2Fimage.png?alt=media&token=592bd746-f60e-4c3d-aa66-d205bc199651)

Temporal Correlation

# Spatial Correlation {#spatial-correlation}

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQgej_ehJOzzXzelVNa%2F-LQggTfiuL9YDwfl170O%2Fimage.png?alt=media&token=1f98f1b8-daa4-4837-b416-d7f41fd7c52e)

Spatial Correlation

Given a rollout component i at time t

N\(i,j\) : Num of**rollout nodes**with a fault signature j for a component i

F\(j\) : Num of**all**nodes with fault signature j during the deployment period

Spatial correlation for a fault signature j is

P\(t│i,j\)=N\(i,j\)/F\(j\)

Filter out faults if P\(t\|i,j\) that is less than a threshold

# Exponential Time Decaying {#exponential-time-decaying}

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQgej_ehJOzzXzelVNa%2F-LQggncrI02o7IG6Qajp%2Fimage.png?alt=media&token=29d140df-900d-4f94-b2c1-b40abf2d7456)

Exponential Time Decaying

In this step, gandalf will gradually forget the blaming on the old components exponentially and focus on new component Decay ratio are scaled to \[a, b\]![](https://microsoft.sharepoint.com/teams/Gandalf46/SiteAssets/Gandalf%20Safe%20Deployment/Home/delaying.PNG "delaying.PNG")​

# Binary Decision {#binary-decision}

In the binary decision step, we evaluate the impact of the rollout based on the features such as \# of impacted nodes, \# of impacted clusters, fault sources, blaming components and \# of impacted nodes per cluster.

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQgej_ehJOzzXzelVNa%2F-LQggyvRQ-gihAwGEn0H%2Fimage.png?alt=media&token=1f53c61a-697a-40d9-a8ef-100b8d8431e7)

