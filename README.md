This artifact for our companion paper “View-Centric Performance Optimization for
Database-Backed Web Applications (#273)” includes both the Panorama framework we developed and some raw data produced by our user study. 

In this artifact, we deploy Panorama in two forms, a Rubymine IDE plugin and a command line tool. In both forms, Panorama provides a view-centric and database-aware development environment for web developers through its two key components 1) Panorama profiler that helps developers understand the data-processing costs of HTML tags on a web page, 2) Panorama optimizer that helps developers identify optimizing opportunities and carry out code refactoring to improve the performance of a web page.  

Also we provide code and data used to evaluate Panorama in the paper: 1) the source code of 12 open-source applications used as benchmarks in our paper; 2) synthesized workload for each of these 12 applications; 3) the questionnaires and results of our user study. Detailed instructions to reproduce our experiments are also included.

### Reproduce experiments in Section VII.
* RQ1: how many opportunities does Panorama identify?
	```
	 $ cd /home/panorama-static-analyzer/controller_model_analysis/
	 $ ./run_RQ1.sh
	 ```
	The detected optimized opportunities will be generated and found in folder ```/home/panorama-static-analyzer/controller_model_analysis/opportunities```.
	The generated patches can be found ```/home/panorama-static-analyzer/controller_model_analysis/patches```

* RQ2: how much performance benefits?
	 ```
	 cd /home/panorama-static-analyzer/controller_model_analysis/
	 ./run_RQ2.sh
	 ```
	 The results are genearted from applications' running logs including end to end time and server time, which are stored under   ```/home/panorama-static-analyzer/controller_model_analysis/RQ2``` in both ```eoe``` and ```server```.


* RQ3: are alternate view designs worthwhile?<br/>
  * Questionnaire can be found [here](https://uchicago.co1.qualtrics.com/jfe/preview/SV_3HNaVHXVyhsdDZr?Q_SurveyVersionID=&Q_CHL=preview).<br/>
  * The raw-data of answers from participants can be found [here](https://docs.google.com/spreadsheets/d/1EAq7ZhROnu2BCQkXYpV9XcrYSkna5FVxy2-WgOg5r2M/edit?usp=sharing), which are all de-identified. 

* RQ4: how accurate is Panorama profiler?
	 ```
	 $ cd /home/panorama-static-analyzer/controller_model_analysis/
	 $ ./run_RQ4.sh
	 ```
	 The complexity of tags will be printed out. And the end-to-end time for each design will be printed out, which comes from our previous running logs. 


