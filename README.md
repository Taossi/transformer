# **** A TensorFlow Implementation of [Attention Is All You Need](https://arxiv.org/abs/1706.03762)


## Requirements
* python==3.x
* tensorflow==1.14.0
* numpy>=1.15.4
* sentencepiece==0.1.8
* tqdm>=4.28.1

## Training
* STEP 1. Run the command below to download [IWSLT 2016 German–English parallel corpus](https://wit3.fbk.eu/download.php?release=2016-01&type=texts&slang=de&tlang=en).
```
bash download.sh
```
 It should be extracted to `iwslt2016/de-en` folder automatically.
* STEP 2. Run the command below to create preprocessed train/eval/test data.
```
python prepro.py
```
If you want to change the vocabulary size (default:32000), do this.
```
python prepro.py --vocab_size 8000
```
It should create two folders `iwslt2016/prepro` and `iwslt2016/segmented`.

* STEP 3. Run the following command.
```
python train.py
```



## test
* Run
```
python test.py --ckpt log/1/iwslt2016_E20L2.54-30580 
```

## Results
* Typically, machine translation is evaluated with Bleu score.

|tst2013 (dev) | tst2014 (test) |
|--|--|
|27.02|24.01|

