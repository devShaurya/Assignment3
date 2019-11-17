# Assignment3
## Preprocessing:
For preprocessing, all the user tags(ones with @), hashtags(ones with #), alpha-numerical terms are removed and only pure hindi and English terms are kept for further processing. 
## Embeddings

The embeddings are used from the flair library which itself uses pretrained bert embeddings and are of the size 31*/3072. These are set as training and testing after padding all embeddings equally.

## Model:

The model consists of bidirection layer followed by a droput layer with rate of 0.2 and then a self attention layer with attention width of 15. This layer is followed by dense layer then a gru and then a dropout layer with a rate of 0.2.
This is a followed by a Dense layer which gives a output vector of size 3*/1.
This is described by a table below.
Model: "sequential_1"1
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
_________________________________________________________________
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
_________________________________________________________________
Total params: 3,296,547
Trainable params: 3,296,547
Non-trainable params: 0

## Performance 
The performance of model is not as good as I expected but if it would have been given more epochs to train then it would have give a good response as self-attention network would have been able to memorize more.
The Output is described in following table:
Predicted  negative  neutral  positive
Actual                                
negative        402      110        21
neutral         322      334        98
positive        133      224       225


Accuracy:  0.5141787051899411

 Report:
              precision    recall  f1-score   support

    negative       0.47      0.75      0.58       533
     neutral       0.50      0.44      0.47       754
    positive       0.65      0.39      0.49       582

    accuracy                           0.51      1869
   macro avg       0.54      0.53      0.51      1869
weighted avg       0.54      0.51      0.51      1869




