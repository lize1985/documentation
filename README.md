# Introduction

​The multiple software components at different layers of a cloud system are continuously deployed and updated in hundreds to millions of nodes \(e.g., Azure infrastructure system, Bing service\). A cloud system can be highly complex such that the defect brought by a small change in one component may lead to system failures and significant customer impact \(e.g., virtual machine downtime of Azure IaaS\). Making sure the faults caused by the rollout of her own component at the early stage of the rollout are identified out of all faults that may be caused by other reasons \(rollout of other components, HW issue, etc.\) is crucial for a release manager since it allows her to timely roll back the changes before causing a broad impact. It is also a challenging task due to multiple source of failures, the intersection of multiple component rollouts, and the high frequency of the rollouts.

Typical solutions, like component level watchdog, are effective for capturing immediate issues, while it is less effective in the following cases: \(1\) false positives: some failures not caused by the rollout are reported; \(2\) issues happened across multiple environments \(e.g., cluster, region\) which is not severe locally but severe enough globally can be missed; \(3\) latent issues, which happen hours after the rollout, may be missed. Gandalf, an intelligence end to end analytics service for safe deployment of cloud service, which addresses these challenges

The input of Gandalf is failure signals and rollout events published to Cosmos/Kusto. Gandalf can continuously monitor these signals, proactively notify deployment engine for automatically stopping bad rollouts, and provide supporting evidence and details for engineers to easily understand the issue and root cause it through an intuitive and interactive front-end.

Gandalf is chartered to provide an OFFLINE, INDEPEDENT Global Monitoring to ensure the safety of the rollout in the last frontier.

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LJZsnkigrCjlOhHlu6R%2F-LQfCcNu22zJfSK7eT-t%2F-LQfCjfMwgPzrPVoqZGd%2Flayeredworkflow.png?alt=media&token=3fde1e25-6251-481c-a9f8-6c8021eb8e9b)

                                                                                         **Figure 1. Safe Deployment Hierarchy**

_Gandalf Safe Deployment data service is a reliable and intelligent web service that provides component deployment safe guard by_

_\(1\) Continously monitoring based on Cosmos, Kusto datasets_

_\(2\) Intelligent no-go decision making based on state-of-art machine learning algorithms_

_\(3\) Reactive UI for self diagnosis in different pivot levels based on popular open source frameworks such as react.js, D3, redux.js and etc._

_\(4\) Reliable Restful API support for customer data integration based on Service Fabrics_

_\(5\) Cluster level continuously monitoring and diagnosis_

