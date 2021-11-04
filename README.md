# Introduction_to_Autotronics_System_Design
This repository is autotronics system design course Lab.We learn some CNN model and YOLO model to detect face.
## LAB1
`給定很小的資料集讓你進行訓練，過程中不斷overfitting，為解決此問題花了好大功夫，最後透過data augmentation以及增加公開資料集cfp-dataset成功降低val_loss`
```js
map_characters ={ 0:'R_train',1:'L_train',2:'F_train',3:'B_train'} //要分類成右邊、左邊、正面、背面
```
`def load_pictures(): //load 圖片資料`
