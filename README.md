## Executive Summary

In this project, we worked on analyzing the GitCoin Grants Round 3 CLR dataset to understand how the mechanism of CLR works, and how it demonstrates the value of the mechanism, and what's the major issues it faces and how to improve.

### Background

[![Gitcoin Grants](http://img.youtube.com/vi/eVgEWSPFR2o/0.jpg)](https://youtu.be/eVgEWSPFR2o)

This research report is built for understanding the patterns and issues in [Gitcoin Grants](https://gitcoin.co/grants/), especially for Gitcoin Grants Round 3 CLR. For more details about the background, check out this Gitcoin issue to learn more: https://gitcoin.co/issue/gitcoinco/data-ops/40/3530

We're intersted in the effectiveness about the Grants funding process and results. We'll first analyze the patterns of the grants and contributions, and then verify whether there're collusions in the contributions. (Gitcoin Grants Round 3 CLR makes use of Pairwise Bonding ( https://ethresear.ch/t/pairwise-coordination-subsidies-a-new-quadratic-funding-design/5553 ) to prevent collusion)

There're several key questions we'd like to study in this research, as mentioned in https://github.com/gitcoinco/data-ops/issues/40, and we mainly focus on (1) the **bias** in the contribution, and (2) the possible **collusions** that we can found by analyzing IP addressed and paired contributions.

### Data Sources

Below datasets are avialble for investigation:

1. The anonymous dataset about Gitcoin Grants Round 3 CLR contributions: https://gist.github.com/owocki/1d6deebe478bfbda3656bb243aab2610


### Bias Analysis

It's interesting to learn about the patterns/trends, especially the bias, in the CLR grants/contributions, to understand how this mechanism works, and pros/cons of this design.

1. When Liberal Radicalism is designed for public good, the bias we found in **tags, keywords, and history**, do reflect its intention to **support the community's public good**. The focus on the "Ethereum" related keywords demonstrated the shared public benefits of the community, but it also indicates that the Gitcoin community may not be active to fund open source projects in a broader and general space of open source projects outside the Ethereum and blockchain world.

2. The distribution of the funds are quite skewed and showed the **competition nature** of the Grants CLR practice. Only the projects that really matter to the "Ethereum" community will be provided with effective funds. However, we need to add further analysis about the impact of the project team leads, etc. to understand how the fund contribution are impacted.


### Collusion Analysis

We do find interesting clues for collusion analyisis, and further analysis could be done to confirm the details.

1. By grouping the contributions from the same IP address, but submitted from multiple profiles, we could find **14** suspecious IP addresses are used by **34** users to make **34** contributions. This brings us a question: is is possible there're 14 people/entities that used the 34 accounts to make exact one contribution by every account? If the answer is yes, why did he/she/they needs to do that? Besides, we need to analyze the **14** groups of grants that are possibly related to each other.

2. In the pairwise coordination, it's interesting to find quite a few pair of profiles/users have apparent shared interests in grants. **102** pairs of contributors have more than 10 shared grants in Gitcoin Grants Round 3 CLR. By looking into more detials, we find that the top 1 pair profiles (`5b35dfc38e8523fe86422a9a12524ae02bc8d40448a4a1db96af800b` and `775fec778ed2672f511d864e139552a3690de36a93de3a8733773678`), shared **34 grants** in their contribution (more than 1/3 of the total number of grants). The two users are ranked top 2 by the number of grants they contributed (73 and 53 respectively). The interesting part is that `5b35dfc38e8523fe86422a9a12524ae02bc8d40448a4a1db96af800b` has granted 25K+ USD in total, while `775fec778ed2672f511d864e139552a3690de36a93de3a8733773678` has granted 5 USD in total for 53 projects, with 0.0943 USD for each contribution evenly, within 4 to 5 hours.

3. By combing results of the above two kinds of analysis towards shared IP addresses and paired contributors, we can narrow down the investigation to find issues faster. By looking at the intersection of the users from the above two analysis, we found the below two profiles may worth investigation first: `ae03c652db8c8a17ea7a89c0593da5ed6c22598fa7a050210c5feb16` and `54356585c9c19db59c4fefd8d157db60bd084fd5218d10c754f46b55`. Similar to `775fec778ed2672f511d864e139552a3690de36a93de3a8733773678`, `ae03c652db8c8a17ea7a89c0593da5ed6c22598fa7a050210c5feb16` has made 5 USD contribution in total, split into 19 contributions evenly, 0.263 USD per contribution. We may request extra info from Gitcoin team to understand why this happens, if these accounts need more attention and analysis.

4. By combining the results, we can also find the shared grants that are contributed by the accounts that are controlled by the same IPs from the
There're **11** such IPs and **26** such accounts / profiles. For example, the IP address `2ceb75027f1a1132d6cf349ea2bcd918b0f79acdb65c4f68dbf06154` has contributed to grant `/grants/79/lodestar-eth20-client` with 4 different accounts, each with **10 USD**, which probably is kind of collusion

For more details about this report, check the [Jupyter Notebook](./analysis.ipynb) to learn more.

### Future Plan

Add more data sources

1. We need to incorporate more data from Gitcoin activities to understand the behaviors of the users.
2. More datasets about the activities data on social media, GitHub, etc. of the projects leads and fund contributors are necessary to analyze the bias towards social impact and the do further investigation about the offchain collusion.

Generalize the research

1. Apply the same model of CLR data analysis to more areas of public good, in order to improve the mechanism and strategy of CLR.
