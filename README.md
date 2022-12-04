# wultr.github.io
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
&lt;/&gt;</p>
<body><p>
Powerlifting is a strength-based sport where athletes compete by performing three compound movements: squat, bench press, and deadlift. Powerlifting tournaments are hosted at different levels (locally, state, regionally, nationally, and internationally) and split into different divisions based on the athletes age, sex, and weight.
<p>
In this project we look at data regarding open powerlifting tournaments. We will look specifically at tournaments hosted by the Internal Powerlifting Federation (IPF) as they are one of the largest organizations resposible for hosting quality, high-standard competitions internationally. With this data, we can look at current demographics of the sport such as participation amongst age groups, regions and strength levels. We can find trends in the sport's popularity geographically or in different groups. We can also attempt to project the strength of an athlete based off attributes like their height, weight, age, and sex. 
<p>
As with any data analysis process, we start by obtaining the data from an open data source. Once the data is obtained, we will filter to look only at data from the IPF or their affilates. This is to ensure data integrity and accuracy of the analysis. We will explore the current standings and spread of tournament data with respect to location, athlete information, or equipment. Afterwards we will attempt to predict athletes strength using regression algorithms. 
  <hr>
<center><h1>Getting Started with the Data</h1></center>
<body><p>
