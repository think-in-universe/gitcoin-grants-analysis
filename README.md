## Executive Summary

In this project, we worked on analyzing the GitCoin Grants CLR Round 3 dataset to understand how the mechanism of CLR works, and how it demonstrates the value of the mechanism, and what's the major issues it faces and how to improve.

We tried to answer the questions about (1) the **bias** in the contribution, and (2) the possible **collusions** that we can found by analyzing IP addressed and paired contributions.


### Bias Analysis

It's interesting to learn about the patterns/trends, especially the bias, in the CLR grants/contributions, to understand how this mechanism works, and pros/cons of this design.

1. When Liberal Radicalism is designed for public good, the bias we found in **tags, keywords, and history**, do reflect its intention to **support the community's public good**. The focus on the "Ethereum" related keywords demonstrated the shared public benefits of the community, but it also indicates that the Gitcoin community may not be active to fund open source projects in a broader and general space of open source projects outside the Ethereum and blockchain world.

2. The distribution of the funds are quite skewed and showed the **competition nature** of the Grants CLR practice. Only the projects that really matter to the "Ethereum" community will be provided with effective funds. However, we need to add further analysis about the impact of the project team leads, etc. to understand how the fund contribution are impacted.

### Collusion Analysis

We do find interesting clues for collusion analyisis, and further analysis could be done to confirm the details.

1. By grouping the contributions from the same IP address, but are submitted from multiple profiles, we're able to detect **14** groups of grants that are possibly related to each other.

1. The analyiss based on paired contribution is still working progress, and could combined with the IP addresses detection to reach more solid conclusion.


For more details about this report, check the [Jupyter Notebook](./analysis.ipynb) to learn more.

