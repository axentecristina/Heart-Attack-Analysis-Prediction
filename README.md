# Heart-Attack-Analysis-Prediction

The purpose of the project is to analyze data, clean and transform it, as well as to predict whether a person is predisposed to a heart attack.

The dataset is provided from the website: https://www.kaggle.com/ and contains features about Heart Attack. The file is named heart.csv.

The columns in the file are as follows:

- Age: patient's age
- Sex: patient's gender
- exang: exercise-induced angina (1 = yes; 0 = no)
- ca: number of major blood vessels (0-3)
- cp: chest pain type which can be of 4 types:
    - Value 1: typical angina
    - Value 2: atypical angina
    - Value 3: non-anginal pain
    - Value 4: asymptomatic
- trtbps: resting blood pressure (in mm Hg)
- chol: cholesterol in mg/dl obtained from BMI sensor
- fbs: (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false)
- rest_ecg: resting electrocardiographic results
  - Value 0: normal
  - Value 1: having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV)
  - Value 2: showing probable or definite left ventricular hypertrophy by Estes' criteria
- thalach: maximum heart rate achieved
- output: 0= less chance of heart attack 1= more chance of heart attack.

## Steps

I will briefly outline the steps I followed, as well as the conclusions drawn based on the analyses conducted.

1. Importing Libraries - I imported the necessary libraries for the project development.
2. In this step, I loaded the file: heart.csv into a DataFrame.
3. Data Analysis
   - I checked if the file contains null values. It does not contain such values.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/13c355ec-7c5e-434e-8395-08a944b1e599)
   - I checked if the dataset contains duplicate values. It contains one duplicate row. I removed that row to eliminate duplicates.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/2b64ab95-e701-44d9-858b-38e8eb2e0efb)
   - Next, the descriptive statistics of the dataset were displayed, as well as the count of values 0 and 1 in the 'output' column.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/f088a603-21af-4489-a75e-fdcbc0c90e88)
   - I analyzed that individuals experiencing chest pain are more predisposed to a heart attack:
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/7da81471-1c8f-46f4-8679-be36bbc0c4e5)
   - Individuals with fasting blood sugar levels < 120 mg/dl are predisposed to a heart attack:
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/b3591fd6-96cd-492e-80d9-024e2934f079)

4. In this step, I used SparkSQL to perform additional data analyses.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/2e68c3b3-2174-4e92-9e78-0b6fa7c53415)

5. Machine Learning Method
   - I separated the features from the target variable and then split the columns into Train and Test sets.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/c06859fc-1fa6-4d4a-beb3-b63a8261a4fb)

   - I utilized the Logistic Regression model since we aim to obtain values of only 0 and 1. Subsequently, the classification model was created and defined, and the data were trained. Once the prediction was executed, I used the confusion matrix.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/506c0f79-dc71-4615-a7c4-f601e3fd3e82)
   - Its accuracy was 0.984.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/132b0dac-ef32-4f10-847b-d116fc35ad7c)
6. Deep Learning Method
   - TensorFlow and the Sequential, Dense, Activation, and Dropout classes from Keras were imported.
   - I created a neural network. Then, I used the relu activation function in the intermediate layers and a activation function.
   - The model was compiled and trained.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/8963cbf1-f052-4c20-b612-ee9987418eaf)
   - The model was evaluated through a classification report.
   ![image](https://github.com/axentecristina/Heart-Attack-Analysis-Prediction/assets/48519726/d6e9a463-2608-4c96-b127-c41f824a8850)

In conclusion, I trained the model using both a Machine Learning method and a Deep Learning method, achieving an accuracy of 0.984 and 0.9, respectively.









