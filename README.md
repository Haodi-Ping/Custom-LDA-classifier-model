# Custom-LDA-classifier-model
Custom LDA classifier model via bentoml.picklable_model


This example is based on https://github.com/eriklindernoren/ML-From-Scratch

bentoml.picklable_model represents a generic model type in BentoML, that uses cloudpickle for model serialization under the hood. Most pure python code based ML model implementation should work with bentoml.picklable_model out-of-the-box.

We use google cloud functions to execute main.py/main functionality

First, install the required packages in requirements.txt, constaining scikit-learn and bentoml dependency packages.

Second, write main.py/main as the serverless functions

Finally, configure gcloud CLI to deploy and call the functionality

Specific details:

gcloud functions deploy fun_mame --entry-point main --runtime python38 --source App/ --trigger-http --allow-unauthenticated

gcloud functions call fun_mame
