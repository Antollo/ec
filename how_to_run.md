# How to install on clean Ubuntu

Generate a new SSH key (git submodules have SSH based urls)

```
ssh-keygen -t ed25519 -C "abc@xyz.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
```

Install dependencies

```
sudo apt update
sudo apt install swig build-essential imagemagick feh libzmq3-dev graphviz
```

Install conda and reopen shell to take effect

```
wget https://repo.anaconda.com/miniconda/Miniconda3-py37_22.11.1-1-Linux-x86_64.sh
bash Miniconda3-py37_22.11.1-1-Linux-x86_64.sh
```

Clone repo

```
git clone --depth 1 https://github.com/Antollo/ec
cd ec
git submodule update --recursive --init
```

Initialize conda environment

```
conda env create -f environment.yml
conda activate DreamCoder
```