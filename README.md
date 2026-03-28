<div align="center">

![Financial Sentiment Analysis](screenshots/Recording%202026-02-02%20112851.gif)

![Status](https://img.shields.io/badge/status-completed-10b981?style=for-the-badge) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white) ![Electron](https://img.shields.io/badge/Electron-191970?style=for-the-badge&logo=Electron&logoColor=white) ![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)

*financial sentiment analysis — from raw text to a model to a UI you can actually use*

</div>

A desktop application that runs financial text through two classical ML models and gives you a clear picture of the sentiment behind it. Python handles the ML. C++ handles preprocessing for speed. Electron wraps everything into something simple and usable.

The interesting part isn't any single piece. It's that all of them have to work together.

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png">

## Why I built this

Finance touches everyone. It doesn't matter if you follow markets or not — the data behind financial decisions shapes things that affect all of us, and most people never get to look at it clearly.

I wanted to build something that worked on real data and produced something real. Sentiment analysis felt like the right fit — it's the kind of problem where the output actually means something, where you can look at a result and have a genuine reaction to it rather than just a number passing a test.

The ML side was the starting point, but what ended up being just as interesting was everything around it. Getting Flask and Electron to talk to each other properly. Writing preprocessing in C++ and linking it into a Python pipeline. I didn't expect to enjoy C++ as much as I did, and I didn't expect that connecting pieces across different languages would feel as satisfying as it does. There's something about the boundary between them — where one system hands off to another — that I find genuinely interesting to think about.

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png">

## What it does

![dashboard](screenshots/Screenshot%202026-02-02%20112926.png)

Two models — Naive Bayes and Logistic Regression — are trained on a financial sentiment dataset and served through a Flask API. The Electron frontend pulls from that API and presents the results in a UI that's simple and clean without hiding any of the detail that matters.

Both models run on every input. Watching them agree tells you something. Watching them disagree tells you more — it gives you a real picture of which model is actually better and where each one breaks down.

![model deep dive](screenshots/Screenshot%202026-02-02%20112953.png)
![analytics](screenshots/Screenshot%202026-02-02%20112644.png)

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png">

## Features

- Side by side Naive Bayes and Logistic Regression predictions on every input
- Visualizations for model confidence, sentiment distribution over time, and feature influence
- C++ text preprocessing compiled as a shared library and linked into the Python pipeline
- Flask API backend consumed by an Electron desktop frontend
- Accuracy metrics and full classification reports for both models

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png">

## Setup

You need Python 3.10+, Node.js 18+, and a g++ compiler. Run everything from the project root.

**Python dependencies**
```bash
pip install -r requirements.txt
```

**Dataset**

Download from [Kaggle — Financial Sentiment Analysis](https://www.kaggle.com/datasets/sbhatti/financial-sentiment-analysis?resource=download), extract the CSV, and place it at `data/data.csv`.

**C++ extension**
```bash
cd src/cpp
g++ -shared -o text_preprocess.dll text_preprocess.cpp
cd ../..
```

Linux/macOS: compile a `.so` instead of `.dll`.

**Node dependencies**
```bash
npm install
```

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png">

## Running

Start the backend first:
```bash
python src/python/main.py
```

Wait for the server to confirm it's running, then open a new terminal:
```bash
npm start
```

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png">

## Stack

- Python — model training, scikit-learn, Flask API
- C++ — text preprocessing compiled as a shared library
- Electron + Node.js — desktop application shell
- HTML / CSS / JavaScript — UI

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/aqua.png">

## About

I'm Hamid, 15, and I built this because I wanted to make something that worked on data that actually matters.

The hardest part was getting all the layers talking to each other — Flask, Electron, a C++ shared library, a Python ML pipeline. The most surprising part was how much I enjoyed working across all of them. Linking things together across languages turned out to be one of the more interesting problems I've worked on.

There's a lot more I want to build.