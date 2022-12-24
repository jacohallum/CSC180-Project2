# CSC180-Project2

Software  to  detect  network  intrusions  protects  a  computer  network  from  unauthorized  users,  including  
perhaps insiders.  This project aims to build an AI-based Network Intrusion Detection System (IDS), 
a  predictive  model  distinguishing  between  bad  connections,  called  intrusions  or  attacks,  and  good 
normal connections. 
 
 
 
Model this problem as a BINARY classification problem. Use the following models to detect attack 
connections (intrusions).  Compare the recall, precision and F1-score of the following models. PLOT the 
confusion matrix for each model.    
• Fully-Connected Neural Networks  
• Convolutional Neural Networks (CNN)  

Download link:   
https://drive.google.com/open?id=1FKyIqsKP4NBOTKRRuVbJjEFxTTCwzlHy 
 
You can also find the complete data and the data description here (we use the 10% subset in this project) 
http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html   
 
This database contains a wide variety of intrusions simulated in a military network environment.  
 
• A  connection  is  a  sequence  of  TCP  packets  starting  and  ending  at  some  well-defined  times,  
between  which  data  flows  to  and  from  a  source  IP  address  to  a  target  IP  address  under  some  
well-defined protocol.   
• Each connection is labeled as either normal, or as one specific attack type.  
• The datasets contain a total of 22 attack types, which are as follows: 
back,buffer_overflow,ftp_write,guess_passwd,imap,ipsweep,land,loadmodule,multihop,neptune
,nmap,normal,perl,phf,pod,portsweep,rootkit,satan,smurf,spy,teardrop,warezclient,warezmaster. 
 
• Type of each feature in the dataset is as follows (see Appendix A for details): 
duration: continuous. 
protocol_type: symbolic. 
service: symbolic. 
flag: symbolic. 
src_bytes: continuous. 
dst_bytes: continuous. 
land: symbolic. 
wrong_fragment: continuous. 
urgent: continuous. 
hot: continuous. 
num_failed_logins: continuous. 
logged_in: symbolic. 
num_compromised: continuous. 
root_shell: continuous. 
su_attempted: continuous. 
num_root: continuous. 
num_file_creations: continuous. 
num_shells: continuous. 
num_access_files: continuous. 
num_outbound_cmds: continuous. 
is_host_login: symbolic. 
is_guest_login: symbolic. 
count: continuous. 
srv_count: continuous. 
serror_rate: continuous. 
srv_serror_rate: continuous. 
rerror_rate: continuous. 
srv_rerror_rate: continuous. 
same_srv_rate: continuous. 
diff_srv_rate: continuous. 
srv_diff_host_rate: continuous. 
dst_host_count: continuous. 
dst_host_srv_count: continuous. 
dst_host_same_srv_rate: continuous. 
dst_host_diff_srv_rate: continuous. 
dst_host_same_src_port_rate: continuous. 
dst_host_srv_diff_host_rate: continuous. 
dst_host_serror_rate: continuous. 
dst_host_srv_serror_rate: continuous. 
dst_host_rerror_rate: continuous. 
dst_host_srv_rerror_rate: continuous 
 
3.  Data Preprocessing 
 
For data preprocessing, you first need encode good connections as “0” and attacks as “1”.   To achieve 
this, you have two options: 
 
(1) Label encoding  
 
https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html 
 
(2) Write your own Python encoding function and applying that function to the label column.  Check 
the map() function discussed in this tutorial: 
 
https://chrisalbon.com/code/python/data_wrangling/pandas_apply_operations_to_dataframes/ 
 
 
 
4.  Requirements 
 
• Split data to training and test.  Use training data to train your models and evaluate the model 
quality using test data 
• Drop all the redundant records. This data set has a big number of redundant records. 
Redundant records in the train set will cause learning algorithms to be biased towards the 
more frequent records.  
• Removing all records with missing values.     
• Encode categorical features and normalize numeric features.  
• Some column(s) may have missing values if you normalize raw values by dividing them 
using column_max – column_min.   Why?   Remove those columns before model training.  
• You must use EarlyStopping when training neural networks using Tensorflow.  
• Tuning the following hyperparameters when training neural networks using Tensorflow to 
record how they affect performance in your report.  Save all the models you have tried as a 
proof in your notebook and tabulate your findings in your report.  
• Activation: relu, sigmoid, tanh 
• Layers and neuron counts 
• Optimizer: adam and sgd 
• Kernel number and kernel size (for CNN only)
