# BloodEagle---AlgoVerse

<div align="center">
    <h1>AgriVerse : AI-POWERED SMART FARMING ASSISTANT Integrated with IOT</h1>
</div>



!


## Overview

Smart Farming Assistant is an innovative solution that uses advanced technology to help farmers improve productivity and make better decisions. The platform features a Smart Crop Recommendation system powered by machine learning to suggest optimal crops based on soil nutrients, climate, and historical data. It also includes a Plant Disease Identification tool using convolutional neural networks (CNNs) to accurately diagnose plant diseases from uploaded images, enabling timely intervention. Additional features such as real-time Weather Forecasts, tailored Fertilizer Recommendations based on soil quality and crop requirements, and a Smart Farming Guide for crop management further enhance its value. With a user-friendly web app, farmers can easily access these insights and tools to improve farming practices.

## IOT Overview
We developed an IoT-enabled device that integrates into the soil and continuously monitors essential soil and climate parameters such as Nitrogen, Phosphorus, Potassium, pH, temperature, humidity, and rainfall.

The collected data is sent to a cloud server, where it is processed and fed into a Machine Learning model. The ML model analyzes the real-time soil-climate conditions and provides personalized crop recommendations to the farmer, ensuring maximum yield and sustainability.

Farmers can access insights through a mobile/web app or SMS alerts, which display:

Soil health status

Suitable crop suggestions

This solution empowers farmers with data-driven decisions, reduces crop failure risks, and promotes sustainable agriculture practices.



## Features

- [x] **Smart Crop Recommendation**: Leverages machine learning to suggest the most suitable crops based on soil nutrients, climate, and historical data.
- [x] **Plant Disease Identification**: Uses convolutional neural networks (CNNs) to accurately detect and classify plant diseases from uploaded images, allowing for timely interventions.
- [x] **User-Friendly Interface**: Features an intuitive platform for farmers to easily input data and receive personalized crop, disease, and fertilizer recommendations.
- [x] **IOT**: Features an intuitive platform for farmers to easily input data and receive personalized crop, disease, and fertilizer recommendations.



## Datasets

The **Smart Farming Assistant** project provides three key datasets: the **Crop Recommendation Dataset** (2200 rows) includes soil and environmental factors such as nitrogen, phosphorous, temperature, humidity, and pH to predict the most suitable crops; the **Plant Disease Identification Dataset** contains 70,295 training and 17,572 validation images covering 38 diseases across 14 crops like Apple, Tomato, and Grape, used to train CNN models for disease detection; and the **Fertilizer Recommendation Dataset** offers data on soil quality and crop needs to provide tailored fertilizer suggestions.

# 📌 Crop Recommendation Model

The **Crop Recommendation Model** utilizes machine learning algorithms to suggest the most suitable crops for farmers based on environmental and soil factors. By analyzing data such as soil nutrients, temperature, humidity, pH, and rainfall, the model provides tailored crop recommendations to ensure optimal growth and productivity. The model uses seven classification algorithms, with **Random Forest** achieving the highest accuracy of 99.55%. This helps farmers make informed decisions on crop selection, ensuring better yields and efficient farming practices.

## Dataset

This dataset consists of **2200 rows** in total.
**Each row has 8 columns representing Nitrogen, Phosphorous, Potassium, Temperature, Humidity, PH, Rainfall and Label**
NPK(Nitrogen, Phosphorous and Potassium) values represent the NPK values in the soil. Temperature, humidity and rainfall are the average values of the sorroundings environment respectively. PH is the PH value present in the soil. **The Label column tells us the type of crop that's best suited to grow based on these conditions.
Label is the value we will be predicting**


## Model Architecture
 
For the Crop Recommendation Model, seven classification algorithms were utilized to predict suitable crop recommendations. These algorithms include:

- Decision Tree
- Gaussian Naive Bayes
- Support Vector Machine (SVM)
- Logistic Regression
- Random Forest (achieved the best accuracy)
- XGBoost
- KNN
  
Each algorithm was trained on a dataset comprising various factors such as soil nutrients, climate conditions, and historical data to provide accurate crop recommendations to farmers.

## Integration

