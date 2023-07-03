# DOS Attack classification with Deep Learning
Welcome everyone,

I'm most attached to this project since it's the one that introduce me to the world of Machine learning. 

We conduct analysis and classification of 7 different internet attack using [CICDDOS2019](https://www.unb.ca/cic/datasets/ddos-2019.html) datasets and [Dos 2017](https://www.unb.ca/cic/datasets/dos-dataset.html) datasets.


## Data Overview:
| Datasets | Labels | Attributes|
| --| --| --|
|DDOS, DOS | ```Portmap``` , ```NetBIOS``` , ```LDAP``` , ```MSSQL``` , ```UDP``` , ```SYN``` , ```Benign``` |86 attributes|

Where Dos attacks need to conduct feature extraction through [CICFlowMeter](https://github.com/CanadianInstituteForCybersecurity/CICFlowMeter)

## Stage I: Baseline Training
Train CNN/RNN models direclt on DDOs/Dos attacks for baseline models:
![5](https://user-images.githubusercontent.com/97998419/223625271-567a2b0c-ff48-471b-aed8-9131839d6f91.png)
Results:
* ```Normalization:``` StandardScaler
* ```Attribute Used:``` 79
* ```DataSize:``` 17 GB
* ```Model Structure:``` Conv1d * 3
* ```Optimizer:``` RMRprop
* ```Loss function:``` Sparse Categorical Crossentropy
* ```Acc:``` 96.57%
* Confusion Matrix:
  
|Benign | LDAP | MSSQL | NetBIOS| Portmap | Syn| UDP|
| -- | --| --| --| --| --| --|
 |17354 |  0  |  0  |  49  |  9  |  89  |  03| 
   |  60 | 1767597  |  18600  |  296   | 0   | 125  |  1    |
   |  316  | 163203 | 5057501  | 263 |   0  |  117   |178796    |
   |  363  |  3  |  747| 3403276 |  0   | 81   | 7664    |
  |   334  |  0  |  746  |  172744| 2  |  201   | 401   |
 |  2319  |  0 |   4060  |  37  |  0 |3990594   | 641    |
  |  53  |  0 |  75080 |   228  |  0   | 40 |3427634  |


Stage II:
Transfer Learning DDos Model's on Dos attack to compare accuracy with baseline models
![6](https://user-images.githubusercontent.com/97998419/223625324-73e8ce11-68c8-437c-9c98-7fbd504819ab.png)

Stage III:
1. split Attacks in three groups and preprocessed by three agents into metadata (source information unkown for the rest of the training)
![7](https://user-images.githubusercontent.com/97998419/223625440-95b8ad99-0307-4156-95c2-573bd0c7a5d4.png)


2. Train universal models that can still classify attack from the metadata for each single attacks
![8](https://user-images.githubusercontent.com/97998419/223625529-2c74d096-116e-489f-a62f-a3781b07c6b8.png)
