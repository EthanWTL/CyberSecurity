# CyberSecurity
analysis of Internet Connection Anomaly like DDos, Dos, brutal force

Stage I:
Train CNN/RNN/DNN models direclt on DDOs/Dos attacks for baseline models:
![5](https://user-images.githubusercontent.com/97998419/223625271-567a2b0c-ff48-471b-aed8-9131839d6f91.png)

Stage II:
Transfer Learning DDos Model's on Dos attack to compare accuracy with baseline models
![6](https://user-images.githubusercontent.com/97998419/223625324-73e8ce11-68c8-437c-9c98-7fbd504819ab.png)

Stage III:
1. split Attacks in three groups and preprocessed by three agents into metadata (source information unkown for the rest of the training)
![7](https://user-images.githubusercontent.com/97998419/223625440-95b8ad99-0307-4156-95c2-573bd0c7a5d4.png)


2. Train universal models that can still classify attack from the metadata for each single attacks
![8](https://user-images.githubusercontent.com/97998419/223625529-2c74d096-116e-489f-a62f-a3781b07c6b8.png)
