# Face-Emotion-Recognition

## **π‘νλ‘μ νΈ μμ½**
μΈκ°μ κ°μ μ κ΅¬λΆνλ λ₯λ¬λ λͺ¨λΈμ AUμ€μ½μ΄λ₯Ό μΆμΆνκ³  λ€μ€ λ‘μ§μ€ν± νκ·λ₯Ό μ΄μ©νμ¬ μ€λͺν¨μΌμ¨ λΆλ₯μ κ·Όκ±°λ₯Ό μ»λλ€.


## **π‘νλ‘μ νΈ κ°μ**
 μ½λ‘λκ° λ°μμΌλ‘ μΈν΄ μ€λ΄μΈμμ λ§μ€ν¬λ₯Ό μ°©μ©ν μ§ 2λμ΄ λμΌλ©° λ°©μ­ κΈ°μ‘° μ νμΌλ‘ μΈν΄ μ€μΈ μ°©μ© μλ¬΄κ° ν΄μ λμ§λ§ λ§μ€ν¬λ μ¬μ ν μ€λ΄λ μ€μΈ λ€μ€μ΄μ©μμ€μμλ κΌ­ μ°©μ©ν΄μΌ νλ€.
 
 
μ΄μ κ°μ λ§μ€ν¬ μ°©μ© μ₯κΈ°νλ μ΄λ¦°μ΄λ€μ μΌκ΅΄ μΈμ λ₯λ ₯μ λΆμ μ  μν₯μ λ―ΈμΉλ€λ μ°κ΅¬κ° λ°νλκ³  μλ μν©μ΄λ€. λ°λΌμ λ³Έ νλ‘μ νΈλ μ°¨ν μ΄λ¦°μ΄λ€μ κ°μ  μ΄ν΄ λ° νμ΅μ λμΈ μ μλ νλμ λ°©μμΌλ‘μ **μΈκ°μ κ°μ μ νλ¨ν  μ μλ νμ΅λͺ¨λΈ**μ λ§λλ κ²μ λͺ©νλ‘ νλ€. 


