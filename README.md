# Data Science Project | The influence of Donald J Trump through tweeter on public opinion in the years 2009-2021

## Phase 1 - Project introduction

**Submitted by:**

* Matan Roginsky
* Ron Hugi

ABOUT

**Research question** - INSERT

**Features** – INSERT:

* CVE ID (CVE-Year-ID)

* Vulnerability Type (Types of vulnerabilities such as Bypass, DOS, XSS, etc.)

* Publish Date (Date)

* Update Date (Date)

* Score (Severity of vulnerability – 1.0-10.0)

* Gained Access Level (None \ Partial \ Complete)

* Access (Local \ Remote)

* Complexity (Low \ Medium \ High)

* Authentication (Required \ Not required)

* Confidentiality (None \ Partial \ Complete)

* Integrity (None \ Partial \ Complete)

* Availability (None \ Partial \ Complete)

**Instances** –174,954 rows, INSERT.

**Data sources** –

INSERT

**Data mining methods** – Crawling and scraping from the donald trump archive.

**Machine learning model** - Our Machine learning model is INSERT.

**Validation methods** – Our validation model is R2.


## Phase 2 - Scraping
Inside **crawling()** function we are:
* INSERT

## Phase 3 - Data Manipulation - INSERT

* **function load_dataframe** - will load our csv file into a dataframe.
* **function remove_unnecessary_data** - will remove a column that contain only None value, will remove rows with the CVE Score of 0, the removal is necessary since that CVE Score 0 indicates that the row is not actually a vulnerability, but more of a informational view of a product, will remove the vulnerabilities that is not in the last decade, since our project is  concerned with the last decade only, will remove duplicate rows and will keep the first one.
* **function replace_missing_data** - will replace missing values such as '???' and NaN with the 0 value, we kept the rows with null values on our dataframe since a row could have a null values on a feature of a vulnerability but the key value of a vulnerability such as the CVE score was not null.
* **function convert_string_to_int** - will convert each string value to an int value based on the diffrent columns, this function is mostly necessary for the machine learning phase. the values were converted mostly based on unique values and specific date was converted to a year since the month and day was not important for our research question 

## Phase 4 - Analyzing the data
### 1. INSERT

**With the help of these Pie Charts, we may see that:**

### 2.

### 3. 

### 4. 

### 5. 

**Temporal**: represents the characteristics of a vulnerability that change over time but not among user environments.
**Environmental**: represents the characteristics of a vulnerability that are relevant and unique to a particular user's environment.
The purpose of the CVSS base group is to define and communicate the fundamental characteristics of a vulnerability. This objective approach to characterizing vulnerabilities provides users with a clear and intuitive representation of a vulnerability. Users can then invoke the temporal and environmental groups to provide contextual information that more accurately reflects the risk to their unique environment. This allows them to make more informed decisions when trying to mitigate risks posed by the vulnerabilities.

## Phase 5 - Machine Learning
### During this phase we created 5 functions:

* **function load_dataset** - will split the dataframe into a new dataframe {x} which will contain the features vactor and a Series {y} which will contain our target values.
* **function split_to_train_and_test** - will will split the 'X' dataframe into 'X_train' and 'X_test', where the ratio of the test out of 'X' is 0.3 and the random state is 41. The 'y' series is splitted in a corresponding way into 'y_train' and 'y_test'.
* **function train_model** - will train a model, which will predict the CVE Score of the given vulnerabilities using linear regression.
* **function predict** - will predict the CVE Score for each of the vulnerabilities in the test set using the trained model. 
* **function evaluate_performance** - will evaluate the performance of the model on the test set using R2.
