*Draft Proposal*

**Guide to Applying to be on the XRP Ledger (XRPL) Foundation's Unique Node List (UNL)**

This document outlines the requirements, process, and evaluation criteria for individuals and organizations seeking to be included on the XRPL Foundation's Unique Node List (UNL).

**1. Initial Prerequisites and Validator Operation**

The first step in the process is demonstrating a history of reliable and secure operation within the XRPL network.

**Run a Non-UNL Validator**

Before applying for the UNL, you must successfully **run an XRPL validator that is not yet on the UNL for a sufficient period of time**. This is a necessary phase to prove your operational reliability and commitment to the network.

**Core Operational Requirement: Agreement and Uptime**

The single most critical requirement is being and remaining in **agreement with the network**. This is directly related to your validator's **uptime**.

  - Your server must be **well-maintained** and capable of keeping up with the network's demands.
  - If your uptime drops, your validator will not be in agreement with the network. High uptime is essential for the reliability of the UNL.

For technical instructions on setting up your validator, please refer to the official documentation:

  - **How to Run an XRP Ledger Validator:** [Running an XRP Ledger Validator](https://xrpl.org/blog/2020/running-an-xrp-ledger-validator)

**Demonstrating Stewardship and Track Record**

Beyond core operational uptime, candidates are strongly encouraged to actively participate in the network to build a verifiable track record of responsibility and commitment. This includes:

  - Timely Upgrades: Promptly upgrading your non-UNL validator to the latest rippled releases.
  - Responsible Governance: Active and thoughtful participation in the decentralized governance process, including casting votes on Fix Amendments in a timely and responsible manner.
      - Even though non-UNL votes do not count toward the formal amendment process, this establishes a clear, observable track record.
  - Community Engagement: Active participation in community discussions and testing efforts to demonstrate a long-term commitment to the network's health and evolution.

**2. The Application Process**

Once you believe your validator is stable and you meet the operational requirements, you can formally apply for consideration.

**Submit a GitHub Pull Request**

To begin the review process, you should go to **GitHub** and submit a **pull request** (PR). This PR serves as your formal application, stating your readiness and desire to be considered for inclusion on the UNL.

Please use this guide, and existing PRs, as a guide to what information should be included in order to be selected. Sensitive information can also be communicated via private channels.

  - **GitHub UNL Repository:** [https://github.com/XRPLF/unl](https://github.com/XRPLF/unl)

**Trust and Reputation**

While the review process can be lengthy, it may be faster for applicants who have established **community credit** or **community reputation** within the XRPL ecosystem. The entire process hinges on demonstrating **trust** to the network and the Foundation.

**3. Evaluation Criteria and Performance**

The XRPL Foundation examines a wide array of criteria, both technical and qualitative, to assess a candidate's suitability. Current decisions are based on objective analysis of these factors.

**Technical Performance Metrics**

| Metric                         | Description                                                                                       |
| :----------------------------: | :-----------------------------------------------------------------------------------------------: |
| Consensus uptime               | Sustained high performance, matching the network's consensus. This is a crucial proxy for uptime. |
| Upgrade promptness/communication | How quickly the operator updates to the latest rippled releases.                                  |
| Emergency promptness           | The ability to rapidly respond to critical issues.                                                |
| Fix Amendment voting           | Active and correct participation in the network's decentralized governance process.               |
| xrp-ledger.toml completeness   | Proper setup and identification of the validator using the configuration file.                    |
| Capacity for network bursts    | Headroom within system specifications and bandwidth                                               |

**Security Requirements (Critical for UNL)**

A UNL validator carries a unique level of **trust** and responsibility, requiring a significantly higher security standard than a normal node.

  - **Preventing Tampering:** You must protect your server from being accessed or tampered with.
  - **Preventing Downtime:** The validator must be protected against attacks like **Denial of Service (DoS)**, which could bring the network to a halt if many UNL validators fail simultaneously.
  - **IP Address Obscuration:** It is vital to **keep the UNL validator’s IP address private** to protect against direct DoS attacks. This is typically achieved by running the UNL validator behind a proxy using another rippled node or multiple rippled nodes, or by using other traditional methods to keep the IP address obscured.
  - **Domain Verification:** This ensures a clear, public identity for the validator's operator.

The XRPL Foundation will conduct **penetration tests** over time on UNL validators to ensure that your validator cannot be easily taken down.

**Diversity Requirements**

Decentralization is a core goal. The Foundation actively seeks a distributed and resilient UNL.

| Diversity Factor              | Description                                                                                       |
| :---------------------------: | :-----------------------------------------------------------------------------------------------: |
| **Geographic diversity**      | Ensuring validators are not concentrated in one physical location.                                |
| **Geo political diversity**   | Distributing validators across different legal and political jurisdictions.                       |
| **Hosting diversity**         | Avoiding over-reliance on a single cloud or hosting provider.                                     |
| **Vertical / Industry diversity** | Ensuring participation from various sectors (e.g., exchanges, academic, independent).           |

**Soft/Qualitative Factors**

  - **Active on socials** | Engagement with the community and transparency. |
  - **Long-term Commitment** | Demonstrated long-term commitment to the network's health. |
  - **Stewardship** | Prioritizing the network's long-term integrity, decentralization, and shared success through thoughtful governance and reliable node operation.

**4. Monitoring Performance and The Final Decision**
This section describes how validator performance is monitored and how final UNL decisions are made.
**Monitoring Validator Performance**

You can monitor your validator's performance statistics, including agreement rate and other metrics, using the official network explorer:

  - **XRPL LiveNet Validators Page:** [https://livenet.xrpl.org/network/validators](https://livenet.xrpl.org/network/validators)
  - **XRPSCAN:** [Validator List on XRPSCAN](https://xrpscan.com/validators)

**Final Authority and UNL Management**

The final decision on which pull requests are approved for inclusion on the UNL rests with the **XRPL Foundation board** or a designated committee appointed by that board. A validator may adhere to all guidelines and not be included.
