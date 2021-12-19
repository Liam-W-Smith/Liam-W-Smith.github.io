---
layout: page
title: The Role of Open Source GIS in Resolving the Reproducibility Crisis
---

In recent years, the reproducibility crisis has garnered the attention of the popular media and the concern of the scientific community.
In today's blog post, I'd like to discuss the reproducibility crisis in the context of geography and evaluate the extent to which open source GIS might address the issue.

First, let's define a few key terms.
The ***reproducibility crisis*** is the dilemma that scientific studies tend to be difficult to *reproduce* and *replicate*.
Various definitions of reproducibility and replicability are used in different academic circles, but for the purposes of this blog post, we'll use the definitions set forth by the Committee on Reproducibility and Replicability in Science.
According to the committee, ***Reproducibility*** refers to "obtaining consistent results using the same input data, computational steps, methods, and code, and conditions of analysis."
And ***Replicability*** refers to "obtaining consistent results across studies aimed at answering the same scientific question, each of which has obtained its own data."
In other words, a study is reproducible when an independent reviewer can follow the study's data and methodology to the same result, and a study is replicable when another researcher can obtain the same result by conducting their own study.

Non-reproducibility and non-replicability pose significant risks for the scientific community.
If one cannot reproduce the analysis of a study, then it is impossible to verify the results of that analysis.
And if one cannot replicate a study, then it is impossible to validate and expand on the study's conclusions.
As such, non-reproducibility and non-replicability tend to obscure erroneous results, which lead researchers and the general public astray.

To prevent researchers from inadvertently publishing falsehoods, research ought to be subject to thorough review.
While the current publishing model benefits from a long-held peer review process, this process fails to ensure adequate reproducibility and replicability.
Researchers write code to analyze large datasets, but they are required to submit neither their code nor their data when they submit articles for publication.
This leaves peer reviewers, and later the general public, to evaluate only the written word.
Without adequate documentation of code and data, it is impossible to evaluate the methodology and data analysis of many studies, much less fully reproduce and replicate them.
In this manner, rather than promoting thorough and complete review, the current publishing model hinders it.

Moreover, our academic model creates an incentive structure that promotes bias and necessitates better review.
Publishing a paper in a prestigious journal, such as *Nature* and *Science*, is key to establishing a reputation in the scientific world.
Especially for researchers at the beginning of their careers, getting published helps secure tenure and future research grants.
Because these publications accept only a fraction of their submissions, researchers are motivated to make their submissions stand out: this means bolder claims and more convincing results.
This incentive to overstate enhances the need for scientists to check the results of their peers, but as previously discussed, our publishing model fails to allow for the reproduction and replication that might hold this incentive in check.

The field of geography has ignored the issues of reproducibility and replicability to an even larger extent than other scientific disciplines, but geographers can start addressing the reproducibility crisis now by practicing Open Source GIS.
In traditional academic settings, researchers work alone or in small teams and solicit feedback only when submitting an article for peer review.
In contrast, in the open source world, researchers regularly upload their code and ask the open source community for feedback troubleshooting help.
In this manner, one's methodology remains public information, making it much easier for others to reproduce and replicate one's work.
Ideally, journals would mandate the disclosure of data, workflows, and statistical analysis in journal submissions, but that appears unlikely to occur in the foreseeable future.
Absent these changes, the open source community provides a great platform for researchers to make their studies transparent.
Moreover, even if journals were to make the appropriate changes, sharing methodology and code on open source platforms would be of enormous help.
The sad reality is that publishing a journal article is a lengthy process that can take over a year.
If geographers shared their GIS code on open source platforms, then other researchers could conduct reproducibility and replicability analyses immediately, rather than waiting for the study to -- *potentially* -- be published in a journal sometime in the next year.
Additionally, open source practices may help realign the incentive structure of academia.
In the open source realm, one's reputation depends on how useful one is to the community.
Troubleshooting for others, posting novel techniques and results that can be evaluated by others, and acting in a manner that benefits the open source community as a whole is how one builds a reputation, rather than by publishing stand-alone research.
Because one's work is inherently subject to thorough review and one's reputation depends on how useful they are to others, open source GIS realigns the incentive structure to favor honesty over bias and collaboration over individualism.
This paradigm shift in the incentive structure of academia would reduce the liability of researchers to exaggerate their findings, thus reducing the urgency of the reproducibility crisis.

In the field of geography, studies may be non-replicable or non-reproducible for the standard reasons, such as the unavailability of data and methodology.
However, studies could also fail to be reproducible or replicable for reasons beyond any open source fix.
Geography has integrates several ways of knowing, including non-scientific ones, which pose challenges to reproducibility and replicability.
Specifically, geography benefits from both idiographic and nomothetic approaches to knowledge.
The idiographic approach to knowledge, described by Kant as a tendency to specify, is when one looks for categorical ways to distinguish different phenomena from each other.
Geography exemplifies this mode of inquiry because it seeks to analyze and distinguish between different regions.
The nomothetic approach to knowledge, described by Kant as a tendency to generalize, is when one looks for laws that transcend place and time.
In the field of geography, the nomothetic approach manifests in efforts to derive laws about spatial patterns.
Reproducibility and replicability make sense in nomothetic contexts, and consequently are practiced in scientific fields from physics to economics to spatial analysis.
But how do we utilize replicability and reproducibility in idiographic contexts?
This is an open and prominent question in geography.
Analyzing and theorizing about the differences between regions is not really conducive to replication and reproduction.
Open Source GIS could help to some extent; for example, if an idiographic study were to use open source GIS software to map different patterns in different regions, then one could use the openly disclosed workflow to reproduce that map.
But this would constitute a very limited reproduction, since there would be no computation and statistical analysis to reproduce.
Other idiographic studies would be completely impossible to reproduce.
How, for example, would one reproduce an analysis of the cultural differences between two regions?
There is no code to run and no methodology to follow -- reproduction simply doesn't make sense.
The use of open source GIS does not inherently make idiographic approaches more replicable or reproducible, because such processes may depend on location and time or be humanistic in nature.

The current publishing and academic models provide insufficient opportunities for reproducibility and replicability, but in the field of geography, Open Source GIS has the potential to markedly improve these efforts.
However, reproducibility and replicability are primarily relevant to nomothetic inquiry, and it is difficult to imagine how one could reproduce and replicate most idiographic work, even with the assistance of open source GIS.

**References:**

- Rey, S. J. (2009). Show me the code: Spatial analysis and open source. *Journal of Geographical Systems*, 11(2), 191–207. [https://doi.org/10.1007/s10109-009-0086-8](https://doi.org/10.1007/s10109-009-0086-8)

- National Academies of Sciences, Engineering, and Medicine 2019. *Reproducibility and Replicability in Science*. Washington, DC: The National Academies Press. [https://doi.org/10.17226/25303](https://doi.org/10.17226/25303)

- Sui, D., & Kedron, P. (2021). Reproducibility and Replicability in the Context of the Contested Identities of Geography. *Annals of the American Association of Geographers*, 111(5), 1275–1283. [https://doi.org/10.1080/24694452.2020.1806024](https://doi.org/10.1080/24694452.2020.1806024)

- Singleton, A. D., Spielman, S., & Brunsdon, C. (2016). Establishing a framework for Open Geographic Information science. *International Journal of Geographical Information Science*, 30(8), 1507–1521. [https://doi.org/10.1080/13658816.2015.1137579](https://doi.org/10.1080/13658816.2015.1137579)
