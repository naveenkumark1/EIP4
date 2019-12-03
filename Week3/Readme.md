#####################################################
## Benchmark Model provided to us at 49th Epoch : 83.58%. 

Epoch 49/50
390/390 [==============================] - 20s 52ms/step - loss: 0.3109 - acc: 0.8972 - val_loss: 0.5585 - val_acc: 0.8358
#####################################################

#####################################################
## Best Accuracy of the model we tried at 26th Epoch : 83.10%

Epoch 00026: LearningRateScheduler setting learning rate to 0.0005571030640668523.
390/390 [==============================] - 45s 115ms/step - loss: 0.3955 - acc: 0.8606 - val_loss: 0.5062 - val_acc: 0.8310
Epoch 27/50
#####################################################

#####################################################
## Model Defenition 
#####################################################

##Defineing New Model
# Final Model
weight_decay = 1e-4 ## https://appliedmachinelearning.blog/2018/03/24/achieving-90-accuracy-in-object-recognition-task-on-cifar-10-dataset-with-keras-convolutional-neural-networks/
model1 = Sequential()
model1.add(SeparableConv2D(filters= 32,kernel_size=(3,3),kernel_regularizer=regularizers.l2(weight_decay),depth_multiplier = 1,input_shape=(32,32,3),activation='relu'))  #30
model1.add(BatchNormalization())
model1.add(Dropout(0.2))
# 30*30*32
#receptive field =3
model1.add(SeparableConv2D(filters= 64,kernel_size=(3,3),kernel_regularizer=regularizers.l2(weight_decay),depth_multiplier = 1,activation='relu')) #28
model1.add(Dropout(0.2))
model1.add(BatchNormalization())
# 28*28*64
#receptive field =5
model1.add(SeparableConv2D(filters= 128,kernel_size=(3,3),kernel_regularizer=regularizers.l2(weight_decay),depth_multiplier = 1,activation='relu')) #26
model1.add(BatchNormalization())
model1.add(Dropout(0.2))
# 26*26*128
#receptive field =7
model1.add(MaxPooling2D(pool_size=(2, 2))) #13
# 13*13*32
#receptive field =8

model1.add(SeparableConv2D(filters= 128,kernel_size=(3,3),kernel_regularizer=regularizers.l2(weight_decay),depth_multiplier = 1,activation='relu')) #11
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

# 11*11*128
#receptive field =12

model1.add(SeparableConv2D(filters= 256,kernel_size=(3,3),kernel_regularizer=regularizers.l2(weight_decay),depth_multiplier = 1,activation='relu')) #9
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

# 9*9*256
#receptive field =16

model1.add(MaxPooling2D(pool_size=(2, 2))) 

# 4*4*256
#receptive field =18

model1.add(SeparableConv2D(filters= 64,kernel_size=(1,1),kernel_regularizer=regularizers.l2(weight_decay),depth_multiplier = 1,activation='relu')) 
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

# 4*4*64
#receptive field =18

model1.add(SeparableConv2D(filters= 10,kernel_size=(1,1),kernel_regularizer=regularizers.l2(weight_decay),depth_multiplier = 1,activation='relu')) 
model1.add(BatchNormalization())
model1.add(Dropout(0.2))

# 4*4*10
#receptive field =18
model1.add(SeparableConv2D(filters= 10,kernel_size=(4,4),kernel_regularizer=regularizers.l2(weight_decay),depth_multiplier = 1,activation='relu')) 

# 1*1*10
#receptive field =30
model1.add(GlobalAveragePooling2D())
model1.add(Activation('softmax'))

#######################################
##  LOGS
#######################################

/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:11: UserWarning: The semantics of the Keras 2 argument `steps_per_epoch` is not the same as the Keras 1 argument `samples_per_epoch`. `steps_per_epoch` is the number of batches to draw from the generator at each epoch. Basically steps_per_epoch = samples_per_epoch/batch_size. Similarly `nb_val_samples`->`validation_steps` and `val_samples`->`steps` arguments have changed. Update your method calls accordingly.
  # This is added back by InteractiveShellApp.init_path()
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:11: UserWarning: Update your `fit_generator` call to the Keras 2 API: `fit_generator(<keras_pre..., validation_data=(array([[[..., callbacks=[<keras.ca..., steps_per_epoch=390, epochs=50)`
  # This is added back by InteractiveShellApp.init_path()
Epoch 1/50

