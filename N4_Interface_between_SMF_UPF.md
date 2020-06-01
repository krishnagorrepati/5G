# N4 Interface between SMF and UPF

###### 3GPP specs TS 23.502 and TS 29.244



![https://github.com/krishnagorrepati/5G/blob/master/n4_app.png](https://github.com/krishnagorrepati/5G/blob/master/n4_app.png)



In the 5G Core (5GC) network the N4 Interface is the bridge between the control plane and the user plane. As such, it is the conduit for PDU session management and traffic steering towards the UPF and PDU usage and event reporting towards the SMF. The SMF conveys the policy rules obtained from the PCF regarding packet handling, forwarding, and usage reporting to the UPF. In order for the UPF to recognize the user plane traffic that must be governed by a particular rule, it uses the Packet Flow Descriptions (PFDs) that are also supplied by an SMF. Finally, in some scenarios the SMF may buffer user plane traffic or forward user plane traffic towards the DN or the UE via the UPF

#### N4 Session Establishment, Modification, and Release

The SMF uses these procedures to manage N4 contexts in associated UPF(s). It uses the N4 Session Establishment to create a new PDU session in the UPF or to change the UPF for an existing PDU session. The information conveyed to the UPF includes the identifiers for the entities involved as well as policy rules that govern UPF behavior regarding that session. 

The SMF uses the N4 Session Modification procedure to update context information as needed. When an SMF determines that an N4 context should be removed from a UPF it initiates the N4 Session Release procedure. A UPF includes any reporting information not yet conveyed to the SMF in the release response message.

As mentioned above, policy rules provided by the SMF  received from PCF may govern the conduct of a UPF in managing a PDU session. Any of the following rules may be conveyed to a UPF:

- Packet Detection Rule (PDR)
- Forwarding Action Rule (FAR)
- QoS Enforcement Rule (QER)
- Usage Reporting Rule (URR)
- Buffering Action Rule (BAR)

#### N4 Report

A UPF uses this procedure to notify the SMF of information that is  not related to a specific N4 session but which may affect all sessions,  such as a user plane path failure with a remote GTP-U peer.

#### N4 Session Report

During N4 session establishment an SMF instructs the UPF to  periodically report certain N4 session-level events. The UPF, in turn,  initiates an N4 Session Report when indicated. The report may include  any of the following items:

- Usage report — transmits the usage data collected for charging purposes
- Start of traffic detection — triggered when traffic described by a PDR is first detected
- Stop of traffic detection — triggered when the end of traffic described by a PDR is detected
- Detection of first downlink data to UE in CM-IDLE state — triggered  when a downlink packet is received but there is no N3 tunnel for  downlink transmission
- PDU session inactivity — triggered when the inactivity timer specified by the SMF expires

#### Heartbeat

A PFCP node initiates the Heartbeat procedure — a simple request/response transaction — to determine whether a PFCP peer is still alive.

#### Load Control and Overload Control (Optional)

UPFs that support Load Control will periodically include the Load Control Information (LCI) IE in normal PFCP signalling to SMFs that likewise support this procedure. The IE includes a load metric that informs the recipient of the current load on the UPF as a percent of its total capacity. The receiving SMF(s) may, when indicated, take actions to regulate the load such as directing traffic to another UPF.

When a UPF that supports Overload Control realizes that its load has or is about to exceed its capacity it includes the Overload Control Information IE (OCI) in normal PFCP signaling to supportive SMFs. In this case the metric used indicates the percentage of reduction in traffic requested by the UPF. The receiving SMFs should attempt to mitigate the overload condition by reducing the requests sent to the UPF by the amount indicated and may take other actions that are implementation specific.

References:-

[https://www.developingsolutions.com/products/dstest-5g-core-network-testing/n4-interface/](https://www.developingsolutions.com/products/dstest-5g-core-network-testing/n4-interface/)

