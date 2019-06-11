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
1. Crop words from a book in [VML dataset](https://www.cs.bgu.ac.il/~majeek/)
```
python3 DatasetMaker.py
```
2. Rename folders
```
python3 DatasetOutsideRenamer.py
```
3. Create validation set
```
python3 10selector.py
```
4. Create train set
```
python3 20selector.py
```
5. Create out of vocabulary (OOV) test set
```
python3 100selector.py
```
6. Train FCN and measure mAP on OOV test set
```
python3 vmlclmaxmap.py
```

