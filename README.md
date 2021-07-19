# KISTI_GUNet_classification_README
## Requirement
---
- pytorch (https://pytorch.org/)
- tqdm (https://pypi.org/project/tqdm/)
- sklearn (https://scikit-learn.org/stable/install.html)
- GLIBCX_3.4.22
---
## Usage
---
```
bash run_GUNet_KISTI.sh dataname fold gpu testname
```
#### &emsp;or
```
python bin/KISTI_GUnet.py rootpath -data [data folder] -data_name [data_name] -fold [CV fold] -learning_rate [learning_rate] -num_epochs [num_epochs] -hidden [hidden layer dim] -latent_dim [latend layer dim] -sortpooling_k [number of nodes kept after SortPooling] -out_dim [output dim] -dropout [True or False] -mode [gpu or cpu] 
```
# Required argument
- dataname : input data name
- fold : cross validation fold 
- gpu : gpu number
- testname : data test graph

# optional argument
- learning_rate [learning rate]
- num_epochs [number of epochs]
- hidden [hidden layer dim]
- latent_dim [latend layer dim] 
- sortpooling_k [number of nodes kept after SortPooling]
- out_dim [output dim]
- dropout [True or False]
- mode [gpu or cpu] 

## example
---
```
bash run_GUNet_KISTI.sh obesity 1 0 test1
```

---
# output
- classification accuracy [~/output/graph_train_acc_1_fold.npy]
