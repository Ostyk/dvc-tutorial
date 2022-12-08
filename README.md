# dvc-tutorial

This tutorial is based on https://dvc.org/doc/use-cases/versioning-data-and-models/tutorial  with the source code for training models ported to Pytorch.

## Install

This installation guide is for Linux based system and requires Python 3.8+. For other platforms please refer to https://dvc.org/doc/install

- VSC extension: `ext install Iterative.dvc`

## Tutorial Steps

**Step 1:** Clone this repository
```
git clone https://github.com/Ostyk/dvc-tutorial.git
cd dvc-tutorial
```

**Step 2:** Install virutalenv

This installs dvc using pip
```
python3 -m venv env
source env/bin/activate
pip3 install --upgrade pip
```

Install packages that aren't the same across platforms

```
pip3 install dvc
pip3 install torch torchvision torchaudio
```

Install the rest

```
pip install -r requirements.txt
```
**Step 3:** Get data from existing data registry
```
dvc get https://github.com/iterative/dataset-registry tutorials/versioning/data.zip
unzip -q data.zip
rm -f data.zip
```
**Step 4:** Train model

```jupyter notebook``` and train with  `CatDogClassifier.ipynb`

**Step 5:** Add data and model to dvc

```
dvc add data
```

You can also add metrics, log files, plots etc.
```
dvc add model_epoch_2.pth
```

**Step 5:** Version current state




**Step 6:** Train another 2nd Model version
Simply train another model using additional data:

#### Get addtionals data:
```
dvc get https://github.com/iterative/dataset-registry \
          tutorials/versioning/new-labels.zip
unzip -q new-labels.zip
rm -f new-labels.zip
```
#### Add data to DVC, train model and add new model:

1. Train model using jupyter notebook
2.  ```
    dvc add data
    dvc add model_epoch_2.pth
    ```

**Step 7:**
Switching between workspaces:
### Full:

```
git checkout v1.0
dvc checkout
```

### On the other hand, if we want to keep the current code, but go back to the previous dataset version, we can target specific data, like this:

```
git checkout v1.0 data.dvc
dvc checkout data.dvc
```



# Useful Links:
- More in depth tutorial: https://dvc.org/doc/use-cases/versioning-data-and-models/tutorial
- Slideshow (DAC.Digital employees only for now): https://docs.google.com/presentation/d/1qS6ouyFTiBdr0a0zKrpWW8S1baJek7gweYJYBHjnuo4/edit?usp=sharing
- No code explanation: https://www.youtube.com/watch?v=UbL7VUpv1Bs
- data registry: https://github.com/iterative/dataset-registry