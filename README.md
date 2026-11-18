# RNN vs LSTM vs GRU: time-series forecasting

Student task: train an RNN, an LSTM and a GRU on a simple time series, compare their predictions, and report which model has the lowest RMSE.

## Project structure

```
rnn-lstm-gru-project/
├── README.md                          project description (this file)
├── requirements.txt                   Python packages for the notebook
├── vercel.json                        Vercel settings (serve the site/ folder)
├── .gitignore
├── notebooks/
│   └── RNN_LSTM_GRU_Time_Series.ipynb Colab notebook (Keras): the main solution
├── site/
│   └── index.html                     Web page deployed on Vercel (TensorFlow.js)
├── data/
│   └── sample_sine_wave.csv           Example file to upload on the web page
└── docs/
    └── Student_Task.pdf               Task description
```

- **Notebook:** trains an RNN, an LSTM and a GRU on a sine-wave dataset, draws the graph, computes RMSE and prints the final answers. Open it in Google Colab and choose **Runtime > Run all**.
- **Web page:** the user pastes or uploads a time series, the page detects the numbers and trains the same three models in the browser. No server or build step is needed.

## Deploy to Vercel

1. Push this repo to GitHub.
2. In Vercel choose **Add New > Project** and import the repo.
3. Leave Framework Preset as **Other** and the build command empty, then deploy.

## Using the page

- Paste numbers (one per line or comma-separated), paste a CSV, or upload a CSV file. Oldest value first. At least 30 values are needed.
- Or select **Load sample dataset**, or upload `data/sample_sine_wave.csv`.
- Select **Train and compare**. Training takes from a few seconds to about a minute, depending on the device.

Results can differ slightly between runs because training starts from random weights.

## Preview locally

```bash
cd site
python -m http.server 8000
```

Open http://localhost:8000.
