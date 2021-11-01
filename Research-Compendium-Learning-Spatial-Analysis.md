---
layout: page
title: Research Compendia as a Tool to Learn Spatial Analysis
---
As described in previous blog posts, it is difficult, if not impossible, to reproduce many geospatial studies.
Even our top geospatial researchers find that the contents of academic journal articles provide insufficient information from which to deduce a workflow.
Researchers today are beginning to use **reproducible research notebooks** and **cyberinfrastructure** to resolve these issues.

A **reproducible research notebook** is a virtual notebook containing the data, code, and outputs of a formal research study.
By gathering the code, comments, and output in a single location, a research compendium makes it crystal-clear what the researchers are doing and how they are doing it.
With the click of a button, users can run the code in the notebook, generating a complete computational replication of the analysis.

**Cyberinfrastructure** refers to the distribution of high-powered information technology which can be accessed from around the world.
Cyberinfrastructure is essential for **CyberGIS**, which is geospatial analysis that draws on the computational power of supercomputers.
By publishing research notebooks on CyberGIS platforms, cutting edge researchers not only allow others to reproduce their results, but also endow people with the computational power with which they can actually complete the computations.

A prevalent example of CyberGIS is the CyberGISX project, which allows individuals across the country, including us students at Middlebury College, to run GIS code on the same bank of supercomputers used by researchers at the University of Illinois Urbana-Champaign.
This CyberGIS project, and others like it, aim to create a collaborative, distributed, and large scale geospatial community running GIS analyses on high performance supercomputers.

While it's difficult for geospatial researchers to reproduce studies without a research notebook, it's even more challenging for students.
For Open Source GIS last week, we read Kang et al's paper, *Rapidly measuring spatial accessibility of COVID-19 healthcare resources: a case study of Illinois, USA*.
During class, we did our best to create a workflow that could achieve the results from the paper.
The paper included a few spatial analysis techniques which I was not familiar with (i.e. egocentric graphs and the Enhanced Two-Step Floating Catchment Area method), and it's fair to say that I could not have generated the workflow on my own.
But with some help from Derrick, who has worked with the paper's research compendium extensively, I found that I could understand, generally, the process by which the authors performed their analysis.

In lab, we proceeded to review the study's Jupyter Notebook on CyberGISX, where the complexity of the study's code become quite apparent.
The parallel processing component abstracted everything to a different level, and functions that may seem conceptually simple on paper took lines upon lines of code to implement with Python.
Being provided with the code granted me a glimpse of the study's geospatial analysis, something that would have taken weeks and weeks of work without the compendium.

In order for a student to learn from reading the code in a research compendium, they must be able to understand how that code works.
Including descriptions before and comments within code chunks is the most effective way I know for a code writer to make their code comprehensible.
Unfortunately, even the files in the compendium we reviewed in class are not perfectly commented.
To be fair, the pre-processing file is very well commented, with a line of comments before every major operation in the code.
But the original analysis and the reanalysis files are not as detailed with their comments; they tend to include comments at the beginning of code chunks describing what the code will accomplish, and less information within the code.
As code chunks lengthen, it quickly becomes difficult to keep track of the purpose of each individual line of code.
For example, in both the original analysis and the reanalysis, the code chunk defining the function, 'network_setting', includes over 30 lines of code but only a handful of comments, most of which relate merely to the units of analysis.
Additional comments describing the purpose of different functions nested within the code would go a long way towards making the code more digestable for students.

It's also important to note the difference between a reproduction for computability and a reproduction for credibility.
In a reproduction for computability, the methods and results are assumed to be correct and only the computations are verified.
Granted sufficient code, such as the notebook for the Kang et al. study, one can compute all of the results of an initial study without really understanding the motive for using every method.
In lab, we ran all the code and quickly conducted a reproduction for computability.
A reproduction for credibility, however, demands a more critical approach in which one considers the validity of all methods in the study.
It's a more substantial intellectual task, which can also be difficult to accomplish when code chunks lack descriptive comments.
As a class, we conducted our computational reproduction before attempting to evaluate the study's credibility, and for both researchers and learners, I think this method has merit.
By first skimming through the code and discovering what it outputs, one familiarizes themself with the study and the CyberGIS environment, preparing themselves with the context required to conduct a reproduction for credibility.

While they are seldom perfect, especially when it comes to code comments, research notebooks with CyberGIS definitely improve reproducibility and make geospatial research easier to digest.
As academics increasingly document their work with online research compendia, geospatial knowledge is sure to become more accessible to fellow academics, students, and the general public, and geospatial studies are sure to become more reproducible.

**References**
- Wang, S. (2019). Cyberinfrastructure. The Geographic Information Science & Technology Body of Knowledge (2nd Quarter 2019 Edition), John P. Wilson (Ed.). DOI: 10.22224/gistbok/2019.2.4
- Kang, J. Y., A. Michels, F. Lyu, Shaohua Wang, N. Agbodo, V. L. Freeman, and Shaowen Wang. 2020. Rapidly measuring spatial accessibility of COVID-19 healthcare resources: a case study of Illinois, USA. International Journal of Health Geographics 19 (1):1–17. DOI:10.1186/s12942-020-00229-x.
- Kedron, Peter and Joseph Holler, 2021-08-23, Geospatial Fellows Webinar Series: [Working with students to reproduce COVID-19 research to establish the credibility of findings and accelerate policymaker adoption](https://aag-geospatialfellows-series.secure-platform.com/a/solicitations/16/sessiongallery/250)
