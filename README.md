# Toxic-Comment-Classification-
classify comments into types of of toxicity like threats, obscenity, insults, and identity-based hate

data:https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data

LSTM model outline:
Layer (type)                 Output Shape              Param #   
=================================================================
input_2 (InputLayer)         (None, 300)               0         
_________________________________________________________________
embedding_2 (Embedding)      (None, 300, 128)          2560000   
_________________________________________________________________
lstm_layer (LSTM)            (None, 300, 50)           35800     
_________________________________________________________________
global_max_pooling1d_2 (Glob (None, 50)                0         
_________________________________________________________________
dropout_3 (Dropout)          (None, 50)                0         
_________________________________________________________________
dense_3 (Dense)              (None, 10)                510       
_________________________________________________________________
dropout_4 (Dropout)          (None, 10)                0         
_________________________________________________________________
dense_4 (Dense)              (None, 6)                 66        

CNN+BiLSTM+Glove

__________________________________________________________________________________________________
Layer (type)                    Output Shape         Param #     Connected to                     
==================================================================================================
input_9 (InputLayer)            (None, 300)          0                                            
__________________________________________________________________________________________________
embedding_20 (Embedding)        (None, 300, 300)     6000000     input_9[0][0]                    
__________________________________________________________________________________________________
conv1d_19 (Conv1D)              (None, 300, 30)      27030       embedding_20[0][0]               
__________________________________________________________________________________________________
dropout_14 (Dropout)            (None, 300, 30)      0           conv1d_19[0][0]                  
__________________________________________________________________________________________________
bidirectional_7 (Bidirectional) (None, 300, 400)     369600      dropout_14[0][0]                 
__________________________________________________________________________________________________
global_average_pooling1d_7 (Glo (None, 400)          0           bidirectional_7[0][0]            
__________________________________________________________________________________________________
global_max_pooling1d_7 (GlobalM (None, 400)          0           bidirectional_7[0][0]            
__________________________________________________________________________________________________
concatenate_7 (Concatenate)     (None, 800)          0           global_average_pooling1d_7[0][0] 
                                                                 global_max_pooling1d_7[0][0]     
__________________________________________________________________________________________________
dense_14 (Dense)                (None, 6)            4806        concatenate_7[0][0]              
==================================================================================================
Total params: 6,401,436
Trainable params: 6,401,436
Non-trainable params: 0
