# Introduction_to_Autotronics_System_Design
This repository is autotronics system design course Lab.We learn some CNN model and YOLO model to detect face.
## LAB1
`給定很小的資料集讓你進行訓練，過程中不斷overfitting，為解決此問題花了好大功夫，最後透過data augmentation以及增加公開資料集cfp-dataset成功降低val_loss`
```js
map_characters ={ 0:'R_train',1:'L_train',2:'F_train',3:'B_train'} //要分類成右邊、左邊、正面、背面
```
```js
def load_pictures(): //load 圖片資料
```
```js
def get_dataset(save=False, load=False):/抓取圖片資料
```
```js
X_train, X_test, y_train, y_test = get_dataset(save=False, load=False) //分成8:1:1 訓練:測試:驗證
```
```js
def create_model_face(input_shape)://神經網路的架構
```
```js
sgd = SGD(lr=0.03, decay=1e-6, momentum=0.9, nesterov=True)//optimizer使用隨機梯度下降、learn-rate設定1e-6....
model.compile(loss='categorical_crossentropy',
             optimizer=sgd,
             metrics=['accuracy' ])
```
```js
batch_size = 64//批次次數
epochs = 500//訓練次數
//開始訓練
history = model.fit(X_train2, y_train2,
         batch_size=batch_size,
         epochs=epochs,
         verbose=1,
         validation_data=(X_val, y_val),
         shuffle=True,
         callbacks=[
             #LearningRateScheduler(lr_schedule),
             ModelCheckpoint('classifier_lab1102.h5', save_best_only=True)
         ]
                   )
```
`loss值`

![image](https://github.com/7-RED/Introduction_to_Autotronics_System_Design/blob/master/圖片/3.PNG)

`accuracy值`

![image](https://github.com/7-RED/Introduction_to_Autotronics_System_Design/blob/master/圖片/4.PNG)

`最後就計算Confusion Matrix`