These two models are integrated into the Smart Crop Recommendation System with Plant Disease Identification. This system provides farmers with comprehensive support, offering both crop recommendations based on various factors and precise identification of crop diseases through image analysis. By combining these models, the system enables farmers to make informed decisions, optimize crop selection, and effectively manage plant diseases for sustainable agriculture and enhanced productivity.

## Results

- Seven classification algorithms were evaluated for crop recommendation tasks.
- The accuracy of each algorithm was assessed, with the Random Forest algorithm achieving the highest accuracy of 99.55%.
- Table 1 below illustrates the accuracy achieved by each algorithm:

> [!IMPORTANT]
> The Random Forest algorithm achieved the highest accuracy of 99.55% in crop recommendation, making it the most reliable model for this system.

**Table 1: Accuracy vs Algorithms**

| Algorithm            | Accuracy   |
| --- | :---: |
| Decision Tree        | 90.0       |
| Gaussian Naive Bayes| 99.09      |
| Support Vector Machine (SVM) | 10.68 |
| Logistic Regression  | 95.23      |
| Random Forest        | 99.55      |
| XGBoost              | 99.09      |
| KNN                  | 97.5       |





---

# 📌Plant Disease Identification Model 

The **Plant Disease Identification Model** utilizes Convolutional Neural Networks (CNN) to accurately identify plant diseases from leaf images. Trained on the **Plant Disease Image Dataset**, which includes 70,295 images in the training set and 17,572 images in the validation set, the model covers 38 different plant disease classes across 14 crops. It detects and classifies diseases such as **Apple Scab**, **Tomato Blight**, and **Powdery Mildew**, offering farmers a reliable tool for early disease detection. 

## Dataset

The **Plant Disease Image Dataset**, used for crop disease identification, consists of 70,295 plant images from the training set and 17,572 images from the validation set, covering a variety of 38 different plant disease classes. The images are standardized to a resolution of 128x128 pixels, and the dataset occupies approximately five gigabytes of storage space.


## Model Architecture
   
For the Plant Disease Identification Model, a Convolutional Neural Network (CNN) architecture was employed. This CNN model was specifically trained for crop disease identification. Leveraging deep learning techniques, the CNN analyzes images of plant leaves to detect and classify diseases accurately. This model aids farmers in early disease detection and management, contributing to improved crop health and yield.


### Key Features:
- **Crop Specific**: The model is designed to diagnose diseases for a specific set of crops.
- **Disease Diagnosis**: It can classify diseases based on images of leaves.
- **Accuracy**: The CNN model demonstrates high accuracy in identifying plant diseases, helping farmers and researchers detect issues early.

### Supported Crops and Diseases:
- The model works with a predefined list of 14 crops.
- For each crop, the model is trained to detect and classify up to 38 specific diseases.

> [!NOTE]
> Since model is trained for specific crops only so it can diagnose those specific crops only. The List of Crops For which this model will be helpful is:

```
[ 'Apple',
'Blueberry',
'Cherry_(including sour)',
'Corn_(maize)',
'Grape',
'Orange',
'Peach', 'Pepper, _bell',
'Potato',
'Raspberry',
'Soybean',
'Squash',
'Strawberry',
'Tomato' ]
```

> [!NOTE]
> The crop which can be used for diagnosis can only diagnose specific disease for which the model is trained. The List of crop diseases on Which Model is trained on is:

```
Found 17572 files belonging to 38 classes.
['Apple___Apple_scab', 'Apple___Black_rot', 'Apple___Cedar_apple_rust', 'Apple___healthy', 'Blueberry___healthy', 'Cherry_(including_sour)___Powdery_mildew', 'Cherry_(including_sour)___healthy',
'Corn_(maize)___Cercospora_leaf_spot Gray_leaf_spot', 'Corn_(maize)___Common_rust_', 'Corn_(maize)___Northern_Leaf_Blight', 'Corn_(maize)___healthy', 'Grape___Black_rot', 'Grape___Esca_(Black_Measles)',
'Grape___Leaf_blight_(Isariopsis_Leaf_Spot)', 'Grape___healthy', 'Orange___Haunglongbing_(Citrus_greening)', 'Peach___Bacterial_spot', 'Peach___healthy', 'Pepper,_bell___Bacterial_spot',
'Pepper,_bell___healthy', 'Potato___Early_blight', 'Potato___Late_blight', 'Potato___healthy', 'Raspberry___healthy', 'Soybean___healthy', 'Squash___Powdery_mildew', 'Strawberry___Leaf_scorch',
'Strawberry___healthy', 'Tomato___Bacterial_spot', 'Tomato___Early_blight', 'Tomato___Late_blight', 'Tomato___Leaf_Mold', 'Tomato___Septoria_leaf_spot', 'Tomato___Spider_mites Two-spotted_spider_mite',
'Tomato___Target_Spot', 'Tomato___Tomato_Yellow_Leaf_Curl_Virus', 'Tomato___Tomato_mosaic_virus', 'Tomato___healthy']

```
### Crop Disease Guide

