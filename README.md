# Wesley Thesis 2019-202 Readme

This organization contains all the components used for the implementation and evaluation of the thesis Prefetching Network Requests in Android Apps: Strategies and Empirical Evaluation submitted for the 2019-2020 edition of 
the [Master Project Computer Science](https://studiegids.vu.nl/en/Master/2019-2020/computer-science/XM_0011) course 
at the [Vrije Universiteit Amsterdam](https://www.vu.nl/en).

## Repositories

This organization contains the following repositories:

| Repository     | Description                                                                                                                                                                                                                                        |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [android-runner](https://github.com/VU-Thesis-2019-2020-Wesley-Shann/android-runner) | Contains a fork from the [S2-Group](https://github.com/S2-group) [Android Runner](https://github.com/S2-group/android-runner) repository.  Framework used to orchestrate the experiment.                                                                                                                                        |
| [experiments](https://github.com/VU-Thesis-2019-2020-Wesley-Shann/experiments)    | Contains all configuration and files use to run the experiment and generated from it.                                                                                                                                                              |
| [NAPPA](https://github.com/VU-Thesis-2019-2020-Wesley-Shann/NAPPA)          | Contains a fork from the [S2-Group](https://github.com/S2-group) [NAPPA](https://github.com/S2-group/NAPPA) repository. All modifications to NAPPA were implemented here and merged back to the parent repository. All injected logging statements were implemented here and not merged back to the parent repository. |
| [subjects](https://github.com/VU-Thesis-2019-2020-Wesley-Shann/subjects)       | Contains the source code from all subjects, both the original and modified versions used for the experiments.                                                                                                                                      |

A more detailed description is provided in each repository.

## Abstract

### Context

In the past years, several solutions were implemented and researches conducted to reduce user perceived-latency. The most common approach to achieve this is via prefetching and caching techniques. However, studies show that the prefetch of network requests must be done with cautious. If prefetches are performed unrestrictedly, an undesirable runtime overhead can be introduced to the mobile device resources (e.g., CPU, memory, battery, bandwidth, etc.). This thesis focuses on the NAPPA framework, a Navigation Aware, Personalized, Prefetching technique for Android.

### Goal

This thesis proposes to improve NAPPA’s quality, in terms of correctness, usability, readability and maintainability. These improvements are motivated to facilitate the NAPPA technique usage in practice and contributing to future development and research.
Moreover, an empirical evaluation is performed to assess the NAPPA’s performance to provide a precise vision of the cost-benefit trade-off provided by NAPPA.

### Method

NAPPA is enhanced in a 3 step approach: identity, select and implement. Points of improvement are identified by using NAPPA, exploring its source code and  comparing its features with similar solutions in the literature. Based on a cost-benefit analysis, some improvements are selected for implementation.
The empirical evaluation is designed to assess NAPPA’s performance in terms of runtime overhead, user perceived-latency reduction, accuracy and prediction duration. A total of 7 real-world open-source applications are selected for this evaluation. 3 versions of the apps are considered: a baseline version without prefetching and 2 NAPPA-enabled versions, each containing a different prefetching strategy. A user navigation flow is defined to automatic interact with the applications. A total of 630 runs are performed, 30 per app and version combination.

### Results

The results showed that there is no significant statistical difference in terms of CPU load (p-value = 0.6501), energy consumption (p-value = 0.8476) and accuracy in predicting the user navigation (p-value = 0.4877).
The difference between the tested versions of the apps showed that there is a significant statistical difference in terms of memory consumption (p-value = 3.026e−11), reduction in user perceived-latency (p-value < 2.2e−16) and runtime duration in predicting user navigation (p-value = 0.0001148). However, these differences are either small or negligible, where the Cliff’s Delta effect size estimation is, respectively, −0.32518 (small), 0.181062 (small) and 0.04553116 (negligible).
Overall, a low number of prefetches is performed, resulting in assessing NAPPA in a “worst-case scenario”, where the benefits in prefetching are minimal.

### Conclusion

This thesis improved the quality of NAPPA and established evidence that NAPPA introduces minimal cost in exchange of reduced userperceived latency. However, further investigation showed that NAPPA’s current value lies within its caching capabilities rather than its prefetching capabilities.
