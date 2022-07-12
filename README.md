# lightning-analysis
Lightning Non-performance Analysis on Reports

## Setup

### Linux environment

Python 3.5+ is required!

``` 
cd lightning-analysis
python3 -m pip install -r requirements.txt
jupyter notebook
```

### Windows environment

1. Go to [anconda products](https://www.anaconda.com/products/distribution) and download & install Anaconda Distribution.
2. During installation you must `Add Anaconda to my PATH environment variable`
4. Open Anaconda Navigator and launch Jupyter Notebook or via Anaconda prompt running `jupyter notebook`.


## Data

1. Download [Salesforce.zip](https://drive.google.com/drive/folders/1Ru1JEGT_cD0UiBXG7fNfHYnaa-ooJTES?usp=sharing) file from our shared point (Most recent version is recommended).
2. Unzip into `lightning-analysis/data/`


## Research questions


### Non-performing dashboards


### Non-performing reports

1. Active reports
1.1. What are the most frequently run reports?
1.2. How long has each report been running?
1.3. How long does it take to a page load these reports?
1.3.1. What types of errors are associated with longer duration reports according to the EFFECTIVE_PAGE_TIME?


| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | Report | REPORT_ID_DERIVED |


#### Performance
  
1. Problematic reports regarding performance
1.1. In which browsers are these reports running?
1.2. What region or locality do most of the executions come from?
1.3. What connection types are users using to access the reports?
1.4. Are these accesses being made through mobile devices?
1.5. What OS types are used to access the reports?
1.6. What are the trends for user actions?

| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | Report, LightningPerformance | REPORT_ID_DERIVED, CLIENT_GEO, CONNECTION_TYPE,  UI_EVENT_SOURCE, etc. |
| Datasets | `active_reports` |  includes all Report Object and Report logs columns |


#### PageView 

1. Problematic reports regarding page load time
1.2. How long the user spent on the page?
1.3. How long does it take to a page load these reports?
1.4. Which components the reports are running?
1.5. Which columns are being used by more than one report?
1.6. What kind of users are running these reports?


| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | LightningPageView | DURATION, EFFECTIVE_PAGE_TIME, PAGE_CONTEXT, PAGE_START_TIME, PAGE_URL, USER_TYPE etc. |
| Datasets | `active_reports` |  includes all Report Object and Report logs columns |


#### Report

1. Problematic reports regarding user run reports
1.1. Where is the database taking the longest to load?
1.2. Where is the application taking the longest to load?
1.3. In what contexts are these reports being run?
1.4. How long does it take to complete the requests?


| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | Report | REPORT_ID_DERIVED, DB_TOTAL_TIME, DB_CPU_TIME, CPU_TIME, RUNT_TIME etc. |
| Datasets | `active_reports` |  includes all Report Object and Report logs columns |

#### Errors

1. Problematic reports regarding errors
1.1. What is the trend for the errors?
1.1.1. Are the errors coming from specific pages?
1.1.2. What region do most of the errors come from?
1.2. Which components are related to the most common errors?


| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | Report, LightningError | PAGE_URL, PAGE_CONTEXT (component), USER_AGENT etc. |
| Datasets | `active_reports` |  includes all Report Object and Report logs columns |