Here is the detailed information and descriptions for all 38 classes:

### 1. Apple___Apple_scab
**Apple Scab** is caused by the fungus *Venturia inaequalis*. It produces dark, scabby lesions on leaves, fruit, and stems, leading to defoliation and reduced fruit quality. The disease thrives in cool, wet conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Apple Scab - NC State Extension Publications](https://content.ces.ncsu.edu/apple-scab)
- [Apple Scab Management - University of Minnesota](https://extension.umn.edu/disease-management/apple-scab)
- [Managing Apple Scab - The Spruce](https://www.thespruce.com/managing-apple-scab-1402587)

### 2. Apple___Black_rot
**Black Rot** of apple is caused by the fungus *Botryosphaeria obtusa*. It produces dark, sunken lesions on fruit, leaves, and stems, leading to fruit rot and defoliation. The disease thrives in warm, humid conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Black Rot of Apple - NC State Extension Publications](https://content.ces.ncsu.edu/black-rot-of-apple)
- [Black Rot Management - University of Minnesota](https://extension.umn.edu/disease-management/black-rot)
- [Managing Black Rot in Apples - The Spruce](https://www.thespruce.com/managing-black-rot-in-apples-1402587)

### 3. Apple___Cedar_apple_rust
**Cedar Apple Rust** is caused by the fungus *Gymnosporangium juniperi-virginianae*. It produces bright orange lesions on leaves and fruit, leading to defoliation and reduced fruit quality. The disease requires both apple and cedar trees to complete its life cycle and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Cedar Apple Rust - NC State Extension Publications](https://content.ces.ncsu.edu/cedar-apple-rust)
- [Cedar Apple Rust Management - University of Minnesota](https://extension.umn.edu/disease-management/cedar-apple-rust)
- [Managing Cedar Apple Rust - The Spruce](https://www.thespruce.com/managing-cedar-apple-rust-1402587)

### 4. Apple___healthy
Healthy apple trees are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy apple trees produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Apple Trees - The Old Farmer's Almanac](https://www.almanac.com/plant/apple-trees)
- [Apple Tree Growing Guide - The Spruce](https://www.thespruce.com/apple-tree-growing-guide-1402587)
- [Apple Tree Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/apple-tree-cultivation/)

### 5. Blueberry___healthy
Healthy blueberry plants are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy blueberry plants produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Blueberries - The Old Farmer's Almanac](https://www.almanac.com/plant/blueberries)
- [Blueberry Growing Guide - The Spruce](https://www.thespruce.com/blueberry-growing-guide-1402587)
- [Blueberry Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/blueberry-cultivation/)

### 6. Cherry_(including_sour)___Powdery_mildew
**Powdery Mildew** of cherry is caused by the fungus *Podosphaera clandestina*. It produces white, powdery spots on leaves and stems, leading to reduced photosynthesis and yield. The disease thrives in warm, dry conditions and can be managed through the use of resistant varieties, proper spacing, and fungicide applications.

For more details, you can refer to:
- [Powdery Mildew of Cherry - NC State Extension Publications](https://content.ces.ncsu.edu/powdery-mildew-of-cherry)
- [Powdery Mildew Management - University of Minnesota](https://extension.umn.edu/disease-management/powdery-mildew)
- [Managing Powdery Mildew in Cherries - The Spruce](https://www.thespruce.com/managing-powdery-mildew-in-cherries-1402587)

### 7. Cherry_(including_sour)___healthy
Healthy cherry trees are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy cherry trees produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Cherry Trees - The Old Farmer's Almanac](https://www.almanac.com/plant/cherry-trees)
- [Cherry Tree Growing Guide - The Spruce](https://www.thespruce.com/cherry-tree-growing-guide-1402587)
- [Cherry Tree Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/cherry-tree-cultivation/)

### 8. Corn_(maize)___Cercospora_leaf_spot Gray_leaf_spot
**Gray Leaf Spot** of corn is caused by the fungus *Cercospora zeae-maydis*. It produces rectangular, gray lesions on leaves, leading to reduced photosynthesis and yield. The disease thrives in warm, humid conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Gray Leaf Spot of Corn - NC State Extension Publications](https://content.ces.ncsu.edu/gray-leaf-spot-of-corn)
- [Gray Leaf Spot Management - University of Minnesota](https://extension.umn.edu/disease-management/gray-leaf-spot)
- [Managing Gray Leaf Spot in Corn - The Spruce](https://www.thespruce.com/managing-gray-leaf-spot-in-corn-1402587)

### 9. Corn_(maize)___Common_rust_
**Common Rust** of corn is caused by the fungus *Puccinia sorghi*. It produces small, reddish-brown pustules on leaves, leading to reduced photosynthesis and yield. The disease thrives in cool, wet conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Common Rust of Corn - NC State Extension Publications](https://content.ces.ncsu.edu/common-rust-of-corn)
- [Common Rust Management - University of Minnesota](https://extension.umn.edu/disease-management/common-rust)
- [Managing Common Rust in Corn - The Spruce](https://www.thespruce.com/managing-common-rust-in-corn-1402587)

### 10. Corn_(maize)___Northern_Leaf_Blight
**Northern Leaf Blight** of corn is caused by the fungus *Exserohilum turcicum*. It produces long, grayish-green lesions on leaves, leading to reduced photosynthesis and yield. The disease thrives in cool, wet conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Northern Leaf Blight of Corn - NC State Extension Publications](https://content.ces.ncsu.edu/northern-leaf-blight-of-corn)
- [Northern Leaf Blight Management - University of Minnesota](https://extension.umn.edu/disease-management/northern-leaf-blight)
- [Managing Northern Leaf Blight in Corn - The Spruce](https://www.thespruce.com/managing-northern-leaf-blight-in-corn-1402587)

### 11. Corn_(maize)___healthy
Healthy corn plants are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper fertilization, and timely irrigation. Healthy corn plants produce high-quality grain and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Corn - The Old Farmer's Almanac](https://www.almanac.com/plant/corn)
- [Corn Growing Guide - The Spruce](https://www.thespruce.com/corn-growing-guide-1402587)
- [Corn Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/corn-cultivation/)

### 12. Grape___Black_rot
**Black Rot** of grape is caused by the fungus *Guignardia bidwellii*. It produces dark, sunken lesions on leaves, stems, and fruit, leading to fruit rot and defoliation. The disease thrives in warm, humid conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Black Rot of Grape - NC State Extension Publications](https://content.ces.ncsu.edu/black-rot-of-grape)
- [Black Rot Management - University of Minnesota](https://extension.umn.edu/disease-management/black-rot)
- [Managing Black Rot in Grapes - The Spruce](https://www.thespruce.com/managing-black-rot-in-grapes-1402587)

### 13. Grape___Esca_(Black_Measles)
**Esca** or **Black Measles** of grape is caused by a complex of fungi, including *Phaeoacremonium aleophilum* and *Phaeomoniella chlamydospora*. It produces dark, sunken lesions on leaves, stems, and fruit, leading to fruit rot and defoliation. The disease thrives in warm, humid conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Esca (Black Measles) of Grape - NC State Extension Publications](https://content.ces.ncsu.edu/esca-black-measles-of-grape)
- [Esca Management - University of Minnesota](https://extension.umn.edu/disease-management/esca)
- [Managing Esca in Grapes - The Spruce](https://www.thespruce.com/managing-esca-in-grapes-1402587)

### 14. Grape___Leaf_blight_(Isariopsis_Leaf_Spot)
**Leaf Blight** or **Isariopsis Leaf Spot** of grape is caused by the fungus *Isariopsis clavispora*. It produces dark, angular lesions on leaves, leading to defoliation and reduced yield. The disease thrives in warm, humid conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Leaf Blight of Grape - NC State Extension Publications](https://content.ces.ncsu.edu/leaf-blight-of-grape)
- [Leaf Blight Management - University of Minnesota](https://extension.umn.edu/disease-management/leaf-blight)
- [Managing Leaf Blight in Grapes - The Spruce](https://www.thespruce.com/managing-leaf-blight-in-grapes-1402587)

### 15. Grape___healthy
Healthy grapevines are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy grapevines produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Grapes - The Old Farmer's Almanac](https://www.almanac.com/plant/grapes)
- [Grape Growing Guide - The Spruce](https://www.thespruce.com/grape-growing-guide-1402587)
- [Grape Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/grape-cultivation/)

### 16. Orange___Haunglongbing_(Citrus_greening)
**Huanglongbing (HLB)** or **Citrus Greening** is caused by the bacterium *Candidatus Liberibacter asiaticus*. It produces yellowing and blotching of leaves, stunted growth, and misshapen fruit. The disease is transmitted by the Asian citrus psyllid and can be managed through the use of resistant varieties, control of the psyllid vector, and removal of infected plants.

For more details, you can refer to:
- [Huanglongbing (Citrus Greening) - NC State Extension Publications](https://content.ces.ncsu.edu/huanglongbing-citrus-greening)
- [Citrus Greening Management - University of Minnesota](https://extension.umn.edu/disease-management/citrus-greening)
- [Managing Citrus Greening - The Spruce](https://www.thespruce.com/managing-citrus-greening-1402587)

### 17. Peach___Bacterial_spot
**Bacterial Spot** of peach is caused by the bacterium *Xanthomonas arboricola pv. pruni*. It produces dark, water-soaked lesions on leaves, stems, and fruit, leading to defoliation and reduced fruit quality. The disease thrives in warm, humid conditions and can be managed through the use of resistant varieties, proper sanitation, and bactericide applications.

For more details, you can refer to:
- [Bacterial Spot of Peach - NC State Extension Publications](https://content.ces.ncsu.edu/bacterial-spot-of-peach)
- [Bacterial Spot Management - University of Minnesota](https://extension.umn.edu/disease-management/bacterial-spot)
- [Managing Bacterial Spot in Peaches - The Spruce](https://www.thespruce.com/managing-bacterial-spot-in-peaches-1402587)

### 18. Peach___healthy
Healthy peach trees are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy peach trees produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Peach Trees - The Old Farmer's Almanac](https://www.almanac.com/plant/peach-trees)
- [Peach Tree Growing Guide - The Spruce](https://www.thespruce.com/peach-tree-growing-guide-1402587)
- [Peach Tree Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/peach-tree-cultivation/)

### 19. Pepper,_bell___Bacterial_spot
**Bacterial Spot** of bell pepper is caused by several species of *Xanthomonas*. It produces dark, water-soaked lesions on leaves, stems, and fruit, leading to defoliation and reduced yield. The disease thrives in warm, humid conditions and can be managed through the use of resistant varieties, proper sanitation, and bactericide applications.

For more details, you can refer to:
- [Bacterial Spot of Bell Pepper - NC State Extension Publications](https://content.ces.ncsu.edu/bacterial-spot-of-bell-pepper)
- [Bacterial Spot Management - University of Minnesota](https://extension.umn.edu/disease-management/bacterial-spot)
- [Managing Bacterial Spot in Bell Peppers - The Spruce](https://www.thespruce.com/managing-bacterial-spot-in-bell-peppers-1402587)

### 20. Pepper,_bell___healthy
Healthy bell pepper plants are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy bell pepper plants produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Bell Peppers - The Old Farmer's Almanac](https://www.almanac.com/plant/bell-peppers)
- [Bell Pepper Growing Guide - The Spruce](https://www.thespruce.com/bell-pepper-growing-guide-1402587)
- [Bell Pepper Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/bell-pepper-cultivation/)

### 21. Potato___Early_blight
**Early Blight** of potato is caused by the fungus *Alternaria solani*. It produces dark, concentric lesions on leaves, stems, and tubers, leading to defoliation and reduced yield. The disease thrives in warm, humid conditions and can be managed through crop rotation, resistant varieties, and fungicide applications.

For more details, you can refer to:
- [Early Blight of Potato - NC State Extension Publications](https://content.ces.ncsu.edu/early-blight-of-potato)
- [Early Blight Management - University of Minnesota](https://extension.umn.edu/disease-management/early-blight)
- [Managing Early Blight in Potatoes - The Spruce](https://www.thespruce.com/managing-early-blight-in-potatoes-1402587)

### 22. Potato___Late_blight
**Late Blight** of potato is caused by the oomycete *Phytophthora infestans*. It produces water-soaked lesions on leaves, stems, and tubers, leading to rapid plant collapse and tuber rot. The disease thrives in cool, wet conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Late Blight of Potato - NC State Extension Publications](https://content.ces.ncsu.edu/late-blight-of-potato)
- [Late Blight Management - University of Minnesota](https://extension.umn.edu/disease-management/late-blight)
- [Managing Late Blight in Potatoes - The Spruce](https://www.thespruce.com/managing-late-blight-in-potatoes-1402587)

### 23. Potato___healthy
Healthy potato plants are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper hilling, adequate irrigation, and balanced fertilization. Healthy potato plants produce high-quality tubers and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Potatoes - The Old Farmer's Almanac](https://www.almanac.com/plant/potatoes)
- [Potato Growing Guide - The Spruce](https://www.thespruce.com/potato-growing-guide-1402587)
- [Potato Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/potato-cultivation/)

### 24. Raspberry___healthy
Healthy raspberry plants are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy raspberry plants produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Raspberries - The Old Farmer's Almanac](https://www.almanac.com/plant/raspberries)
- [Raspberry Growing Guide - The Spruce](https://www.thespruce.com/raspberry-growing-guide-1402587)
- [Raspberry Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/raspberry-cultivation/)

### 25. Soybean___healthy
Healthy soybean plants are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper crop rotation, adequate irrigation, and balanced fertilization. Healthy soybean plants produce high-quality beans and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Soybeans - The Old Farmer's Almanac](https://www.almanac.com/plant/soybeans)
- [Soybean Growing Guide - The Spruce](https://www.thespruce.com/soybean-growing-guide-1402587)
- [Soybean Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/soybean-cultivation/)

### 26. Squash___Powdery_mildew
**Powdery Mildew** of squash is caused by several species of fungi, including *Erysiphe cichoracearum* and *Podosphaera xanthii*. It produces white, powdery spots on leaves and stems, which can lead to reduced photosynthesis and yield. The disease thrives in warm, dry conditions and can be managed through the use of resistant varieties, proper spacing, and fungicide applications.

For more details, you can refer to:
- [Squash With Mildew - What To Do When Squash Leaves Have Powdery Mildew](https://www.gardeningknowhow.com/edible/vegetables/squash/powdery-mildew-in-squash.htm)
- [Powdery mildew on squash: What is it and how do you get rid of it?](https://savvygardening.com/powdery-mildew-on-squash/)
- [How to Treat Powdery Mildew on Squash: Effective Control Strategies](https://www.evergreenseeds.com/how-to-treat-powdery-mildew-on-squash/)

### 27. Strawberry___Leaf_scorch
**Leaf Scorch** of strawberry is caused by the fungus *Diplocarpon earlianum*. It produces reddish-purple lesions on leaves, which can lead to defoliation and reduced yield. The disease thrives in warm, humid conditions and can be managed through proper sanitation, resistant varieties, and fungicide applications.

For more details, you can refer to:
- [Leaf Scorch of Strawberry - NC State Extension Publications](https://content.ces.ncsu.edu/leaf-scorch-of-strawberry)
- [11 Strawberry Diseases: How to Identify, Prevent, and Treat Them](https://www.epicgardening.com/strawberry-diseases/)
- [Managing Pests in Gardens: Fruit: Diseases: Leaf scorch of strawberries](https://ipm.ucanr.edu/pmg/garden/fruit/DISEASE/leafscorch.html)

### 28. Strawberry___healthy
Healthy strawberry plants are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy strawberry plants produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [How to Grow Strawberries: The Ultimate Guide | Rivulis](https://www.rivulis.com/how-to-grow-strawberries/)
- [How to Grow Strawberries - Tractor Supply Co.](https://www.tractorsupply.com/tsc/cms/life-out-here/garden/growing-guides/fruits/how-to-grow-strawberries)
- [How to Plant & Grow The Perfect Strawberries - The Botanic Home](https://thebotanichome.com/how-to-grow-strawberries/)

### 29. Tomato___Bacterial_spot
**Bacterial Spot** of tomato is caused by several species of *Xanthomonas*. It produces dark, water-soaked lesions on leaves, stems, and fruit, leading to defoliation and reduced yield. The disease thrives in warm, humid conditions and can be managed through the use of resistant varieties, proper sanitation, and bactericide applications.

For more details, you can refer to:
- [Bacterial Spot of Tomato - Wisconsin Horticulture](https://hort.extension.wisc.edu/articles/bacterial-spot-of-tomato/)
- [Bacterial spot of tomato and pepper | UMN Extension](https://extension.umn.edu/disease-management/bacterial-spot-tomato-and-pepper)
- [Bacterial Spot of Pepper and Tomato - NC State Extension Publications](https://content.ces.ncsu.edu/bacterial-spot-of-pepper-and-tomato)

### 30. Tomato___Early_blight
**Early Blight** of tomato is caused by the fungus *Alternaria solani*. It produces dark, concentric lesions on leaves, stems, and fruit, leading to defoliation and reduced yield. The disease thrives in warm, humid conditions and can be managed through crop rotation, resistant varieties, and fungicide applications.

For more details, you can refer to:
- [Early Blight of Tomato - NC State Extension Publications](https://content.ces.ncsu.edu/early-blight-of-tomato)
- [Early blight in tomato and potato | UMN Extension](https://extension.umn.edu/disease-management/early-blight-tomato-and-potato)
- [How to Control Early Blight of Tomatoes - The Old Farmer's Almanac](https://www.almanac.com/pest/early-blight)

### 31. Tomato___Late_blight
**Late Blight** of tomato is caused by the oomycete *Phytophthora infestans*. It produces water-soaked lesions on leaves, stems, and fruit, leading to rapid plant collapse and fruit rot. The disease thrives in cool, wet conditions and can be managed through the use of resistant varieties, proper sanitation, and fungicide applications.

For more details, you can refer to:
- [Tomato Late Blight - NC State Extension Publications](https://content.ces.ncsu.edu/tomato-late-blight)
- [How to Identify, Treat, and Prevent Late Blight in Tomatoes](https://www.epicgardening.com/late-blight-tomatoes/)
- [22 Tomato Diseases: Identification, Treatment and Prevention - The Spruce](https://www.thespruce.com/identify-treat-prevent-tomato-diseases-7153094)

### 32. Tomato___Leaf_Mold
**Leaf Mold** of tomato is caused by the fungus *Cladosporium fulvum*. It produces yellow spots on the upper leaf surface and a grayish-brown mold on the underside, leading to defoliation and reduced yield. The disease thrives in humid conditions and can be managed through proper ventilation, resistant varieties, and fungicide applications.

For more details, you can refer to:
- [Tomato leaf mold | UMN Extension](https://extension.umn.edu/disease-management/tomato-leaf-mold)
- [Tomato Leaf Mold | Cornell Vegetables - Cornell University](https://www.vegetables.cornell.edu/pest-management/disease-factsheets/tomato-leaf-mold/)
- [Tomato Leaf Mold Treatment: How To Treat Leaf Mold Of Tomato Plants](https://www.gardeningknowhow.com/edible/vegetables/tomato/managing-tomato-leaf-mold.htm)

### 33. Tomato___Septoria_leaf_spot
**Septoria Leaf Spot** of tomato is caused by the fungus *Septoria lycopersici*. It produces small, circular lesions with dark borders and gray centers on leaves, leading to defoliation and reduced yield. The disease thrives in warm, humid conditions and can be managed through proper sanitation, resistant varieties, and fungicide applications.

For more details, you can refer to:
- [Septoria Leaf Spot of Tomato - NC State Extension Publications](https://content.ces.ncsu.edu/septoria-leaf-spot-of-tomato)
- [Septoria Leaf Spot of Tomato - Illinois Extension](https://extension.illinois.edu/plant-problems/septoria-leaf-spot-tomato)
- [Identify and Treat Septoria Leaf Spot on Tomatoes - Gardener's Path](https://gardenerspath.com/how-to/disease-and-pests/septoria-leaf-spot-tomatoes/)

### 34. Tomato___Spider_mites Two-spotted_spider_mite
**Two-Spotted Spider Mite** is a common pest of tomato plants. It produces tiny, yellow or white spots on leaves, leading to leaf bronzing, webbing, and defoliation. The pest thrives in hot, dry conditions and can be managed through proper irrigation, natural predators, and miticide applications.

For more details, you can refer to:
- [Two-Spotted Spider Mite | Entomology - University of Kentucky](https://entomology.ca.uky.edu/ef310)
- [Tomato Cultivars Resistant or Susceptible to Spider Mites Differ in](https://pmc.ncbi.nlm.nih.gov/articles/PMC7952643/)
- [Two-spotted Spider Mite - Center for Agriculture, Food, and the Environment](https://ag.umass.edu/vegetable/fact-sheets/two-spotted-spider-mite)

### 35. Tomato___Target_Spot
**Target Spot** of tomato is caused by the fungus *Corynespora cassiicola*. It produces small, circular lesions with concentric rings on leaves, stems, and fruit, leading to defoliation and reduced yield. The disease thrives in warm, humid conditions and can be managed through proper sanitation, resistant varieties, and fungicide applications.

For more details, you can refer to:
- [Target Spot of Tomato - Bayer](https://www.vegetables.bayer.com/ca/en-ca/resources/agronomic-spotlights/target-spot-of-tomato.html)
- [Target Spot On Tomato Fruit - Gardening Know How](https://www.gardeningknowhow.com/edible/vegetables/tomato/target-spot-on-tomatoes.htm)
- [New Disease Report – Target Spot of Tomato | Purdue University](https://vegcropshotline.org/article/new-disease-report-target-spot-of-tomato/)

### 36. Tomato___Tomato_Yellow_Leaf_Curl_Virus
**Tomato Yellow Leaf Curl Virus (TYLCV)** is a viral disease transmitted by the whitefly *Bemisia tabaci*. It causes yellowing and curling of leaves, stunted growth, and reduced fruit set. The disease is managed through the use of resistant varieties, control of the whitefly vector, and removal of infected plants.

For more details, you can refer to:
- [Tomato Yellow Leaf Curl Virus - NC State Extension Publications](https://content.ces.ncsu.edu/tomato-yellow-leaf-curl-virus)
- [Tomato yellow leaf curl virus - Wikipedia](https://en.wikipedia.org/wiki/Tomato_yellow_leaf_curl_virus)
- [Tomato Yellow Leaf Curl Virus Disease - Springer](https://link.springer.com/book/10.1007/978-1-4020-4769-5)

### 37. Tomato___Tomato_mosaic_virus
**Tomato Mosaic Virus (ToMV)** is a viral disease that causes mottling, yellowing, and distortion of leaves, leading to reduced yield and fruit quality. The virus is transmitted through mechanical means, such as contaminated tools and hands. The disease is managed through the use of resistant varieties, proper sanitation, and removal of infected plants.

For more details, you can refer to:
- [Tomato Mosaic | Vegetable Disease Facts - U.OSU](https://u.osu.edu/vegetablediseasefacts/tomato-diseases/high-tunnel-diseases/tomato-mosaic/)
- [Tomato mosaic virus - Wikipedia](https://en.wikipedia.org/wiki/Tomato_mosaic_virus)
- [Tomato viruses | UMN Extension](https://extension.umn.edu/disease-management/tomato-viruses)

### 38. Tomato___healthy
Healthy tomato plants are those that are free from diseases and pests, and are well-maintained through proper cultural practices. Key practices include selecting disease-resistant varieties, proper pruning, adequate irrigation, and balanced fertilization. Healthy tomato plants produce high-quality fruit and have a longer productive lifespan.

For more details, you can refer to:
- [Tomato | Crops - Plantix](https://plantix.net/en/library/crops/tomato/)
- [13 Best Tips for Planting and Growing Great Tomatoes - The Spruce](https://www.thespruce.com/top-tomato-growing-tips-1402587)
- [Tomato Cultivation: Tips for a Healthy Crop - The Farming Insider](https://thefarminginsider.com/tomato-cultivation/)





