Epoch 00001: LearningRateScheduler setting learning rate to 0.005.
390/390 [==============================] - 49s 126ms/step - loss: 0.5707 - acc: 0.8026 - val_loss: 0.8484 - val_acc: 0.7259
Epoch 2/50

Epoch 00002: LearningRateScheduler setting learning rate to 0.0037907505686125857.
390/390 [==============================] - 45s 115ms/step - loss: 0.5473 - acc: 0.8101 - val_loss: 0.8249 - val_acc: 0.7270
Epoch 3/50

Epoch 00003: LearningRateScheduler setting learning rate to 0.003052503052503053.
390/390 [==============================] - 45s 115ms/step - loss: 0.5262 - acc: 0.8163 - val_loss: 0.6963 - val_acc: 0.7645
Epoch 4/50

Epoch 00004: LearningRateScheduler setting learning rate to 0.0025549310168625446.
390/390 [==============================] - 45s 114ms/step - loss: 0.5075 - acc: 0.8224 - val_loss: 0.6630 - val_acc: 0.7784
Epoch 5/50

Epoch 00005: LearningRateScheduler setting learning rate to 0.0021968365553602814.
390/390 [==============================] - 45s 115ms/step - loss: 0.4920 - acc: 0.8290 - val_loss: 0.6085 - val_acc: 0.7924
Epoch 6/50

Epoch 00006: LearningRateScheduler setting learning rate to 0.001926782273603083.
390/390 [==============================] - 45s 115ms/step - loss: 0.4751 - acc: 0.8338 - val_loss: 0.6515 - val_acc: 0.7822
Epoch 7/50

Epoch 00007: LearningRateScheduler setting learning rate to 0.0017158544955387784.
390/390 [==============================] - 45s 115ms/step - loss: 0.4688 - acc: 0.8352 - val_loss: 0.6247 - val_acc: 0.7885
Epoch 8/50

Epoch 00008: LearningRateScheduler setting learning rate to 0.0015465511908444168.
390/390 [==============================] - 45s 115ms/step - loss: 0.4600 - acc: 0.8398 - val_loss: 0.6196 - val_acc: 0.7921
Epoch 9/50

Epoch 00009: LearningRateScheduler setting learning rate to 0.0014076576576576576.
390/390 [==============================] - 45s 114ms/step - loss: 0.4514 - acc: 0.8403 - val_loss: 0.5616 - val_acc: 0.8116
Epoch 10/50

Epoch 00010: LearningRateScheduler setting learning rate to 0.0012916559028674762.
390/390 [==============================] - 45s 114ms/step - loss: 0.4444 - acc: 0.8434 - val_loss: 0.5857 - val_acc: 0.8032
Epoch 11/50

Epoch 00011: LearningRateScheduler setting learning rate to 0.0011933174224343678.
390/390 [==============================] - 44s 114ms/step - loss: 0.4361 - acc: 0.8480 - val_loss: 0.5357 - val_acc: 0.8162
Epoch 12/50

Epoch 00012: LearningRateScheduler setting learning rate to 0.0011088933244621866.
390/390 [==============================] - 45s 114ms/step - loss: 0.4291 - acc: 0.8497 - val_loss: 0.5845 - val_acc: 0.8064
Epoch 13/50

Epoch 00013: LearningRateScheduler setting learning rate to 0.001035625517812759.
390/390 [==============================] - 45s 114ms/step - loss: 0.4255 - acc: 0.8524 - val_loss: 0.5516 - val_acc: 0.8163
Epoch 14/50

Epoch 00014: LearningRateScheduler setting learning rate to 0.0009714396735962696.
390/390 [==============================] - 45s 115ms/step - loss: 0.4256 - acc: 0.8505 - val_loss: 0.5868 - val_acc: 0.8051
Epoch 15/50

Epoch 00015: LearningRateScheduler setting learning rate to 0.0009147457006952067.
390/390 [==============================] - 45s 115ms/step - loss: 0.4174 - acc: 0.8535 - val_loss: 0.5446 - val_acc: 0.8189
Epoch 16/50

Epoch 00016: LearningRateScheduler setting learning rate to 0.000864304235090752.
390/390 [==============================] - 45s 115ms/step - loss: 0.4159 - acc: 0.8538 - val_loss: 0.5185 - val_acc: 0.8224
Epoch 17/50

Epoch 00017: LearningRateScheduler setting learning rate to 0.00081913499344692.
390/390 [==============================] - 45s 115ms/step - loss: 0.4080 - acc: 0.8586 - val_loss: 0.5621 - val_acc: 0.8115
Epoch 18/50

