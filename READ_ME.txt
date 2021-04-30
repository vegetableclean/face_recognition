website for reference : https://zhuanlan.zhihu.com/p/36962109
--First-- environment kick-off

1.go to cmd -- # in to face_recognition_practice folder
cd C:\Users\vegetableclean\Anaconda3\Lib\site-packages\conda\face_recognition_practice

2.activate enviroment--named tensorflow 
activate tensorflow
{it will show up (tensorflow) at left side}

3.compile code
python (_folder name_).py

--SECOND--Explaination for files:
(0=open camera q=close camera)

1.catch_usb_video.py  # check if camera can open
python python catch_usb_video.py 0

2.recognise_face.py # detect face
python recognise_face.py 0

3.face_datas.py # prepare data
# make and add "me" and "other" file to the Brief contents
execute <python face_datas.py 0 1000 data/me> <python face_datas.py 0 1000 data/other>
#remember to delete the non-face image

4.face_train_use_keras.py #train model
mkdir model #make model file
python face_predict_use_keras.py 
we can see loss (loss) accuaray(acc) valdiation loss(val_loss) valdiation accuracy(val_acc)

*refixed face_train_use_keras.py 
#take away 
#train model,take away
model = Model()
model.build_model(dataset)
model.train(dataset)
model.save_model(file_path = './model/me.face.model.h5')
'''
#evaluation model 
model = Model()
model.load_model(file_path = './model/me.face.model.h5')
model.evaluate(dataset)

execute again <python face_train_use_keras.py> we can see the total accuracy

5.face_predict_use_keras.py #recognize face
python face_predict_use_keras.py 0

---END---


