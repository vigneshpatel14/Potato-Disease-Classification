# Potato Disease Classification

## Setup for Python:

1. Install Python ([Setup instructions](https://wiki.python.org/moin/BeginnersGuide))

2. Install Python packages

```
pip3 install -r training/requirements.txt
pip3 install -r api/requirements.txt
```

3. Install Tensorflow Serving ([Setup instructions](https://www.tensorflow.org/tfx/serving/setup))

## Setup for ReactJS

1. Install Nodejs ([Setup instructions](https://nodejs.org/en/download/package-manager/))
2. Install NPM ([Setup instructions](https://www.npmjs.com/get-npm))
3. Install dependencies

```bash
cd frontend
npm install --from-lock-json
npm audit fix
```

4. Copy `.env.example` as `.env`.

5. Change API url in `.env`.


## Training the Model

1. Download the data from [kaggle](https://www.kaggle.com/arjuntejaswi/plant-village).
2. Only keep folders related to Potatoes.
3. Run Jupyter Notebook in Browser.

```bash
jupyter notebook
```

4. Open `training/potato-disease-training.ipynb` in Jupyter Notebook.
5. In cell #2, update the path to dataset.
6. Run all the Cells one by one.
7. Copy the model generated and save it with the version number in the `models` folder.

## Running the API

### Using FastAPI

1. Get inside `api` folder

```bash
cd api
```

2. Run the FastAPI Server using uvicorn

```bash
uvicorn main:app --reload --host 0.0.0.0
```

3. Your API is now running at `0.0.0.0:8000`

### Using FastAPI & TF Serve

1. Get inside `api` folder

```bash
cd api
```


4. Run the FastAPI Server using uvicorn
   For this you can directly run it from your main.py or main-tf-serving.py using pycharm run option
   OR you can run it from command prompt as shown below,

```bash
uvicorn main-tf-serving:app --reload --host 0.0.0.0
```

5. Your API is now running at `0.0.0.0:8000`

## Running the Frontend

1. Get inside `api` folder

```bash
cd frontend
```

2. Copy the `.env.example` as `.env` and update `REACT_APP_API_URL` to API URL if needed.
3. Run the frontend

```bash
npm run start
```
## Creating the TF Lite Model

1. Run Jupyter Notebook in Browser.

```bash
jupyter notebook
```

2. Open `training/tf-lite-converter.ipynb` in Jupyter Notebook.
3. In cell #2, update the path to dataset.
4. Run all the Cells one by one.
5. Model would be saved in `tf-lite-models` folder.

Inspiration: https://cloud.google.com/blog/products/ai-machine-learning/how-to-serve-deep-learning-models-using-tensorflow-2-0-with-cloud-functions

