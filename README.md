# Waveglow library

This Waveglow library was changed to be used with vait library.


## Instalation

### 1) Install waveglow library

(This will also install tacotron2 library)

```shell
pip install waveglow==22.12.28
```


### 2) Install CUDA 11.3 or 11.6

```shell
pip install -r requirements-cuda-11.3.txt
# or
pip install -r requirements-cuda-11.6.txt
```


### 3) Install apex
```shell
git clone https://github.com/NVIDIA/apex /home/${USER}/apex
cd /home/${USER}/apex
pip install -v --disable-pip-version-check --no-cache-dir ./
cd -
```


### 4) Download published model files

```shell
wget https://drive.google.com/open?id=1rpK8CzAAirq9sWZhe9nlfvxMF1dRgFbF
```


### 5) Download mel-spectrograms

```shell
wget https://drive.google.com/file/d/1g_VXK2lpP9J25dQFhQwx7doWl_p20fXA/view?usp=sharing
```


## Usage: Creating audio

```shell
waveglow-inference -f <(ls mel_spectrograms/*.pt) -w waveglow_256channels_universal_v5.pt -o . --is_fp16 -s 0.6
```


## Usage: Training

```shell
mkdir checkpoints
waveglow-train -c config.json
```
