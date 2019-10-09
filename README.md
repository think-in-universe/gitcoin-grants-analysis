## Executive Summary

In this project, we worked on analyzing the GitCoin Grants CLR Round 3 dataset to understand how the mechanism of CLR works, and how it demonstrates the value of the mechanism, and what's the major issues it faces and how to improve.

### Background

[![Gitcoin Grants](http://img.youtube.com/vi/eVgEWSPFR2o/0.jpg)](https://youtu.be/eVgEWSPFR2o)

This research report is built for understanding the patterns and issues in [Gitcoin Grants](https://gitcoin.co/grants/), especially for Gitcoin Grants CLR Round 3. For more details about the background, check out this Gitcoin issue to learn more: https://gitcoin.co/issue/gitcoinco/data-ops/40/3530

We're intersted in the effectiveness about the Grants funding process and results. We'll first analyze the patterns of the grants and contributions, and then verify whether there're collusions in the contributions. (Gitcoin Grants CLR Round 3 makes use of Pairwise Bonding ( https://ethresear.ch/t/pairwise-coordination-subsidies-a-new-quadratic-funding-design/5553 ) to prevent collusion)

There're several key questions we'd like to study in this research, as mentioned in https://github.com/gitcoinco/data-ops/issues/40, and we mainly focus on (1) the **bias** in the contribution, and (2) the possible **collusions** that we can found by analyzing IP addressed and paired contributions.

### Data Sources

Below datasets are avialble for investigation:

1. The anonymous dataset about Gitcoin Grants CLR Round 3 contributions: https://gist.github.com/owocki/1d6deebe478bfbda3656bb243aab2610


### Bias Analysis

It's interesting to learn about the patterns/trends, especially the bias, in the CLR grants/contributions, to understand how this mechanism works, and pros/cons of this design.

1. When Liberal Radicalism is designed for public good, the bias we found in **tags, keywords, and history**, do reflect its intention to **support the community's public good**. The focus on the "Ethereum" related keywords demonstrated the shared public benefits of the community, but it also indicates that the Gitcoin community may not be active to fund open source projects in a broader and general space of open source projects outside the Ethereum and blockchain world.

2. The distribution of the funds are quite skewed and showed the **competition nature** of the Grants CLR practice. Only the projects that really matter to the "Ethereum" community will be provided with effective funds. However, we need to add further analysis about the impact of the project team leads, etc. to understand how the fund contribution are impacted.

### Collusion Analysis

We do find interesting clues for collusion analyisis, and further analysis could be done to confirm the details.

1. By grouping the contributions from the same IP address, but are submitted from multiple profiles, we're able to detect **14** groups of grants that are possibly related to each other.

1. In the pairwise coordination, it's interesting to find quite a few pair of profiles/users have apparent shared interests in grants. For example, the top 1 pair profiles (`5b35dfc38e8523fe86422a9a12524ae02bc8d40448a4a1db96af800b` and `775fec778ed2672f511d864e139552a3690de36a93de3a8733773678`), shared **34 grants** in their contribution (more than 1/3 of the total number of grants). **102** pairs of contributors have more than 10 shared grants in Round 3.  Further analyiss needs to be done to understand the relationship between the users.


For more details about this report, check the [Jupyter Notebook](./analysis.ipynb) to learn more.

### Future Plan

Add more data sources

1. More datasets about the activities data on social media, GitHub, etc. of the projects leads and fund contributors are necessary to analyze the bias towards social impact and the further investigation about the offchain collusion.

Generalize the research

1. Apply the same model of CLR data analysis to more areas of public good, in order to improve the mechanism and strategy of CLR.
