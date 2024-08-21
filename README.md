# DSC Challange
 
## Model file(s)

Since the files are considered to be large by git, files can be downloaded on this url:

``
https://drive.google.com/drive/folders/10KitDcOeGgmdKqj50BwrQNYXRx3v-6Uv?usp=sharing
``

Put the model files to the **model-deploy-learn/models/**, you can choose any;

Files in the link as in .h5 or .p formats.

## Prerequisites  & Installing
 
 
Create conda env:
 
 
``
conda create --n openai_env python=3.9
``
 
Activate env:
 
 
``
conda activate openai_env
``
 
Install All Depedencies :
 
``
pip install -r requirements.txt
``
 
Run :
 
``
uvicorn main:app --reload --log-level debug --port 8200
``