---
title: "Copper Price Prediction"
date: 2025-07-23
---

## Introduction
The goal of this project is to develop a machine learning model that predicts the daily closing price of U.S. copper futures (COMEX) using only data available before the market opens. By leveraging historical price data from COMEX, SHFE, and LME, the model aims to support informed decision-making for traders, analysts, and researchers while maintaining realistic forecasting conditions without data leakage.

## Data Cleaning
In the data cleaning stage, we standardized copper futures data from COMEX, SHFE, and LME by converting column names to lowercase, setting datetime indices, and sorting rows chronologically. Missing values were forward-filled when appropriate. SHFE prices were converted from CNY per ton to USD per pound using daily exchange rates, while LME prices were similarly converted from USD per ton. This processing ensured consistency across datasets for modeling and analysis.

## Exploratory Data Analysis

{{< figure src="lme.png" alt="LME grpah" caption=" " class="center" width="100%" >}}

{{< figure src="comex.png" alt="COMEX grpah" caption=" " class="center" width="100%" >}}

{{< figure src="shfe.png" alt="SHFE grpah" caption=" " class="center" width="100%" >}}

<iframe src="_index.md" width="100%" height="600" style="border:none;"></iframe>


<style>

</style>

<div id="fig_el70308eed2b038-6fd3-4540-88ed-8895b4e878ae5864511648"></div>
<script>
function mpld3_load_lib(url, callback){
  var s = document.createElement('script');
  s.src = url;
  s.async = true;
  s.onreadystatechange = s.onload = callback;
  s.onerror = function(){console.warn("failed to load library " + url);};
  document.getElementsByTagName("head")[0].appendChild(s);
}

if(typeof(mpld3) !== "undefined" && mpld3._mpld3IsLoaded){
   // already loaded: just create the figure
   !function(mpld3){
       
       mpld3.draw_figure("fig_el70308eed2b038-6fd3-4540-88ed-8895b4e878ae5864511648", {"width": 640.0, "height": 480.0, "axes": [], "data": {}, "id": "el70308eed2b038-6fd3-4540-88ed-8895b4e878ae", "plugins": [{"type": "reset"}, {"type": "zoom", "button": true, "enabled": false}, {"type": "boxzoom", "button": true, "enabled": false}]});
   }(mpld3);
}else if(typeof define === "function" && define.amd){
   // require.js is available: use it to load d3/mpld3
   require.config({paths: {d3: "https://d3js.org/d3.v5"}});
   require(["d3"], function(d3){
      window.d3 = d3;
      mpld3_load_lib("https://mpld3.github.io/js/mpld3.v0.5.11.js", function(){
         
         mpld3.draw_figure("fig_el70308eed2b038-6fd3-4540-88ed-8895b4e878ae5864511648", {"width": 640.0, "height": 480.0, "axes": [], "data": {}, "id": "el70308eed2b038-6fd3-4540-88ed-8895b4e878ae", "plugins": [{"type": "reset"}, {"type": "zoom", "button": true, "enabled": false}, {"type": "boxzoom", "button": true, "enabled": false}]});
      });
    });
}else{
    // require.js not available: dynamically load d3 & mpld3
    mpld3_load_lib("https://d3js.org/d3.v5.js", function(){
         mpld3_load_lib("https://mpld3.github.io/js/mpld3.v0.5.11.js", function(){
                 
                 mpld3.draw_figure("fig_el70308eed2b038-6fd3-4540-88ed-8895b4e878ae5864511648", {"width": 640.0, "height": 480.0, "axes": [], "data": {}, "id": "el70308eed2b038-6fd3-4540-88ed-8895b4e878ae", "plugins": [{"type": "reset"}, {"type": "zoom", "button": true, "enabled": false}, {"type": "boxzoom", "button": true, "enabled": false}]});
            })
         });
}
</script>
