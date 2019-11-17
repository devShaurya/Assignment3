# Assignment3
## Preprocessing:
For preprocessing, I am removing all the http links and @ and # are also removed. The langids were thought to be of no use 

## Model
Model: "sequential_1"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
bidirectional_1 (Bidirection (None, 31, 256)           3277824   
_________________________________________________________________
dropout_1 (Dropout)          (None, 31, 256)           0         
_________________________________________________________________
seq_self_attention_1 (SeqSel (None, 31, 256)           16449     
_________________________________________________________________
dense_1 (Dense)              (None, 31, 3)             771       
_________________________________________________________________
gru_1 (GRU)                  (None, 20)                1440      
_________________________________________________________________
dropout_2 (Dropout)          (None, 20)                0         
_________________________________________________________________
dense_2 (Dense)              (None, 3)                 63        
=================================================================
Total params: 3,296,547
Trainable params: 3,296,547
Non-trainable params: 0
