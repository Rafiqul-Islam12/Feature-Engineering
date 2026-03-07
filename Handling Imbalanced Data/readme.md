# ***Imbalanced Datasets***

***Imbalanced Data তখন ঘটে যখন একটি dataset-এ একটি class-এর sample সংখ্যা অন্য class-গুলোর তুলনায় অনেক বেশি হয়। অর্থাৎ dataset-এর class distribution সমান থাকে না।***    
***In this situation, machine learning models usually majority class কে বেশি favour করে এবং minority class ঠিকভাবে predict করতে পারে না।***   

<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img1.png" width="500"> <img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img2.png" width="480">   

- ***এই ধরনের সমস্যা real-world applications এ অনেক common, যেমন:   
  Fraud Detection   
  Medical Diagnosis   
  Disease Prediction   
  Risk Prediction   
  কারণ এসব ক্ষেত্রে important cases সাধারণত minority class এ থাকে।***

---
## ***Problems Caused by Imbalanced Data***  
1️⃣ ***`Model Bias Toward Majority Class`***  
***Machine Learning models সাধারণত majority class এর দিকে bias হয়ে যায় এবং সেটাকেই বেশি predict করতে থাকে।***      

2️⃣ ***`Minority Class Ignored`***   
***Minority class এর instances অনেক সময় noise বা insignificant pattern হিসেবে ধরা হয়।   
ফলে training এর সময় model এগুলোকে overlook করতে পারে।***   

3️⃣ ***`Misleading Accuracy` 
Imbalanced dataset এ accuracy misleading হতে পারে।***  
***Example:   
Total samples = 1000  
Majority class = 900  
Minority class = 100   
যদি model সবকিছু majority class predict করে, তাহলে accuracy হবে = 90%   
কিন্তু বাস্তবে model minority class detect করতে পারছে না।***   

4️⃣ ***`Skewed Decision Boundary`   
Imbalanced dataset এর কারণে model এমন decision boundary তৈরি করে যা majority class কে বেশি favour করে।   
ফলে: Minority class misclassify হয়, Model এর generalization ability কমে যায়।***   

***Imbalanced data machine learning এ একটি গুরুত্বপূর্ণ সমস্যা।   
এটা ঠিকভাবে handle না করলে model majority class বেশি predict করবে এবং minority class detect করতে ব্যর্থ হবে।   
Example:   
Fraud detection এ fraud detect না হওয়া    
Medical diagnosis এ রোগী detect না হওয়া   
Risk prediction এ high-risk case miss করা***    

---
# ***Techniques to Handle Imbalanced Data***
- [***Undersampling***](https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/1.%20Undersampling.ipynb)  
- [***Oversampling***](https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/2.%20Oversampling.ipynb)
- [***SMOTE***](https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/3.%20SMOTE.ipynb)   
  
---
## ***Undersampling and Oversampling***
***`Undersampling` → Majority class এর data reduce করা***   
***`Oversampling` → Minority class এর data increase করা***
<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img3.png" width="900">  

## ***`1️⃣ Undersampling`***  
***ধরা যাক dataset এ:***   
- ***Non-Addicted = 900***
- ***Addicted = 100***

***Undersampling করার পরে:***  
- ***Non-Addicted = 100***
- ***Addicted = 100***

<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img2.png" width="490"> <img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img4.png" width="500">  
<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img5.png" width="490"> <img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img6.png" width="500">  

***`Types`***     
***1. `Random Undersampling`    
Simple technique, Faster.    
Majority class থেকে randomly কিছু samples remove করা হয়।***    

***2. Tomek Links    
Tomek Link হলো two classes এর খুব কাছাকাছি data points।   
এই ধরনের pair remove করলে classes এর boundary clean হয়।    
Benefit: Noise reduce করে, Class separation improve করে।***    

***3. NearMiss    
NearMiss majority class থেকে এমন samples রাখে যেগুলো minority class এর কাছে থাকে।    
Model যেন difficult cases থেকে learn করে।***     

***`Disadvantages of Undersampling`***    
***Important information / Useful data loss হতে পারে  
Small dataset হলে performance degrade হতে পারে   
Majority class এর pattern পুরোটা learn করা সম্ভব নাও হতে পারে***   

---
## ***`2️⃣ Oversampling`***     
***ধরা যাক dataset এ:***   
- ***Non-Addicted = 900***
- ***Addicted = 100***

***Oversampling করার পরে:***  
- ***Non-Addicted = 900***
- ***Addicted = 900***

<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img2.png" width="490"> <img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img4.png" width="500">  
<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img7.png" width="490"> <img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img8.png" width="500">   

***`Types`***   
***1. `Random Oversampling`  
এটা সবচেয়ে simple technique।   
Minority class এর samples randomly duplicate করা হয়।***  
   
***2. SMOTE***   

---
## ***`3️⃣ SMOTE (Synthetic Minority Over-sampling Technique)`***   
***একটি popular oversampling technique.   
Normal oversampling এ minority class data duplicate করা হয়, কিন্তু SMOTE duplicate না করে নতুন synthetic samples generate করে।   
এর ফলে dataset balance হয় এবং overfitting এর probability কমে যায়।***    

***ধরা যাক dataset এ:***   
- ***Non-Addicted = 900***
- ***Addicted = 100***

***SMOTE করার পরে:***  
- ***Non-Addicted = 900***
- ***Addicted = 900***    
  
<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img9.png" width="900">   

#### ***`SMOTE Algorithm`***  
***`Step 1`: Train KNN on Minority Class   
প্রথমে শুধুমাত্র minority class observations নিয়ে একটি KNN model ব্যবহার করা হয়।   
Usually: k = 5 nearest neighbors   
প্রতিটি minority data point এর সবচেয়ে কাছের 5টি minority data point identify করা হয়।***    

***`Step 2`: Randomly Select Minority Samples   
Minority class থেকে কিছু samples randomly select করা হয়।***    

***`Step 3`: Randomly Select One Neighbor    
KNN থেকে পাওয়া neighbors এর মধ্যে একটি neighbor randomly select করা হয়।***    
   
***`Step 4`: Generate Random Number   
0 এবং 1 এর মধ্যে একটি random number generate করা হয়।***   

***`Step 5`: Create Synthetic Sample   
নতুন sample তৈরি করা হয় original sample এবং neighbor এর মধ্যে interpolation করে।    
Formula:    
Synthetic sample = original sample + factor × (neighbor − original sample)***    

***`Example`***  
***Let,  
Original sample A = (2,3)    
Neighbor B = (4,5)    
factor = 0.5***   

***Synthetic sample:   
= A + 0.5 × (B − A)   
= (2,3) + 0.5 × (2,2)   
= (2,3) + (1,1)    
= (3,4)***    

***New Synthetic point = (3,4)***    

<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img2.png" width="490"> <img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img4.png" width="500">  
<img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img10.png" width="490"> <img src="https://github.com/Rafiqul-Islam12/Feature-Engineering/blob/main/Handling%20Imbalanced%20Data/images/img11.png" width="500">       

---
# ***Resources***
- [***Imbalanced Data in Machine Learning (CampusX)***](https://www.youtube.com/watch?v=yh2AKoJCV3k&t=1744s)  
- [***Handling Imbalanced Data***](https://medium.com/@dakshrathi/handling-imbalanced-data-key-techniques-for-better-machine-learning-6e33b466f8b7)

---
## ***Author***    
***Md. Rafiqul Islam   
CSE, CoU***  






