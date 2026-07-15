python3 -c "import requests; print('requests OK')"
python3 -c "import phonenumbers; print('phonenumbers OK')"
python3 -c "import bs4; print('bs4 OK')"
python3 -c "import cryptography; print('crypto OK')"   # Sering jadi penyebab
python3 -c "import PIL; print('PIL OK')"               # Sering jadi penyebab


python3 -c "import cryptography"      # jika ada
python3 -c "import lxml"              # jika ada
python3 -c "import PIL"               # jika ada
python3 -c "import numpy"             # jika ada
python3 -c "import cv2"               # jika ada
python3 -c "import yaml"              # jika ada



curl -fsSL https://pyenv.run | bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
source ~/.zshrc

pyenv install 3.11.9

cd ~/Downloads/Xtrack
pyenv local 3.11.9

deactivate   
rm -rf venv
python -m venv venv
source venv/bin/activate

pip install --upgrade pip setuptools wheel
pip install -r requirements.txt   

python Xtrack.py
