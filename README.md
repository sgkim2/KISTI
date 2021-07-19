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

## input preprocessing
- Step 1 : fMRI preprocessing [1]
- Step 2 : extract ROI signal [2,3]
- Step 3 : make graph matrix (pearson correlation) [4]
- Step 4 : transform graph matrix to Graph Unet style Graph [5]
* step 1~3 vary depending on the user's data.

## example of Graph Unet style Graph (Step 4)

- example of one subject

<img src = "https://github.com/sgkim2/KISTI/blob/main/GUnet_input.png" width="70%" height="70%">

## example
---
```
bash run_GUNet_KISTI.sh obesity 1 0 test1
```

---
# output
- classification accuracy [~/output/graph_train_acc_1_fold.npy]

# reference 
- [1] Effective preprocessing procedures virtually eliminate distance-dependent motion artifacts in resting state FMRI
- [2] Sheirer's ROI (https://findlab.stanford.edu/functional_ROIs.html)
- [3] Using AFNI 3dmaskave (https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dmaskave.html)
- [4] pearson correlation (https://en.wikipedia.org/wiki/Pearson_correlation_coefficient)
- [5] Graph U-Nets (https://arxiv.org/pdf/1905.05178.pdf)
