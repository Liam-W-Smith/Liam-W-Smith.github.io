---
layout: page
title: Research Compendiums as a Tool to Learn Spatial Analysis
---
Draw on specific examples from the Kang et al (2020) accessibility study and its associated research compendium and computational notebooks. LOOK FOR WAYS TO INTEGRATE THIS

Does the reproduction study with a research compendium in CyberGIS facilitate learning spatial analysis? How?
- yes, the research compendium compiled in the reproduction study is very helpful for students learning spatial analysis.
- As detailed in previous blog posts, it is difficult, even for our top researchers, to deduce one's workflow from an academic study.
- For students who are inexperienced with GIS, it is even more challenging.
- Research compendia with detailed instructions for running one's code makes things easier.
- In the example we have been looking at in class, all of the code required to accomplish the analysis is provided.
- it is still difficult to understand everything going on in the code, but it is far easier than trying to derive the workflow given a mere description of the study.
- ELABORATE. MAYBE USE SPECIFIC EXAMPLES.

Are there ways in which the research compendium could be improved to better facilitate learning? How?
- In order to learn from reading the code in a research compendium, one must understand what the code is doing and how the code works.
- Currently, the .ipynb file documenting pre-processing of data is very well commented, with a line of comments before every major operation in the code.
- The .ipynb files with the original analysis and the reanalysis are not quite as detailed with their comments.
- Both files contain comments at the beginning of most code chunks, which describe, generally, what the code in each chunk will accomplish.
- This information is helpful, but it could be more helpful.
- As code chunks lengthen, it quickly becomes difficult to track what each individual line of code is doing.
- For example, in both the original analysis and the reanalysis, the code chunk defining the function, 'network_setting', includes over 30 lines of code, but only a handful of comments, most of which relate merely to the units of analysis.
- A few comments describing the purpose of different lines of code would go a long way towards making the code more digestable for students.

ADD MORE
- Coming from a math background, I feel like I should understand everything I'm doing -- deriving from first principles.
SO this way of learning was strange for me.

**Notes on Reading**
- Cyberinfrastructure refers to the distribution of high-powered information technology and experienced users.
Cyberinfrastructure is essential for CyberGIS, which essentially is geospatial analysis that draws on the computational power of cyberinfrastructure.
A prevalent example of CyberGIS is the CyberGISX project, which allows individuals across the country, including us students at Middlebury College, to run GIS code on the same bank of supercomputers used by researchers at the University of Illinois Urbana-Champaign.
This CyberGIS project, and others like it, aim to create a collaborative, distributed, and large scale geospatial community running GIS analyses on high performance supercomputers.
- There are many opporunities to mutually advance cyberinfrastructure and CyberGIS, but there are also challenges.
One of the most concerning challenges today results from the proliferation of data sources, from remote sensing to social media data.
While these data may provide significant insight into physical and human geographic processes, the proliferation of data has also outpaced the creation of metadata.
Too often, data is published without sufficient information regarding its provenance and quality.
Innovation in the CyberGIS and cyberinfrastructure realms may be needed in order to address these issues.

DONE

maybe I should add something explaining the computatonal notebook side of it?

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
