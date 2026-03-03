1. Create a folder that contains this repository and the libero repository.


3. Create a conda virtual environment
conda create -n libero python=3.8.13
conda activate libero

4. Install requirements
pip3 install -r LIBERO/requirements.txt
pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113

