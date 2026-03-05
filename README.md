# LIBERO Setup

This section documents the full setup process used to run the `quick_guide_algo.ipynb` notebook from the LIBERO repository. It includes cloning the repository, creating a Conda environment, installing dependencies, and resolving common installation issues encountered during setup.

---

## 1. Clone the Repository

```bash
git clone https://github.com/Lifelong-Robot-Learning/LIBERO.git
cd LIBERO
```

## 2. Create a Conda Environment
```bash
conda create -n py3813 python=3.8.13
conda activate py3813
```
Verify:
```bash
python --version
```
Expected output:
```bash
Python 3.8.13
```
## 3. Install Jupyter and Register the Kernel
```bash
pip install notebook ipykernel
python -m ipykernel install --user --name py3813 --display-name "Python (py3813)"
```
Start Jupyter:
```bash
jupyter notebook
```
In the notebook interface select:
```bash
Kernel → Change Kernel → Python (py3813)
```
## 4. Install LIBERO as a Local Package
From the repository root:
```bash
pip install -e .
```
Verify:
```bash
python -c "import libero; print(list(getattr(libero,'__path__',[])))"
```
## 5. Install Core Dependencies
Some dependencies require manual installation.
```bash
pip install hydra-core
pip install omegaconf
pip install easydict
conda install -c conda-forge pytorch torchvision
conda install -c conda-forge h5py
pip install requests
```
Verify:
```bash
python -c "import torch; print(torch.__version__)"
```
## 6. Fix Broken charset_normalizer Installation
```bash
pip uninstall -y charset-normalizer charset_normalizer requests

pip install --no-cache-dir --force-reinstall \
"charset-normalizer==2.0.12" \
"requests==2.27.1"
```
Verify:
```bash
python -c "import charset_normalizer, requests; print(charset_normalizer.__version__, requests.__version__)"
```
## 7. Install Dataset Dependencies
```bash
conda install -c conda-forge h5py pillow tqdm
```
## 8. Run the Notebook
```bash
jupyter notebook
```
Open:
```bash
notebooks/quick_guide_algo.ipynb
```
Ensure kernel:
```bash
Python (py3813)
```
## Note: LIBERO demonstration datasets must be downloaded separately. 
## Use my env
```bash
conda env create -f environment.yml
```










