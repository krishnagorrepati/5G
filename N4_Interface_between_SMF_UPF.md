# N4 Interface between SMF and UPF

###### 3GPP specs TS 23.502 and TS 29.244



![n4_app](https://github.com/krishnagorrepati/5G/n4_app)



In the 5G Core (5GC) network the N4 Interface is the bridge between the control plane and the user plane. As such, it is the conduit for PDU session management and traffic steering towards the UPF and PDU usage and event reporting towards the SMF. The SMF conveys the policy rules obtained from the PCF regarding packet handling, forwarding, and usage reporting to the UPF. In order for the UPF to recognize the user plane traffic that must be governed by a particular rule, it uses the Packet Flow Descriptions (PFDs) that are also supplied by an SMF. Finally, in some scenarios the SMF may buffer user plane traffic or forward user plane traffic towards the DN or the UE via the UPF

As mentioned above, policy rules provided by the SMF received from PCF may govern the conduct of a UPF in managing a PDU session. Any of the following rules may be conveyed to a UPF:

- Packet Detection Rule (PDR)
- Forwarding Action Rule (FAR)
- QoS Enforcement Rule (QER)
- Usage Reporting Rule (URR)
- Buffering Action Rule (BAR)



References:-

[https://www.developingsolutions.com/products/dstest-5g-core-network-testing/n4-interface/](https://www.developingsolutions.com/products/dstest-5g-core-network-testing/n4-interface/)