Epoch 00018: LearningRateScheduler setting learning rate to 0.0007784524365561264.
390/390 [==============================] - 45s 114ms/step - loss: 0.4147 - acc: 0.8539 - val_loss: 0.5771 - val_acc: 0.8010
Epoch 19/50

Epoch 00019: LearningRateScheduler setting learning rate to 0.0007416196974191634.
390/390 [==============================] - 45s 115ms/step - loss: 0.3993 - acc: 0.8597 - val_loss: 0.5471 - val_acc: 0.8135
Epoch 20/50

Epoch 00020: LearningRateScheduler setting learning rate to 0.0007081149978756551.
390/390 [==============================] - 45s 115ms/step - loss: 0.4076 - acc: 0.8568 - val_loss: 0.5557 - val_acc: 0.8097
Epoch 21/50

Epoch 00021: LearningRateScheduler setting learning rate to 0.0006775067750677507.
390/390 [==============================] - 45s 114ms/step - loss: 0.4027 - acc: 0.8596 - val_loss: 0.5724 - val_acc: 0.8089
Epoch 22/50

Epoch 00022: LearningRateScheduler setting learning rate to 0.0006494349915573452.
390/390 [==============================] - 45s 115ms/step - loss: 0.4013 - acc: 0.8568 - val_loss: 0.5423 - val_acc: 0.8172
Epoch 23/50

Epoch 00023: LearningRateScheduler setting learning rate to 0.0006235969069593414.
390/390 [==============================] - 45s 115ms/step - loss: 0.3993 - acc: 0.8604 - val_loss: 0.5313 - val_acc: 0.8188
Epoch 24/50

Epoch 00024: LearningRateScheduler setting learning rate to 0.0005997361161089121.
390/390 [==============================] - 45s 115ms/step - loss: 0.4003 - acc: 0.8593 - val_loss: 0.5572 - val_acc: 0.8142
Epoch 25/50

Epoch 00025: LearningRateScheduler setting learning rate to 0.000577634011090573.
390/390 [==============================] - 45s 115ms/step - loss: 0.3990 - acc: 0.8609 - val_loss: 0.5793 - val_acc: 0.8052
Epoch 26/50

Epoch 00026: LearningRateScheduler setting learning rate to 0.0005571030640668523.
390/390 [==============================] - 45s 115ms/step - loss: 0.3955 - acc: 0.8606 - val_loss: 0.5062 - val_acc: 0.8310
Epoch 27/50

Epoch 00027: LearningRateScheduler setting learning rate to 0.0005379814934366257.
390/390 [==============================] - 45s 115ms/step - loss: 0.3921 - acc: 0.8629 - val_loss: 0.5273 - val_acc: 0.8189
Epoch 28/50

Epoch 00028: LearningRateScheduler setting learning rate to 0.0005201289919900136.
390/390 [==============================] - 45s 115ms/step - loss: 0.3916 - acc: 0.8620 - val_loss: 0.5271 - val_acc: 0.8220
Epoch 29/50

Epoch 00029: LearningRateScheduler setting learning rate to 0.0005034232782923882.
390/390 [==============================] - 45s 115ms/step - loss: 0.3910 - acc: 0.8625 - val_loss: 0.5372 - val_acc: 0.8178
Epoch 30/50

Epoch 00030: LearningRateScheduler setting learning rate to 0.000487757291971515.
390/390 [==============================] - 45s 115ms/step - loss: 0.3930 - acc: 0.8631 - val_loss: 0.5420 - val_acc: 0.8188
Epoch 31/50

Epoch 00031: LearningRateScheduler setting learning rate to 0.0004730368968779565.
390/390 [==============================] - 45s 115ms/step - loss: 0.3897 - acc: 0.8629 - val_loss: 0.5370 - val_acc: 0.8177
Epoch 32/50

Epoch 00032: LearningRateScheduler setting learning rate to 0.00045917898796951054.
390/390 [==============================] - 45s 115ms/step - loss: 0.3832 - acc: 0.8648 - val_loss: 0.5553 - val_acc: 0.8116
Epoch 33/50

Epoch 00033: LearningRateScheduler setting learning rate to 0.0004461099214846538.
390/390 [==============================] - 45s 115ms/step - loss: 0.3873 - acc: 0.8642 - val_loss: 0.5285 - val_acc: 0.8217
Epoch 34/50

Epoch 00034: LearningRateScheduler setting learning rate to 0.0004337642057777392.
390/390 [==============================] - 45s 115ms/step - loss: 0.3821 - acc: 0.8645 - val_loss: 0.5403 - val_acc: 0.8182
Epoch 35/50

