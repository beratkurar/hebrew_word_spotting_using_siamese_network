# hebrew_word_spotting_using_siamese_network

### Installations for running keras-tensoflow on GPU
1. Upgrade pip and install opencv2
```
cd ~
pip install --upgrade pip
pip install opencv-python
```
2. Upgrade keras and set tensorflow background
```
pip uninstall keras
pip install keras==2.1.2
pip uninstall python-dateutil
pip install python-dateutil
vi ~/.keras/keras.json
  {
    "backend": "tensorflow",
    "image_data_format": "channels_last",
    "floatx": "float32",
    "epsilon": 1e-07
  }
```
3. Uninstall tensorflow and install tensorflow-gpu which is necessary to run on GPU
```
pip uninstall tensorflow
pip install tensorflow-gpu==1.2
```
5. Run python on a specific GPU
```
import os
os.environ["CUDA_VISIBLE_DEVICES"]="2"
```

### How to run the project
1. Download the [Pinkas dataset](https://www.cs.bgu.ac.il/~berat/)
2. Balance train set at 30 samples
```
python3 balance_train.ipynb
```
2. Train siamese network on 100 same pairs and 100 different pairs from each class
```
pinkas_siamese_random_pairs.ipynb
```
3. Train siamese network on hard pairs
```
pinkas_siamese_hard_pairs.ipynb
```


