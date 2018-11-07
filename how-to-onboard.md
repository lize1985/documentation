# How to Onboard

# Current Supporting Components {#current-supporting-components}

1. AgentPackage

2. SlbMonAgentHost

3. SLBHostPluginService

4. PolicyAgentHostPlugin

5. PhyNetAgentHostPlugin

6. PcmIncarnation

7. OSHostPlugin

8. NodeOSBaseImage

9. NMAgentHostPlugin

10. NetSecurityUpdateAgentHostPlugin

11. NetAnalyticsAgentHostPlugin

12. MonitoringAgentExeConfig

13. MonitoringAgentDllConfig

14. McfTemplateFile

15. LmAgentHostPlugin

16. GuestOS

17. GuestAgentHostPlugin

18. FirmwareUpgradeHostPlugin

19. DcmAgentHostPlugin

20. CredentialsManagementHostPlugin

# Current Monitoring Faults {#current-monitoring-faults}

* NodeFault

* ContainerFault

* OSCrash/AzureWaston

* NodeReboot/DirtyShutdown

* AgentFault

* Vmdowntime

# How to Onboard {#how-to-onboard}

Onboarding to Gandalf is extremely easy. You only need to provide us 2 dataset. One is mandatory and the other one is optimal. By default, gandalf will monitor 8 fault sources and the fault signals is expanding. The faults are presented in the section above

## \(1\) Events that need to be changed \(required\) {#1-events-that-need-to-be-changed-required}

* EventTime

* Cluster

* NodeId

* PivotGroup

* BuildVersion

* AdditionalEventInfo

## \(2\) Faults that need to be monitored and correlated \(Optional\) {#2-faults-that-need-to-be-monitored-and-correlated-optional}

* Faulttime

* Cluster

* NodeId

* PivotGroup

* Signature

* AdditionalDiagnositcsInfo

![](/assets/onboard.png)

