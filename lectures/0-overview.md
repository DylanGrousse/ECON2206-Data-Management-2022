# Data Management
## Introduction
### [Malka Guillot](https://malkaguillot.github.io/)
### HEC Liège | <a href="https://gitlab.uliege.be/mguillot/econ2306-data-management-2021-22/">ECON2306</a>


<!--
---
## Zoom rules before we begin
- Turn on video <i class="fas fa-video"></i> and set audio to mute <i class="fas fa-microphone-slash"></i>
- Set zoom name to “Full Name, School, Dept/Major”(ex: “Leon Smith, ETH Computer Science”)
- Say “hi” in the chat
-->

---

<!-- .slide:  id="toc" class: left, inverse -->
# Table of contents

1. [Prologue ](#prologue)

2. [Logistics](#logistics)

2. [General motivation](#motivation)

3. [Tools and resources](#tools_resources)

2. [Course outline](#course_outline)

2. [Epilogue](#hw)

Notes: my notes


--

## More interaction using
TODO: Configurer woodclap

--

## What do you want to learn during the class?


<div style="position:relative;  text-align: center;" >
<iframe allowfullscreen frameborder="0" height="100%" mozallowfullscreen src="https://app.wooclap.com/events/HHQNFR/questions/61e9758ca45a831197a500c0" width="100%"></iframe>
    <div style="position:absolute;  z-index:500;height:80%;width:100%;"></div>
</div>

---

<!-- .slide: id="prologue"  -->
# Prologue:
## (Big) **data** and (policy) **analysis**

<html><div style='float:left'></div><hr color='#EB811B' size=1px width=796px></html>


--

- (Big) Data can diagnose (and hopefully help solve) (policy)
problems.


- Visualization matters.

--

### Police discrimination in the US

- **Policy question**:
  - assess racial disparities in policing in the United States
-  <!-- .element: class="fragment" -->
  **Big data**:
  - Analyze a dataset detailing nearly 100 million traffic stops conducted across the country.
- <!-- .element: class="fragment" -->
  **Methodo**:
  - Use a sunset as a "veil of darkness" masks one’s race
- <!-- .element: class="fragment" -->
  **Result**:
  -    Black drivers were less likely to be stopped after sunset, suggesting bias in stop decisions

<div class="r-stack"><img data-src="./images/discrimination-police-us.png" style="height: 195px;" ><!-- .element: class="fragment" --></div>

<p><cite><i class="fa fa-book fa-fw" aria-hidden="true"> </i>
Pierson, E., Simoiu, C., Overgoor, J. et al.
<a href=https://rdcu.be/cfg4x>A large-scale analysis of racial disparities in police stops across the United States.</a>
Nat Hum Behav 4, 736–745 (2020).</cite></p>

Note:
For each window (19:00–19:15, 19:15–19:30 and 19:30–19:45), we compute the percentage of stops that involved black drivers for a series of 10-min periods before and after dusk. The figure is based on 112,938 stops of black and white drivers (35,270 during 19:00–19:15, 38,726 during 19:15–19:30 and 38,942 during 19:30–19:45), with points sized according to the total number of stops in each bin. The vertical line at t = 0 indicates dusk, at which point it is generally considered ‘dark’; we remove stops in the ~30-min period between sunset (indicated by the left-most vertical line in each panel) and dusk, as this period is neither ‘light’ nor ‘dark’. The dashed horizontal lines show the overall proportion of stops involving black drivers before and after dark, with 95% CI. For all three depicted time windows, black drivers comprise a smaller share of stopped drivers after dark, when a veil of darkness masks their race, suggestive of racial profiling

''Police stops suffer from persistent racial bias and point to the value of policy interventions to mitigate these disparities.''

--

(Big) Data can cause (or magnify) problems.

--

### Predictive policing

<div class="r-stack"><img data-src="./images/predictive-policing.png" style="height: 400px;" > </div>

--

### Predictive policing

<div class="r-stack"><img data-src="./images/predictive-policing-2.png" style="height: 400px;" > </div>

--

## Welcome

- This course focuses on applications of <bcolor> big data tools to public policy analysis </bcolor>

<div class="r-stack"><img data-src="./images/policy-data.jpeg" style="height: 200px;" ></div>


- Goals:
  - Equip you with the standard machine learning toolkit.
  - Put it to work on a real-world policy project.


--

## What this course is, and is not
- It is:
  - Applied and oriented towards practice;
  - General overview of different techniques - what they are and how to use them.
  - Data analysis in general, not restricted to a research or a  field (economics, political science).
  - In python.
- It is not:
  - Computer science. We’re not coding up models from scratch.
  - Mathematical statistics. We’re not deriving the functions by hand.

--

<!-- .slide: id=""-->
## Who am I?

  <div class="image-float">
    <p style="position: relative; right: 0px; top: 10;">
        <a href="./images/malka_small.jpg"><img src="./images/malka_small.jpg" height="200px"/></a></p>
        <a href="image2.jpg"><img src="" height="100px"/></a></p>
   <p class="fragment" data-fragment-index="4" style="position:absolute; left:40px; top:40px;">
     </div>
  <div class="content-aside">
   <p class="fragment fade-down" data-fragment-index="1">
    PhD in economics from the Paris School of Economics </p>
   <p class="fragment" data-fragment-index="2">
    Postdoc at ETH </p>
    <p class="fragment" data-fragment-index="3">
     Assistant professor in applied micro economics at HEC Liège </p>   <p class="fragment" data-fragment-index="4">
    Interested in <bcolor>public economics</bcolor> questions:
    <a href="https://cepr.org/active/publications/discussion_papers/dp.php?dpno=15415/">inequality</a> and
    <a href="https://payroll-tax-inequality-app.herokuapp.com/">taxation</a></p>


   <p class="fragment" data-fragment-index="4">
    Using the standard econometric toolbox + natural language processing + machine learning </p>
 </div>

 <a href="https://malkaguillot.github.io/"><i class="fas fa-globe" ></i></a>
 <a href="https://twitter.com/MalkaGuillot/"><i class="fab fa-twitter" ></i></a>
 <a href="https://www.linkedin.com/in/malka-guillot-408b5361/"><i class="fab fa-linkedin" ></i></a>


--

## Who are you? Results from pre-class survey
TODO

<div style="position:relative;  text-align: center;" >
<iframe width="600" height="371" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRGFhbIXPxREBXDPpZDy_P4rzWMDuSaReFumIyXnyg4V3JBVOboEYzV1GTq7Rf_--lMgHzSdIIxoP0H/pubchart?oid=230737814&amp;format=image"></iframe>
</div>


---

<!-- .slide: id="logistics"  -->
# Logistics
<html><div style='float:left'></div><hr color='#EB811B' size=1px width=796px></html>

--

## How does the class work?

- <!-- .element: class="fragment" -->
  <bcolor> Lectures</bcolor>: 3 hours / week  
  - 2 hour theory
  - 1 hour practice:
    - coding exercises
  - sometimes the frontier between theory and practice will be fuzzy.
- <!-- .element: class="fragment" -->
  <bcolor>Every week</bcolor>
  - Thursdays
    - Theory: 8:45-10:45 (with a 10 minute break)
    - Practice: 11:00-12:00
  - Where? N1a 220 (2/20) [Liège centre - Louvrex]
  - Dates: 10.02.; 17.02.; 24.02.; 03.03.; 10.03.; 17.03.; 24.03.; 31.04.; 28.04.; 05.05.; 12.05.; 19.05.

--

## Online Course Materials
- [lola]([Moodle](https://moodle-app2.let.ethz.ch/course/view.php?id=14461) ):
  - Course announcement and forum
  - Giving back homerwork
- <!-- .element: class="fragment" data-fragment-index="2" -->
   [Syllabus](https://docs.google.com/document/d/1eviJuOoWUjoonxS1LvQJi1kMbmkNUulJtZ31542w100)
-   <!-- .element: class="fragment" -->
  [Github folder](https://github.com/MalkIPP/big_data_policy_2020) or [Github page](https://malkipp.github.io/big_data_policy_2021/)
  - <!-- .element: class="fragment" -->
      <bcolor>Slides</bcolor>: in html, also available in PDF
      - relying on [RevealJS](https://revealjs.com/)
  -   <!-- .element: class="fragment" -->
      <bcolor>Coding sessions</bcolor>: in [Jupyter Notebook](https://jupyter.org/)
      - You can use [mybinder](https://mybinder.org/) in the beginning

--

## Evaluation Policy

- **Homeworks**: should be given back as [jupyter notebooks](https://jupyter.org/) in PDF format.
  - $4(hw) *10\textrm{ pts} + 2(hw) * 5 \textrm{ pts} -10 $ <bcolor>
      =40%</bcolor>
-  **Participation in class & presentations** <bcolor>=5% bonus</bcolor>:
- Course project $\rightarrow$

--

## Course Communication

- Course communication will be done through [lola's forum]()
- I will be available
  - During the breaks, after the class.

--

## Teaching Assistants

[Michel Coppée](https://www.uliege.be/cms/c_9054334/fr/repertoire?uid=u224042) (Michel.Coppee@uliege.be)

Can answer questions about lectures, notebooks, assignments, and projects

--

## How to reach me?

- **Personal question**: face-to-face interaction > emails
- **General interest question**: forum > email

<i class="fa fa-send" aria-hidden="true"></i>
[mguillot@uliege.be](mguillot@uliege.be)


<i class="fa fa-location-arrow" aria-hidden="true"></i>
Bât. N1 Economie (bureau 33a) <br>
rue Louvrex 14 <br>
4000 Liège <br>
Belgique


---

<!-- .slide: id="motivation"  -->
# Data management: what, for whom, why, how?
<html><div style='float:left'></div><hr color='#EB811B' size=1px width=796px></html>



--

## What? A tentative definition

DM concerns all process, tools, and techniques related to the management of data

With the objective of exploiting the data, we need the data to be
- consistent
- of high inequality
- (secured)

$\Rightarrow$ This class: from acquisition of data to data analysis

--

## For whom?

- For research
- For firms

Public targeted: any students using data for projects. For academics or non academics.

TODO: show some examples
**Question**: Do you have some ideas of what question you would want to use data for ?

---

<!-- .slide: id="motivation"  -->
# General motivation
<html><div style='float:left'></div><hr color='#EB811B' size=1px width=796px></html>



--

## Data management: what, why, how?


--

## Revolution in the use of data
- <bcolor> new datasets</bcolor> : administrative microdata, digitization of text archives, social media
- <bcolor> new methods</bcolor> : causal inference, natural language processing, machine learning

$\Rightarrow$ New avenues  in:
- research
- policy analysis
- business (costumer services)

[New possibilities: exciting!]() <!-- .element: class="fragment" -->

Notes:
We are seeing a revolution in research / policy analysis / business sector

I have my own field of specialization, but I expect that you come with your own intresest in economics / finance / management

$\rightarrow$ invest the tools learnt during the class to invent new visualization important for your field


--

## # of Wikipedia Pages, 2001-2020

<div class="r-stack"><img data-src="./images/wikipedia-pages.png" style="height: 500px;" ></div>

Source: [Wikimedia Statistics](https://stats.wikimedia.org/#/en.wikipedia.org/content/pages-to-date/normal|line|2001-01-01~2021-03-01|page_type~content|monthly). The running count of all pages created, excluding pages being redirects.

--

## What is big data?

<div class="r-stack"><img data-src="./images/big-data-illustration.jpeg" style="width: 400px;" ></div>

--

### Expert Survey (UC Berkeley, 2014)

<div class="r-stack"><img data-src="./images/bigdata-worldcould.png" style="width: 600px;" ></div>

Image by Jennifer Dutcher, source: https://datascience.berkeley.edu/what-is-big-data

--

### Conclusion

<div class="r-stack"><img data-src="./images/big-data-cartoon.jpeg" style="width: 600px;" ></div>

Source: [Ingeniero Dilbert](https://twitter.com/dilbert_ing/status/636499650560835584)

--

### What is big data?

- **Variety** of types/formats of data
  - Structured
  - Unstructured
- **Volume** of data
- **Velocity**: Speed of data flow/stream
- Unusual sources
  - Ready made vs. costummades

$\rightarrow$ Use programming and statistics to extract value


--

### Big data in the Social sciences

- From web applications and digitization of economic and political processes
- <bcolor> Volume </bcolor>: can be big, but usually smaller than in natural sciences
- <bcolor> Variety </bcolor> and <bcolor> variability</bcolor>: often important and challengin
  - Various resources
  - Data generation from 'the real world'
- But usually no streaming applications (<bcolor>velocity</bcolor> not that much of an issue)

--

### New tools and methods

- **Data collection**: API, Webscraping
- **Analysis**: text analysis, machine learning
  - Data can be tall (many observations) or **wide/fat** (many regressors)
  $\Rightarrow$ Machine learning helps to extract the relevant information

- **Visualization**: maps, social networks, web appeals

--

### Big data ecosystem

<div class="r-stack"><img data-src="./images/2020-Data-and-AI-Landscape-Preview-1.png" style="width: 800px;" ></div>

Source: ‘Big Data Landscape (2020)’ from  http://mattturck.com, [high definition image](http://mattturck.com/wp-content/uploads/2020/09/2020-Data-and-AI-Landscape-Matt-Turck-at-FirstMark-v1.pdf)


--

## What is machine learning?

More on this in the statistical learning theory lecture.

--

## Why is it useful to policy analysis?

--

## Empirical policy research (1)
- Standard causal inference framework
- <!-- .element: class="fragment" --> Relying on a <b> counterfactual </b>: what happens with and without a policy
- <!-- .element: class="fragment" -->
The <em>art of the counterfactual</em>  intertwine with applied econometrics

 <p><i class="fa fa-arrow-right" aria-hidden="true"></i>  many <bcolor>policy applications where causal inference is not central</bcolor>, or even necessary</p><!-- .element: class="fragment" -->

--

## (Toy) example
Policy maker facing a drought must decide whether to:

1. <p style="font-size: .9em"><!-- .element: class="fragment" data-fragment-index="1"--> Invest in a rain dance to increase the chance of rain<p>

  <p style="font-size: .8em"><!-- .element: class="fragment" data-fragment-index="2"--><bcolor>Causality</bcolor>: do rain dances cause rain?<p>

2. <p style="font-size: .9em"><!-- .element: class="fragment" data-fragment-index="3" --> Take an umbrella to work to avoid getting wet on the way home?<p>

  <p style="font-size: .8em"><!-- .element: class="fragment" --><bcolor>Prediction</bcolor>: is the chance of rain high enough to merit an umbrella?<p>

<p><cite><i class="fa fa-book fa-fw" aria-hidden="true"> </i> Kleinberg, J., Ludwig, J., Mullainathan, S. and Obermeyer, Z.,2015.  <a href=https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4869349/pdf/nihms776714.pdf>Prediction policy problems</a>. American Economic Review, 105(5), pp.491-95.</cite></p>


--

## Conclusion:
### <bcolor>Why relying on BD and ML appeals to policy analysis?</bcolor>

1. <!-- .element: class="fragment" --> Not all policy problems are causal inference problems, some require <b>prediction</b>
  <p><!-- .element: class="fragment" --><i class="fa fa-arrow-right" aria-hidden="true"></i> ML and BD <bcolor>supplement</bcolor> standard econometrics</p>
2. <!-- .element: class="fragment" --> Some data pose <b>new empirical challenges</b>
  <p><!-- .element: class="fragment" --><i class="fa fa-arrow-right" aria-hidden="true"></i> ML and BD <bcolor>complement</bcolor> standard econometrics</p>

--

## Learning objectives:

1. Technical skills
  - <div style="font-size:.8em"> Introduction data analysis and visualization in python: pandas, web-scraping, API, web-app </div>
  - <div style="font-size:.8em"> Programming skills necessary to train and assess the performance of the most popular machine learning algorithms</div>

<!-- .element: class="fragment" -->
2. Substantive knowledge
  - <div style="font-size:.8em">Statistical theory underlying common supervised and unsupervised machine learning algorithms.</div>
  - <div style="font-size:.8em">When and how to apply different types of machine learning algorithms to policy issues</div>

<!-- .element: class="fragment" -->

---

<!-- .slide: id="tools_resources" -->
# Tools and resources
<html><div style='float:left'></div><hr color='#EB811B' size=1px width=796px></html>

--

## Your programming background

<div style="position:relative;  text-align: center;" >
  <a href="https://app.sli.do/event/tevwuniu" target="_blank">
    <div style="position:absolute;  z-index:500;height:245px;width:100%;"></div>
    <iframe src="https://app.sli.do/event/tevwuniu/embed/polls/1bb3f5ad-829d-486c-8be3-17c642e0f2af" width="300" height="400"></iframe>
  </a>

  https://app.sli.do/event/tevwuniu
</div>

--


## Why Python?

<div class="r-stack"><img data-src="./images/python-search.png" style="height: 500px;" ></div>

--

## Why Python?

- General-purpose language
  - One of the core languages of scientific computing
- Elegant syntax
- Many useful libraries:
  - Data manipulation: [Pandas](https://pandas.pydata.org/)
  - Machine learning: [scikit-learn](http://scikit-learn.org/)
  - Statistics: [statsmodels](http://statsmodels.sourceforge.net/)
  - Natural Language Procession [nltk]()
- Also path dependency: the language I know the best


--

## Using Python

| <a href=https://www.anaconda.com/products/individual>Anaconda</a>| <a href=https://jupyter.org/>Jupyter notebook</a> | Spyder</a> |
|:------:|:---:|:-----:|
|<img data-src="./images/anaconda-logo.png"  style="height: 80px;" > | <img data-src="./images/jupyter-logo2.png" style="height: 80px" class="center"> | <img data-src="./images/spyder-logo.png" alt="" style="height: 80px">|
|a convenient all-in-one install |for homerwork|for longer code|

<bcolor> You are welcome to use R instead.</bcolor>


--

##  <i class="fa fa-arrow-right" aria-hidden="true"></i> Anaconda

<img data-src="./images/anaconda-navigator.png" style="width: 1800px;"  >

Spyder & Jupyter notebook are two development environments from the Anaconda set up.

Notes:
See downlowding instruction and small video

--

## Course materials are on [Github](https://github.com/MalkIPP/big_data_policy_2021)

- [Git](https://git-scm.com)
  - Git is a distributed version control system.
  - Dropbox + track changes, optimized for codes
- [GitHub](https://github.com/) (≠ Git)
  - = Online hosting platform that provides an array of services built on top of the Git system.
  - Makes life easier

>Github is also great for scientific research and for collaboration on code.

--

## Why Git and Github?

<img data-src="./images/phd-comics-doc.gif"  style="height: 550px; position:relative;     margin-left: auto;margin-right: auto;display: block" >

Also [git vs. Dropbox from a researcher's perspective](https://michaelstepner.com/blog/git-vs-dropbox/)


--

## How to interact with the materials?

1. **Simple** -> Just use the online GitHub interface to
   - Access the materials
   - Amend the students' presentation signing sheet
2. **Advanced**
   - Download [git](https://git-scm.com/downloads)
   - Create an account on [GitHub](https://github.com/)
   - Go through this [simple guide](https://rogerdudler.github.io/git-guide/)
   - In case it goes wrong: http://ohshitgit.com/

You can use [mybinder](https://mybinder.org/v2/gh/MalkIPP/big_data_policy_2021/main) to launch the notebooks from Github

--

## <i class="fa fa-book fa-fw" aria-hidden="true"></i>Main textbook references<i class="fa fa-book fa-fw" aria-hidden="true"></i>

  <div class="image-float">
    <p style="position: relative; left: 0px; top: 5;">
      <a href="./images/homl-python.jpeg"><img src="./images/homl-python.jpeg" width="100px"/></a></p>
      <a href="./images/homl-python.jpeg"><img src="./images/ISL.jpeg" width="100px"/></a></p>
    </div>

<div class="content-aside">
 <p>Geron,  <a href="https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/">Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow</a>
</p>
 <p> James, Witten, Hastie, and Tisbshirani (JWHT), <a href="https://www.statlearning.com/">Introduction to statistical learning with applications in R</a>
 </p>

</div>

--

## Other references

Gaillac and L’Hour, [ Machine Learning for Econometrics](https://drive.google.com/file/d/1L_iervUBKj3RsXHLEGOtAFlyHEHpmyT4/view).

---

<!-- .slide: id="course_outline"-->
# Course outline
<html><div style='float:left'></div><hr color='#EB811B' size=1px width=796px></html>


--

## 0. Theoretical context

- **W1 & W2**: Statistical learning theory


--

## 1. Tools
- **W1**:
  - Overview + tools
  - HW on the basics of python and jupyter notebook

- **W2**: Webscraping and API

- **W13**: Web-app application (dash)


--

## 2. Machine Learning
- **W3+5**: Unsupervised ML
- **W4+6**: Supervised ML
- **W7**: Advanced ML
- **W8+10**: Text as data
- **W9**: Advanced ML: Working with time series

--

## 3. Causal inference designs
- **W11**: Causal analysis framework
- **W12**: Synthetic control methods

---

<!-- .slide: id="hw"-->
# For next week
<html><div style='float:left'></div><hr color='#EB811B' size=1px width=796px></html>


--

## Python

- See installation guide on lola
- Install [Anaconda](https://www.anaconda.com/products/individual), try out to run python in a Jupyter notebook and spyder
- Basics of python's syntax: [Learn Python](https://www.learnpython.org/)
  - less `Classes and Objects` + `Modules and Packages`.
- Wait for next week's introduction by Michel !

--

## Troubleshooting

  - Use the [course forum]() to share & find answers
  - Let's try to make this a <bcolor>fun collaborative experience</bcolor> for everyone
