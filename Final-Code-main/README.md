# Modeling Website Fingerprinting in Open and Closed Worlds
### 💡Introduction
The goal of this project is to create machine learning models using Tor network packet flow data, to determine whether an instance is communicating with a monitored website or an unmonitored website, and to identify its destination if it is a monitored website.

### 🖥️ Closed-world scenario
In the closed-world experiments, the user can only access monitored(preivously-known) websites. <br/> 
The goal is to classify the 95 monitored websites. <br/> 
We used an SVM, a decision tree, and a random forest model.

### 🖥️ Open-world scenario
In the open-world experiments, the user to access any websites within the system. <br/> 
Data can be classified into two parts  <br/> 
* `monitored data` : the attacker is interested in
* `unmonitored data` : deemed irrelevant by the attacker <br/> 

monitored website instances are treated as positive samples, and unmonitored website instances are treated as negative samples.
<br/> 
#### 📌 `Binary Classification`
Determine whether the web traffic trace corresponds to a monitored website. To do this, we reassign the label '1' to all monitored website instances (positive samples) and assign the label '-1' to all unmonitored website instances (negative samples)

#### 📌 `Multi-Class Classification`
Classify 95 monitored website traces with unique labels against additional unmonitored websites. In the multi-class setting, we label the monitored website instances with {0, 1, 2, ..., 94} and the unmonitored website instances with the label '-1'.

We used a decision tree and a random forest model.

### 💡 How to RUN
You can download monitored and unmonitored data from the below google drive. <br/> 
[dataset] (https://drive.google.com/drive/folders/13sDplxKUNmntbYr6WhpqQARiBvH41Oum)
<br/> You can run the code in Colab. Please upload the downloaded data to Colab's file.

#### ‼️ You need to replace the path in this code with the absolute path of the files `mon_standard10.pkl` and `unmon_standard10_3000.pkl` on your drive ‼️

```
with open("/content/sample_data/mon_standard.pkl", "rb") as file: 
```
```
with open("/content/sample_data/unmon_standard10_3000.pkl", "rb") as file:
```
