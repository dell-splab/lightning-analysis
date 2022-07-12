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

| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | Report | REPORT_ID_DERIVED |

| | NB | Owner | Splunk | Status |
|-|-|-|-|-|
|1. | Active reports | Jeferson | :frog: | `DONE` |
|1.1. | What are the most frequently run reports? | Jeferson || `DONE` |
|1.2. | How long has each report been running? | Jeferson || `DONE`|
|1.3. | How long does it take to a page load these reports?| Izaquiel || `REVIEW`|
|1.3.1. | What types of errors are associated with longer duration reports according to the EFFECTIVE_PAGE_TIME?| Izaquiel ||`STARTED`|

#### Performance
  
| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | Report, LightningPerformance | REPORT_ID_DERIVED, CLIENT_GEO, CONNECTION_TYPE,  UI_EVENT_SOURCE, etc. |
| Datasets | `active_reports` |  includes all Report Object and Report logs columns |
 
| | NB | Owner | Splunk | Status |
|-|-|-|-|-|
|1. | Problematic reports regarding performance | Maciel | | `TODO` |
|1.1. | In which browsers are these reports running? | | | `TODO` |
|1.2. | What region or locality do most of the executions come from? | Debora |  | `TODO`|
|1.3. | What connection types are users using to access the reports? | |  |`TODO`|
|1.4. | Are these accesses being made through mobile devices? | |  |`TODO`|
|1.5. | What OS types are used to access the reports? | |  |`TODO`|
|1.6. | What are the trends for user actions? | | |`TODO`|


#### PageView 

| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | LightningPageView | DURATION, EFFECTIVE_PAGE_TIME, PAGE_CONTEXT, PAGE_START_TIME, PAGE_URL, USER_TYPE etc. |
| Datasets | `active_reports` |  includes all Report Object and Report logs columns |

| | NB | Owner | Splunk | Status |
|-|-|-|-|-|
|1. | Problematic reports regarding page load time| Jeferson | |`DONE`|
|1.2. | How long the user spent on the page?| | |`TODO`|
|1.3. | How long does it take to a page load these reports?| |  |`REDO`|
|1.4. | Which components the reports are running?| ||`DONE`|
|1.5. | Which columns are being used by more than one report?| ||`DONE`|
|1.6. | What kind of users are running these reports?| Klebler | |`STARTED`|

#### Report

| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.| 
| ELF (logs) | Report | REPORT_ID_DERIVED, DB_TOTAL_TIME, DB_CPU_TIME, CPU_TIME, RUNT_TIME etc. |
| Datasets | `active_reports` |  includes all Report Object and Report logs columns |

| | NB | Owner | Splunk | Status |
|-|-|-|-|-|
|1. | Problematic reports regarding user run reports | Jeferson | | `TODO`|
|1.1. | Where is the database taking the longest to load?| | | `TODO`|
|1.2. | Where is the application taking the longest to load?| | | `TODO`|
|1.3. | In what contexts are these reports being run?| | |`TODO`|
|1.4. | How long does it take to complete the requests?| | |`TODO`|

#### Errors

| Data source | Tables | Columns |
|:-|:-:|:-:|
| Objects (workbench)| Report |  Id, Name, LastRunDate etc.|
| ELF (logs) | Report, LightningError | PAGE_URL, PAGE_CONTEXT (component), USER_AGENT etc. |
| Datasets | `active_reports` |  includes all Report Object and Report logs columns |

| | NB | Owner | Splunk | Status |
|-|-|-|-|-|
| 1. | Problematic reports regarding errors| Gabriela | | `TODO`|
| 1.1. | What is the trend for the errors? | ||`TODO`|
| 1.1.1. | Are the errors coming from specific pages?| ||`TODO` |
| 1.1.2. | What region do most of the errors come from?| ||`TODO` |
| 1.2. | Which components are related to the most common errors? | Kleber | |`DONE`|

