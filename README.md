# Webapp_shiny_python

This repo consist of web app designed and developed using [shiny for python](https://shiny.rstudio.com/py/) library by RStudio. 

A web application to show the project structure for a deep learning model deployed using shiny has been developed.

The deep learning model was built using Tensorflow/Keras:

* Convolutional Neural Netwok
* Min Max Scaler 

Each of these components are developed within the project in an offline setting inside `/model`. 
The Neural Network and Min-Max scaler models will still be needed in a production 
or testing setting in order to be able to predict user-submitted queries, 
so they can be serialized via python's pickle functionality and stored within the `/model` folder.


## Installation

Create a conda virtual environment in the project directory.

```
conda create -n venv python=3.9
```

Activate the virtual environment.
```
conda activate venv
```

While in the virtual environment, install required dependencies from `requirements.txt`.

```
pip install -r requirements.txt
```

Now we can deploy the web application via

```
shiny run app.py
```

and navigate to `http://127.0.0.1:8000/` to see it live. On this page, a user can then submit different features from UI into the drop down and slider 
input field and get the predictions from the trained model in the form of probability of annual earning more than 50k.

[![Alt text](images/uned_image.png)](https://www.youtube.com/watch?v=oTc1yVZlrIU&t=4s)

The application may then be terminated with the following commands.
```
ctrl - c
```

## Project Structure 

~~~
Example_webapp_shiny_python

├── data
├── images
├── notebooks
├── model
│   ├── nn_model.pkl
│   └── normalize.pkl
├── app.py
├── _utils.py
├── aux_params.py
├── requirements.txt
└── README.md
