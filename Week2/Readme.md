# Week2 

# Approach 

1) Stacked 2 Conolution networks with the below blocks 
- Block 1 : 2(16,3,3)
- Block 2 : 1(10,3,3) & 3(16,3,3)
- Transition Layer : 1(10,4,4)

# Validaiton Score

Model: "sequential_1"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_1 (Conv2D)            (None, 26, 26, 16)        144       
_________________________________________________________________
batch_normalization_1 (Batch (None, 26, 26, 16)        64        
_________________________________________________________________
dropout_1 (Dropout)          (None, 26, 26, 16)        0         
_________________________________________________________________
conv2d_2 (Conv2D)            (None, 24, 24, 16)        2304      
_________________________________________________________________
batch_normalization_2 (Batch (None, 24, 24, 16)        64        
_________________________________________________________________
dropout_2 (Dropout)          (None, 24, 24, 16)        0         
_________________________________________________________________
conv2d_3 (Conv2D)            (None, 24, 24, 10)        160       
_________________________________________________________________
max_pooling2d_1 (MaxPooling2 (None, 12, 12, 10)        0         
_________________________________________________________________
conv2d_4 (Conv2D)            (None, 10, 10, 10)        900       
_________________________________________________________________
batch_normalization_3 (Batch (None, 10, 10, 10)        40        
_________________________________________________________________
dropout_3 (Dropout)          (None, 10, 10, 10)        0         
_________________________________________________________________
conv2d_5 (Conv2D)            (None, 8, 8, 16)          1440      
_________________________________________________________________
batch_normalization_4 (Batch (None, 8, 8, 16)          64        
_________________________________________________________________
dropout_4 (Dropout)          (None, 8, 8, 16)          0         
_________________________________________________________________
conv2d_6 (Conv2D)            (None, 6, 6, 16)          2304      
_________________________________________________________________
batch_normalization_5 (Batch (None, 6, 6, 16)          64        
_________________________________________________________________
dropout_5 (Dropout)          (None, 6, 6, 16)          0         
_________________________________________________________________
conv2d_7 (Conv2D)            (None, 4, 4, 16)          2304      
_________________________________________________________________
batch_normalization_6 (Batch (None, 4, 4, 16)          64        
_________________________________________________________________
dropout_6 (Dropout)          (None, 4, 4, 16)          0         
_________________________________________________________________
conv2d_8 (Conv2D)            (None, 1, 1, 10)          2560      
_________________________________________________________________
batch_normalization_7 (Batch (None, 1, 1, 10)          40        
_________________________________________________________________
global_average_pooling2d_1 ( (None, 10)                0         
_________________________________________________________________
activation_1 (Activation)    (None, 10)                0         
=================================================================
Total params: 12,516
Trainable params: 12,316
Non-trainable params: 200
_________________________________________________________________

# Log 

WARNING:tensorflow:From /usr/local/lib/python3.6/dist-packages/keras/optimizers.py:793: The name tf.train.Optimizer is deprecated. Please use tf.compat.v1.train.Optimizer instead.

WARNING:tensorflow:From /usr/local/lib/python3.6/dist-packages/keras/backend/tensorflow_backend.py:3576: The name tf.log is deprecated. Please use tf.math.log instead.

WARNING:tensorflow:From /usr/local/lib/python3.6/dist-packages/tensorflow_core/python/ops/math_grad.py:1424: where (from tensorflow.python.ops.array_ops) is deprecated and will be removed in a future version.
Instructions for updating:
Use tf.where in 2.0, which has the same broadcast rule as np.where
WARNING:tensorflow:From /usr/local/lib/python3.6/dist-packages/keras/backend/tensorflow_backend.py:1033: The name tf.assign_add is deprecated. Please use tf.compat.v1.assign_add instead.

WARNING:tensorflow:From /usr/local/lib/python3.6/dist-packages/keras/backend/tensorflow_backend.py:1020: The name tf.assign is deprecated. Please use tf.compat.v1.assign instead.

Train on 60000 samples, validate on 10000 samples
Epoch 1/20

Epoch 00001: LearningRateScheduler setting learning rate to 0.003.
60000/60000 [==============================] - 14s 230us/step - loss: 0.4498 - acc: 0.8983 - val_loss: 0.0860 - val_acc: 0.9831
Epoch 2/20

Epoch 00002: LearningRateScheduler setting learning rate to 0.002274450341167551.
60000/60000 [==============================] - 10s 170us/step - loss: 0.1179 - acc: 0.9756 - val_loss: 0.0556 - val_acc: 0.9875
Epoch 3/20

Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018315018317.
60000/60000 [==============================] - 10s 175us/step - loss: 0.0806 - acc: 0.9814 - val_loss: 0.0464 - val_acc: 0.9890
Epoch 4/20

Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586101175269.
60000/60000 [==============================] - 11s 175us/step - loss: 0.0669 - acc: 0.9834 - val_loss: 0.0346 - val_acc: 0.9906
Epoch 5/20

Epoch 00005: LearningRateScheduler setting learning rate to 0.001318101933216169.
60000/60000 [==============================] - 10s 172us/step - loss: 0.0572 - acc: 0.9850 - val_loss: 0.0347 - val_acc: 0.9901
Epoch 6/20

Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560693641618498.
60000/60000 [==============================] - 10s 170us/step - loss: 0.0523 - acc: 0.9861 - val_loss: 0.0337 - val_acc: 0.9905
Epoch 7/20

Epoch 00007: LearningRateScheduler setting learning rate to 0.001029512697323267.
60000/60000 [==============================] - 10s 174us/step - loss: 0.0470 - acc: 0.9871 - val_loss: 0.0287 - val_acc: 0.9921
Epoch 8/20

Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307145066501.
60000/60000 [==============================] - 11s 181us/step - loss: 0.0446 - acc: 0.9878 - val_loss: 0.0259 - val_acc: 0.9923
Epoch 9/20

Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445945945945946.
60000/60000 [==============================] - 11s 180us/step - loss: 0.0421 - acc: 0.9887 - val_loss: 0.0250 - val_acc: 0.9925
Epoch 10/20

Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935417204857.
60000/60000 [==============================] - 11s 179us/step - loss: 0.0412 - acc: 0.9889 - val_loss: 0.0252 - val_acc: 0.9924
Epoch 11/20

Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159904534606206.
60000/60000 [==============================] - 11s 182us/step - loss: 0.0378 - acc: 0.9892 - val_loss: 0.0223 - val_acc: 0.9935
Epoch 12/20

Epoch 00012: LearningRateScheduler setting learning rate to 0.0006653359946773121.
60000/60000 [==============================] - 11s 178us/step - loss: 0.0358 - acc: 0.9899 - val_loss: 0.0223 - val_acc: 0.9935
Epoch 13/20

Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753106876554.
60000/60000 [==============================] - 11s 176us/step - loss: 0.0349 - acc: 0.9898 - val_loss: 0.0221 - val_acc: 0.9929
Epoch 14/20

Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638041577617.
60000/60000 [==============================] - 11s 180us/step - loss: 0.0333 - acc: 0.9901 - val_loss: 0.0217 - val_acc: 0.9940
Epoch 15/20

Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474204171241.
60000/60000 [==============================] - 11s 184us/step - loss: 0.0325 - acc: 0.9907 - val_loss: 0.0216 - val_acc: 0.9939
Epoch 16/20

Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825410544512.
60000/60000 [==============================] - 11s 185us/step - loss: 0.0307 - acc: 0.9912 - val_loss: 0.0210 - val_acc: 0.9939
Epoch 17/20

Epoch 00017: LearningRateScheduler setting learning rate to 0.000491480996068152.
60000/60000 [==============================] - 11s 186us/step - loss: 0.0304 - acc: 0.9914 - val_loss: 0.0224 - val_acc: 0.9940
Epoch 18/20

Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670714619336759.
60000/60000 [==============================] - 11s 185us/step - loss: 0.0285 - acc: 0.9918 - val_loss: 0.0222 - val_acc: 0.9930
Epoch 19/20

Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718184514981.
60000/60000 [==============================] - 11s 182us/step - loss: 0.0303 - acc: 0.9912 - val_loss: 0.0220 - val_acc: 0.9937
Epoch 20/20

Epoch 00020: LearningRateScheduler setting learning rate to 0.00042486899872539303.
60000/60000 [==============================] - 11s 186us/step - loss: 0.0285 - acc: 0.9919 - val_loss: 0.0219 - val_acc: 0.9937
<keras.callbacks.History at 0x7f9a0067bc88>
