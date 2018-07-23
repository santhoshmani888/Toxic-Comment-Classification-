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