Epoch 00035: LearningRateScheduler setting learning rate to 0.0004220834036805673.
390/390 [==============================] - 45s 115ms/step - loss: 0.3833 - acc: 0.8658 - val_loss: 0.5244 - val_acc: 0.8221
Epoch 36/50

Epoch 00036: LearningRateScheduler setting learning rate to 0.0004110152075626798.
390/390 [==============================] - 45s 115ms/step - loss: 0.3835 - acc: 0.8643 - val_loss: 0.5589 - val_acc: 0.8149
Epoch 37/50

Epoch 00037: LearningRateScheduler setting learning rate to 0.0004005126561999359.
390/390 [==============================] - 45s 115ms/step - loss: 0.3756 - acc: 0.8677 - val_loss: 0.5348 - val_acc: 0.8173
Epoch 38/50

Epoch 00038: LearningRateScheduler setting learning rate to 0.00039053346871826915.
390/390 [==============================] - 45s 115ms/step - loss: 0.3823 - acc: 0.8659 - val_loss: 0.5453 - val_acc: 0.8176
Epoch 39/50

Epoch 00039: LearningRateScheduler setting learning rate to 0.00038103947568968145.
390/390 [==============================] - 45s 115ms/step - loss: 0.3750 - acc: 0.8687 - val_loss: 0.5350 - val_acc: 0.8187
Epoch 40/50

Epoch 00040: LearningRateScheduler setting learning rate to 0.0003719961312402351.
390/390 [==============================] - 45s 115ms/step - loss: 0.3830 - acc: 0.8668 - val_loss: 0.5336 - val_acc: 0.8204
Epoch 41/50

Epoch 00041: LearningRateScheduler setting learning rate to 0.0003633720930232558.
390/390 [==============================] - 45s 115ms/step - loss: 0.3782 - acc: 0.8669 - val_loss: 0.5633 - val_acc: 0.8120
Epoch 42/50

Epoch 00042: LearningRateScheduler setting learning rate to 0.00035513885929398396.
390/390 [==============================] - 45s 115ms/step - loss: 0.3736 - acc: 0.8680 - val_loss: 0.5206 - val_acc: 0.8240
Epoch 43/50

Epoch 00043: LearningRateScheduler setting learning rate to 0.0003472704542297541.
390/390 [==============================] - 45s 115ms/step - loss: 0.3801 - acc: 0.8664 - val_loss: 0.5479 - val_acc: 0.8173
Epoch 44/50

Epoch 00044: LearningRateScheduler setting learning rate to 0.00033974315417544334.
390/390 [==============================] - 45s 115ms/step - loss: 0.3740 - acc: 0.8679 - val_loss: 0.5428 - val_acc: 0.8191
Epoch 45/50

Epoch 00045: LearningRateScheduler setting learning rate to 0.00033253524873636604.
390/390 [==============================] - 45s 115ms/step - loss: 0.3755 - acc: 0.8695 - val_loss: 0.5388 - val_acc: 0.8210
Epoch 46/50

Epoch 00046: LearningRateScheduler setting learning rate to 0.00032562683165092806.
390/390 [==============================] - 45s 115ms/step - loss: 0.3707 - acc: 0.8689 - val_loss: 0.5276 - val_acc: 0.8234
Epoch 47/50

Epoch 00047: LearningRateScheduler setting learning rate to 0.0003189996172004594.
390/390 [==============================] - 45s 115ms/step - loss: 0.3716 - acc: 0.8695 - val_loss: 0.5370 - val_acc: 0.8194
Epoch 48/50

Epoch 00048: LearningRateScheduler setting learning rate to 0.0003126367785906334.
390/390 [==============================] - 45s 115ms/step - loss: 0.3741 - acc: 0.8656 - val_loss: 0.5433 - val_acc: 0.8185
Epoch 49/50

Epoch 00049: LearningRateScheduler setting learning rate to 0.00030652280529671407.
390/390 [==============================] - 45s 115ms/step - loss: 0.3729 - acc: 0.8693 - val_loss: 0.5302 - val_acc: 0.8222
Epoch 50/50

Epoch 00050: LearningRateScheduler setting learning rate to 0.0003006433768264085.
390/390 [==============================] - 45s 115ms/step - loss: 0.3731 - acc: 0.8694 - val_loss: 0.5294 - val_acc: 0.8207
Model took 2246.51 seconds to train

Accuracy on test data is: 82.07

