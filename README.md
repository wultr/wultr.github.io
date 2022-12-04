<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><img src="https://images.unsplash.com/photo-1541600383005-565c949cf777?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80" alt="Drawing" style="width: 700px;"/></p>
<p></p>
<p><h1 style="font-size:36px;">Analyzing Open Powerlifting Data</h1></p>
<p><h4>
Walter Pezquera</h4></p>
<p><hr></p>
<p><h1>Introduction</h1>

<body><p>
Powerlifting is a strength-based sport where athletes compete by performing three compound movements: squat, bench press, and deadlift. Powerlifting tournaments are hosted at different levels (locally, state, regionally, nationally, and internationally) and split into different divisions based on the athletes age, sex, and weight.
<p>
In this project we look at data for powerlifting tournaments. We will look specifically at tournaments hosted by the Internal Powerlifting Federation (IPF) as they are one of the largest organizations resposible for hosting quality, high-standard competitions internationally. With this data, we can look at current demographics of the sport such as participation amongst age groups, regions and strength levels. We can find trends in the sport's popularity geographically or in different groups. We can also attempt to project the strength of an athlete based off attributes like their height, weight, age, and sex. 
<p>
As with any data analysis process, we start by obtaining the data from an open data source. Once the data is obtained, we will filter to look only at data from the IPF or their affilates. This is to ensure data integrity and accuracy of the analysis. We will explore the current standings and spread of tournament data with respect to location, athlete information, or equipment. Afterwards we will attempt to predict athletes strength using regression algorithms. 
  <hr>
<center><h1>Data Collection</center>
<body><p>
We use Python3 and libraries such as pandas, numpy, matplotlib and scikit-learn to perform our analysis.
</body>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Necessary libraries and imports to complete this tutorial</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="k">import</span> <span class="n">model_selection</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="k">import</span> <span class="n">linear_model</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="k">import</span> <span class="n">preprocessing</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="k">import</span> <span class="n">LabelEncoder</span>
<span class="kn">import</span> <span class="nn">statsmodels.formula.api</span> <span class="k">as</span> <span class="nn">smf</span>
<span class="kn">import</span> <span class="nn">warnings</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<body>
The dataset we will be using comes from the Openpowerlifting Data Service. They are a community of powerlifer who scrape the internet for tournament information and append it to their database. They provide a great service to the powerlifting community by creating a permenant archive of the world's powerlifting data and providing it in convenient formats. 
<h2>Acquiring the Data</h2>
<p>
The data can be downloaded from the OpenPowerlifting site <a href="https://openpowerlifting.gitlab.io/opl-csv/">here</a>. On the site, we can follow the sidebar to "Bulk CSV Downloads" and select which dataset we want to use. There is a complete dataset containing information from all tournaments and another which only contains information about tournaments hosted by the IPF or its affiliates. For our analysis, we will use the dataset with only IPF and affiliate information. 
