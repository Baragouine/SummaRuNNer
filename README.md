# SummaRuNNer

## Clone project
```bash
git clone https://github.com/Baragouine/SummaRuNNer.git
```

## Create environnement
```bash
conda create --name SummaRuNNer python=3.9
```

## Activate environnement
```bash
conda activate SummaRuNNer
```

## Install dependencies
```bash
pip install -r requirements.txt
```

## Convert initial dataset to valid pandas json
Download the [initial dataset](https://drive.google.com/file/d/1JgsboIAs__r6XfCbkDWgmberXJw8FBWE/view?usp=sharing).  
Copy train.json, val.json and test.json to `./data/ref` .  
Run the python script: `convert_ref_data_to_raw_data.py`:
```bash
python3 ./convert_ref_data_to_raw_data.py
```

## Compute own labels
```bash
python3 ./compute_own_labels_from_raw_data.py
```

## Eval RNN_RNN
accuracy = 0.7947603395657316+/-0.0003403645399815157
rouge1 = 0.2952507457561455+/-0.0006882599953940415
rouge2 = 0.15091452229881022+/-0.000400575299884331
rougeL = 0.198735038961782+/-0.0005179696499819547

## Batch size influences on RNN_RNN
### Batch 8
 * Training time: 28467 s (474.45 min ou 7.9 h)  
 * Test Accuracy: 0.795   
 * Test Rouge 1: 0.293  
 * Test Rouge 2: 0.150 
 * Test Rouge L: 0.198

### Batch 16
 * Training time: 25016 s (416.93 min ou 6.95 h)  
 * Test Accuracy: 0.795  
 * Test Rouge 1: 0.295  
 * Test Rouge 2: 0.151
 * Test Rouge L: 0.199

### Batch 32
 * Training time: 21712 s (361.87 min ou 6.03 h)  
 * Test Accuracy: 0.795  
 * Test Rouge 1: 0.296  
 * Test Rouge 2: 0.151  
 * Test Rouge L: 0.199  

### Batch 64
 * Training time: 21924 s (365.4 min ou 6.09 h)  
 * Test Accuracy: 0.794  
 * Test Rouge 1: 0.296  
 * Test Rouge 2: 0.151
 * Test Rouge L: 0.199
