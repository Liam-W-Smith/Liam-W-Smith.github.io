---
layout: page
title: Research Compendia as a Tool to Learn Spatial Analysis
---
As described in previous blog posts, it is difficult, if not impossible, to reproduce many geospatial studies.
Even our top geospatial researchers find that the contents of academic journal articles provide insufficient information from which to deduce the authors' workflow.
Researchers today are beginning to use *reproducible research notebooks* and *cyberinfrastructure* to resolve these issues.

A *reproducible research notebook* is a virtual notebook containing the data, code, and outputs of a formal research study.
By gathering the code, comments, and output all in one location, a research compendium makes it crystal-clear what the researchers are doing and how they are doing it.
With the click of a button, users can run the code that computes the researchers' results, generating a complete computational replication of their analysis.

*Cyberinfrastructure* refers to the distribution of high-powered information technology which can be accessed from around the world.
Cyberinfrastructure is essential for *CyberGIS*, which is geospatial analysis that draws on the computational power of cyberinfrastructure.
Cutting edge geospatial researchers take advantage of both research compendia and CyberGIS by publishing research notebooks on cyberinfrastructure platforms.
Reproducible research notebooks in CyberGIS environments allow individuals to run spatial analyses confirming the computational reproducibility of complex studies on cyberinfrastructure from their own personal computers.

A prevalent example of CyberGIS is the CyberGISX project, which allows individuals across the country, including us students at Middlebury College, to run GIS code on the same bank of supercomputers used by researchers at the University of Illinois Urbana-Champaign.
This CyberGIS project, and others like it, aim to create a collaborative, distributed, and large scale geospatial community running GIS analyses on high performance supercomputers.

While it's difficult for geospatial researchers to reproduce studies without a research notebook, it's even more challenging for students.
For Open Source GIS last week, we read Kang et al's paper, *Rapidly measuring spatial accessibility of COVID-19 healthcare resources: a case study of Illinois, USA*.
During class, we did our best to create a workflow that could achieve the results from the paper.
The paper included a few spatial analysis techniques which I was not familiar with (i.e. egocentric graphs and the Enhanced Two-Step Floating Catchment Area method), and I think it's fair to say I could not have generated the workflow on my own.
But with some help from Derrick, who has worked with the paper's research compendium extensively, I found that I could understand, generally, the process by which the authors performed their analysis.

In lab, we proceeded to review the study's Jupyter Notebook on CyberGISX, which includes the code and data necessary to complete their analysis.
As we reviewed their analysis to see how they implemented our workflow diagram with code, the complexity of the analysis became more and more apparent to me.
It's one thing to generate a workflow diagram that is implementable in QGIS; it's a completely different animal to code GIS analyses in Python.
Functions that are conceptually simple on paper can take 50 lines of code to implement with Python.
The fact that the compendium provided me with the code allowed me to understand the study's geospatial analysis at a level that would take days and days of work without it.

In order for a student to learn from reading the code in a research compendium, they must understand how that code works.
Including descriptions before and comments within code chunks is the most effective way for a code writer to communicate code for learning.
In the Kang et al reproduction notebook, the pre-processing file very well commented, with a line of comments before every major operation in the code.
The original analysis and the reanalysis files are not as detailed with their comments; they tend to include comments at the beginning of code chunks describing what the code will accomplish, with less information within the code.
As code chunks lengthen, it quickly becomes difficult to keep track of the purpose of each individual line of code.
For example, in both the original analysis and the reanalysis, the code chunk defining the function, 'network_setting', includes over 30 lines of code but only a handful of comments, most of which relate merely to the units of analysis.
Additional comments describing the purpose of different lines of code would go a long way towards making the code more digestable for students.


HERE I DIFFERENTIATE BETWEEN A COMPUTATIONAL REPRODUCTION AND A CREDIBILITY REPRODUCTION



**Video**
Reproduction for computability vs reproduction for credibility.
Granted sufficient code, one can compute all of the results of an initial study without really understanding the motive for using every method.
Reproduction for credibility, however, demands a more critical approach.
In addition to assessing whether the same computations lead to the same result, a reproduction for credibility involves critically examining the reason for every computation in order ensure accuracy.
In a reproduction for computability, the methods and results are assumed to be correct.
In a reproduction for credibility, one focuses on all aspects of the study.

It is useful for students to conduct a computational reproduction before diving into the details of whether or not the methodology is sound, because it provides some context for the study.
In class last week, we all worked together to generate a workflow for the original study.
I found this to be very conceptually helpful.
Looking over the code in the Jupyter notebook, we saw how the authors implemented that workflow with Python code.
For this reason, I feel pretty confident about my conceptual understanding of the process.
However, I can't say that I understand what all of the code is doing.
That would require a much more extensive dive into the code, and would be much easier if there were more detailed comments.


**References**
- Wang, S. (2019). Cyberinfrastructure. The Geographic Information Science & Technology Body of Knowledge (2nd Quarter 2019 Edition), John P. Wilson (Ed.). DOI: 10.22224/gistbok/2019.2.4
- Kang, J. Y., A. Michels, F. Lyu, Shaohua Wang, N. Agbodo, V. L. Freeman, and Shaowen Wang. 2020. Rapidly measuring spatial accessibility of COVID-19 healthcare resources: a case study of Illinois, USA. International Journal of Health Geographics 19 (1):1–17. DOI:10.1186/s12942-020-00229-x.
- Kedron, Peter and Joseph Holler, 2021-08-23, Geospatial Fellows Webinar Series: [Working with students to reproduce COVID-19 research to establish the credibility of findings and accelerate policymaker adoption](https://aag-geospatialfellows-series.secure-platform.com/a/solicitations/16/sessiongallery/250)