μ°μ  κ°μ₯ λνμ μΈ κ°μ  6κ°μ§(angry, disgust, happy, neutral, sad, surprise)λ₯Ό μ μ νμ¬  [λ°μ΄ν° μ](#λ°μ΄ν°μ)μ κ΅¬μ±νμλ€. [μ€νμμ€ βopenfaceβ](https://github.com/TadasBaltrusaitis/OpenFace/wiki/Action-Units)λ₯Ό νμ©ν΄ λ°μ΄ν°μμ λΆμνμ¬ κ° κ°μ μ μ’ν λ° AUμ€μ½μ΄ jpgνμΌ, csvνμΌ λ°μ΄ν°μμ νλ³΄νλ€. 6κ°μ§ κ°μ μ λΆλ₯νλ λ°©λ²μ **λ€μ€ λ‘μ§μ€ν± νκ· λ°©μ**μ μ΄μ©νμΌλ©° **μμ±μ AU_r, ν΄λμ€λ 6κ°μ§ κ°μ **μΌλ‘ μ νλ€. 


 λ§μ§λ§μΌλ‘ AUμ€μ½μ΄λ₯Ό νμ©ν [λ€μ€λ‘μ§μ€ν± νκ· λ°©μμ λͺ¨λΈ](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/src/model.ipynb), κ΅¬κΈμμ μ κ³΅νλ μλΉμ€μΈ [Teachable Machine νμ© λͺ¨λΈ](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/src/Teachable_machine_model.ipynb), [CNN νμ© λͺ¨λΈ](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/src/CNN_model.ipynb)(based [kaggle data_set](https://www.kaggle.com/datasets/msambare/fer2013))μ μ±λ₯μ λΉκ΅ν΄λ³Έλ€.

## **π‘λ²μ **
```
TensorFlow 2.9.2 
Python 3.8.13 μ΄μ
matplotlib 3.5.2
keras 2.9.0
```
## **π‘ 1.μ€νμμ€ νκ²½ μ€μ  λ° λ°μ΄ν° μΆμΆ λ°©λ²**
### 1) μ€νμμ€ νκ²½ μ€μ 
1. Creat folder
- [creatFolder.py](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/src/creatFloder.py)μΌλ‘ OpenFace > input, output μμ±

2. Docker download 
- [docker download](https://docs.docker.com/get-docker/) ν starting

3. Window powershell command μ»€λ μ€μΉ
```
wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
```
### 2) λ°μ΄ν°μ μΆμΆ
λ°©λ²1. window powershell command μλ ₯
docker μ€ν ν openface 
```
docker run -it --rm -d --name openface -v C:\OpenFace\input:/home/openface-build/build/bin/input -v C:\OpenFace\output:/home/openface-build/build/bin/processed -w /home/openface-build/build/bin algebr/openface:latest
```
input νμ ν΄λμ λ°μ΄ν°μ λΆμ
  > inputμ νμ ν΄λμ λΆμνκ³ μνλ λ°μ΄ν°(jpgνμλ§ κ°λ₯)μ μ₯ 
```
docker exec openface ./FaceLandmarkImg -fdir input/[ν΄λλͺ] -out_dir processed/[ν΄λλͺ]
```
λ°©λ²2. νμ΄μ¬ μ½λ μλ ₯
```
import os
# docker μ€ν ν openface μ€ν λͺλ μ΄
os.system('docker run -it --rm -d --name openface -v C:\OpenFace\input:/home/openface-build/build/bin/input -v C:\OpenFace\output:/home/openface-build/build/bin/processed -w /home/openface-build/build/bin algebr/openface:latest')
# input νμ ν΄λ λΆμ > output νμ ν΄λ csv νμΌ μμ± λͺλ Ήμ΄
os.system('docker exec openface ./FaceLandmarkImg -fdir input/[ν΄λλͺ] -out_dir processed/[ν΄λλͺ]')
```
- μ€νκ²°κ³Ό :  [command.ipynb](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/src/command.ipynb)
> <img width="304" alt="hahahah" src="https://user-images.githubusercontent.com/101412264/186561481-37dda9e5-13ea-486e-8301-206c37307ba9.PNG">


## **π‘ 2 .μ΅μ’ νμ΅ λ°μ΄ν° μμ± λ° λͺ¨λΈ μ€κ³ λ°©λ²**
### 1) csvνμΌ ν΅ν© ν au_r μ€μ½μ΄ μΆμΆ > μ΅μ’ νμ΅λ°μ΄ν° μμ±
- κ° ν΄λμ€λ³λ‘ λ°λ³΅ν΄μ csvνμΌ λ§λ€κΈ° > κ²°κ³Ό: [/data/csv/angry.csv](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/data/csv/angry.csv),[/data/csv/disgust.csv](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/data/csv/disgust.csv),[/data/csv/happy.csv](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/data/csv/happy.csv),[/data/csv/neutral.csv](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/data/csv/nutral.csv), [/data/csv/sad.csv](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/data/csv/sad.csv),[/data/csv/surprise.csv](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/data/csv/surprise.csv)
```
import os
import pandas as pd

file_csv = []
def print_files_in_dir(root_dir):
    files = os.listdir(root_dir)
    for file in files:
        path = os.path.join(root_dir, file)
        file_name = path
        if file_name[-4:] =='.csv':
            file_csv.append(file_name)
 
if __name__ == "__main__":
    root_dir = r"C:\OpenFace\output\[κ° κ°μ  ν΄λλͺ]"
    print_files_in_dir(root_dir)

# csv νμΌ > dataframe μ½κ³  ν΅ν©νκΈ°
all_df = pd.DataFrame()
for path in file_csv:
    df = pd.read_csv(path)
    all_df = pd.concat([all_df,df],ignore_index=True)
```
**AU_r μ€μ½μ΄(μμ±) μΆμΆ λ° ν΄λμ€(κ°μ )μΆκ° & csvμ μ₯**
```
all_df_X = all_df.iloc[:,-35:-18]
all_df['emotion'] = # μΆμΆνλ κ°μ  λ°μ΄ν°μ λ§μΆ°μ μ«μ λ£κΈ° - angry : 0 , disgust : 1, happy : 2, neutral : 3, sad : 4, surprise:5
all_df.to_csv('emotion.csv') # 6κ°μ§ κ°μ  csv νμΌ ν΅ν© > emotion μ΅μ’ νμ΅ λ°μ΄ν° μμ±
```
- μ€νκ²°κ³Ό 
> μμ κ³Όμ  λ°λ³΅ ν κ° ν΄λμ€λ³csv νμΌμ μ λΆ ν©μ³μ **μ΅μ’ νμ΅λ°μ΄ν°** [**emotion.csv**](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/data/csv/emotion.csv) μμ±

### 2) νμ΅ μ§ν : λ€μ€ λ‘μ§μ€ν± νκ·λΆμ > λͺ¨λΈ μ€κ³
νμ΅ν  λ°μ΄ν° λΆλ¬μ€κΈ° λ° λλ€μΆμΆ
```
df_pre = pd.read_csv('emotion.csv')

df_all = df_pre.sample(frac=1)
```
μ-ν«μ½λ©
```
dataset = df_all.values

import tensorflow as tf
from sklearn.preprocessing import LabelEncoder

X = dataset[:,:-1].astype(float) # confidence μ μΈ
Y = dataset[:,-1]
Y_encoded = tf.keras.utils.to_categorical(Y)
```
λ°μ΄ν°μ(emotion.csv)μμ train,test μ€μ  
```
X_train,X_test,Y_train,Y_test = train_test_split(X,Y_encoded,
                                                 test_size = 0.25)
```
λ₯λ¬λ λͺ¨λΈ κ²°μ νκΈ° : relu μ softmax μ¬μ©
```
model = Sequential()
model.add(Dense(300,input_dim=17,activation="relu"))
model.add(Dense(200,activation="relu"))
model.add(Dense(100,activation="relu"))
model.add(Dense(50,activation="relu"))
model.add(Dense(6,activation="softmax"))
model.compile(loss='categorical_crossentropy',
              optimizer='adam',
              metrics=['accuracy'])
```
μλ μ€λ¨ μ€μ  
```
early_stopping_callback = EarlyStopping(monitor='val_loss',patience=7)
```
λͺ¨λΈ μ μ₯ ν΄λ μμ± λ°  μ μ₯ μ‘°κ±΄ μ€μ 
```
MODEL_DIR = './model'
if not os.path.exists(MODEL_DIR):
  os.mkdir(MODEL_DIR)
# λͺ¨λΈ μ μ₯ μ‘°κ±΄ μ€μ 
modelpath = './model/{epoch:02d}-{val_loss:.4f}.hdf5'
checkpointer = ModelCheckpoint(filepath=modelpath,
                               monitor="val_loss",
                               verbose=1,
                               save_best_only=True)
```
λͺ¨λΈ μ€ννκΈ° λ° μ μ₯
```
history = model.fit(X_train,Y_train,
                    validation_split=0.33,
                    epochs=5000,
                    batch_size=50,
                    callbacks=[early_stopping_callback,checkpointer])
```

## **π‘λͺ¨λΈ μ±λ₯** 
- Model : [best_model.hdf5](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/models/best_model.hdf5)
- loss : 0.4320
- val_loss : 0.7306
- accuracy : 0.8518
- val_accuracy : 0.7353
- last update : 22/08/24
- μ€ν κ²°κ³Ό : [model.ipynb](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/src/model.ipynb)

## **π‘λͺ¨λΈ νμ€νΈ** 
- νμ΅νμ§ μμ [test_data](https://github.com/Happy-ryan/Face-Emotion-Recognition/tree/main/data/jpg/test)μ [best_model.hdf5](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/models/best_model.hdf5) λ£μ΄ μ λ΅λ₯  νμ
- μ€νκ²°κ³Ό
[exec_final.ipynb](https://github.com/Happy-ryan/Face-Emotion-Recognition/blob/main/src/exec_final.ipynb)

## **π‘λͺ¨λΈ μ±λ₯ λΉκ΅**
1. [test_data](https://github.com/Happy-ryan/Face-Emotion-Recognition/tree/main/data/jpg/test)μ λν λ κ°μ§ λͺ¨λΈ μ μ²΄ μ λ΅λ₯  λΉκ΅
- AUμ€μ½μ΄λ₯Ό νμ©ν λ€μ€λ‘μ§μ€ν± νκ· λ°©μμ λͺ¨λΈ : **μ μ²΄ μ λ΅λ₯  : 0.80**
- Teachable Machine νμ© λͺ¨λΈ : **μ μ²΄ μ λ΅λ₯  : 0.47**

- μ λ¦¬
> λ°μ΄ν°μ μκ° μ μ λ κ·Έλ¦¬κ³  λΆλ₯ν΄μΌν  ν΄λμ€κ° λ§μ λ Teachable Machine λͺ¨λΈμ μ λλ‘ κ°μ  νμ μ νκΈ° μ΄λ €μ΄ κ²μ μ μ μλ€.


2. λ°μ΄ν° μμ λ°λ₯Έ κ° κ°μ λ³ μ λ΅λ₯  νλ¨
- model ( based [λ°μ΄ν° μ](#λ°μ΄ν°μ) : μ΄ train_data μ : 4474 / μ΄ test_data : 60 )
> <img width="378" alt="model" src="https://user-images.githubusercontent.com/101412264/186623603-38c37561-ec9b-4989-9e26-013ac503627f.png">


- CNN ( based [kaggle data_set](https://www.kaggle.com/datasets/msambare/fer2013) : μ΄ train_data μ : 25538 / μ΄ test_data μ 7168 )
> <img width="376" alt="CNN" src="https://user-images.githubusercontent.com/101412264/186623588-4af2aa46-203b-4cc7-82cf-862cd8cadc49.png">


- Teachable machine ( based[λ°μ΄ν° μ](#λ°μ΄ν°μ) : μ΄ train_data μ : 4474 / μ΄ test_data : 60 )  
> <img width="421" alt="γγ" src="https://user-images.githubusercontent.com/101412264/186637822-e5c234fe-ca69-481f-9e99-fce62be79658.png">


- μ΅μ’ μ λ¦¬
> Teachable machine λͺ¨λΈκ³Ό CNN λͺ¨λΈ λͺ¨λ CNNμ κΈ°λ³ΈμΌλ‘ νλλ° κ° λ°μ΄ν°λ₯Ό νμ΅νκ³  test_dataμ λν κ° κ°μ  νμ λ₯  λ° μ μ²΄ μ λ΅λ₯  μ°¨μ΄κ° μ¬νκ²λλ€. μ΄λ CNNκΈ°λ°μΌλ‘
> μΈκ°μ κ°μ μ νλ¨νκΈ° μν΄μλ **kaggle λ°μ΄ν°λ§νΌ μμ£Ό λ§μ μμ λ°μ΄ν°κ° μμ΄μΌ μ μλ―Έν νμ΅μ΄ μ§νλμ΄ νμ μ ν  μ μλ€λ κ²°λ‘ **μ΄ λμ¨λ€.
> 
> κ·Έμ λ°ν΄ modelμ CNN λͺ¨λΈ νμ΅ λ°μ΄ν° μμ 17%μ λΆκ³Όνμ§λ§ test_dataμ λν΄μ CNNλͺ¨λΈκ³Ό μ μ¬ν κ²½ν₯κ³Ό μ λ΅λ₯ μ λ³΄μ¬μ€λ€. 
> μ΄λ₯Ό ν΅ν΄μ **AU_r μ€μ½μ΄κ° μΈκ°μ κ°μ κ³Ό μ μλ―Έν μκ΄κ΄κ³κ° μμ΄ μ μ μμ λ°μ΄ν°λ‘λ λμ νλ₯ λ‘ μΈκ°μ κ°μ μ νλ¨ν  μ μλ€λ κ²°λ‘ **μ μ μ μλ€.

## **λ°μ΄ν°μ** 
μ΄ 6μ’ μ μ 
1. train_data
- angry 713μ₯
- disgust 220μ₯
- happy 766μ₯
- neutral 700μ₯
- sad 1039μ₯
- surprise 1041μ₯
2. test_data
- κ° κ°μ λ³ 10μ₯μ© 60μ₯
