# dvc-tutorial


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
pip install -r requirements.txt
```
**Step 3:** Get data from existing data registry
```
dvc get https://github.com/iterative/dataset-registry \
          tutorials/versioning/new-labels.zip
unzip -q new-labels.zip
rm -f new-labels.zip
```

**Step 4:**

**Step 5:**
# Useful Links:
- Slideshow (DAC.Digital employees only for now): https://docs.google.com/presentation/d/1qS6ouyFTiBdr0a0zKrpWW8S1baJek7gweYJYBHjnuo4/edit?usp=sharing
- No code explanation: https://www.youtube.com/watch?v=UbL7VUpv1Bs
- data registry: https://github.com/iterative/dataset-registry