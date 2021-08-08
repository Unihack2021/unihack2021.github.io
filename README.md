## Inspiration
The 2021 Tokyo Olympic Games is one of the biggest topics in recent days and has attracted a lot of attention. While there are many sports enthusiasts, the vast majority of people lack the background understanding of certain sports, which prevents them from getting involved in matches and knowing the technical details/difficulties of sports and the stories behind countries and athletes.

## What it does
OLYMPEDIA aims to be an information medium and platform for all those who follow the Olympic Games. OLYMPEDIA provides all Olympic followers with the latest event information, game schedule, country/sports background information, as well as our own unique AI Olympics judge and medal analysis & predictions.

OLYMPEDIA has three core modules：
* Olympic Information Hub: Provides latest information about the 2021 Tokyo Olympic Games, includes：
    * Countdown to the next match 
    * Event calendar of all the incoming and past events
    * Info about the background & story of each country
    * Match Highlights
* AI Olympics Judge - ML model for AQA (Action Quality Assessment) using C3D-AVG-MTL network architecture: use artificial intelligence (multi-task learning) to assess how well divers perform; better ensure the rigor of competition and avoid controversy
* Medal Predictions - ML model for medal prediction (ARIMA model and linear regression): by studying all past Olympic records from 1896-2016, OLYMPEDIA provides an accurate estimate of the number of medals each country would win and performs analysis on the relationship between medals and national GDP

## How we built it
### Frondend
* Tech Stacks: HTML5, CSS3/SASS, Javascript, jQuery, Bootstrap, Streamlit
* The frontend was built mainly in HTML5 and CSS3. The overall theme color is consistent with the 2021 Tokyo Olympic Games’ theme color - Emblem Blue. Data and events' information are extracted from the [Olympics](https://olympics.com/en/) official website.

### ML - AI AQA Judge
* Tech Stacks: Python, Scipy, Numpy, Pytorch/Torchvision, PIL, pickle, Shell Script
* Algorithms: C3D-AVG-MTL Network
* Inspired by the paper [“What and How Well You Performed? A Multitask Learning Approach to Action Quality Assessment”](https://openaccess.thecvf.com/content_CVPR_2019/papers/Parmar_What_and_How_Well_You_Performed_A_Multitask_Learning_Approach_CVPR_2019_paper.pdf), we trained a C3D-AVG-MTL network using Pytorch.
* The datasets we used are 20+ videos from past diving competitions (total of 50+ hours). We used excel for annotations and used ffmpeg in shell script to convert them to 6,000,000+ jpeg files as training samples. The C3D-AVG-MTL network architecture is attached.

### ML - Medal Prediction
* Tech Stacks: Python, OS, Scipy, Numpy, Pandas, Matplotlib, Sklearn
* Algorithms: Linear Regression, Logistic Regression, ARIMA (AutoRegressive Integrated Moving Average)
* The metal prediction model is a series of statistical models built using historical individual athletes data. The data includes each athlete's nationality, basic traits such as age, height, and weight, and the athlete's sport and metal. The data are sourced from Kaggle's [120 years of Olympic history: athletes and results](https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results), but it was originally crawled from www.sports-reference.com. The data are first pre-processed to remove invalid entries and null entries. We built three different prediction models. The metal prediction is built using Linear regression and ARIMA mode, predicting how many gold, silver, and bronze medalists each country will produce.

## Challenges we ran into
* Installing a lot of dependencies and running pytorch under CUDA environment.
* Debugging GPU memory allocation error with basically no info given from pytorch.## Inspiration
The 2021 Tokyo Olympic Games is one of the biggest topics in recent days and has attracted a lot of attention. While there are many sports enthusiasts, the vast majority of people lack the background understanding of certain sports, which prevents them from getting involved in matches and knowing the technical details/difficulties of sports and the stories behind countries and athletes.

## What it does
OLYMPEDIA aims to be an information medium and platform for all those who follow the Olympic Games. OLYMPEDIA provides all Olympic followers with the latest event information, game schedule, country/sports background information, as well as our own unique AI Olympics judge and medal analysis & predictions.

OLYMPEDIA has three core modules：
* Olympic Information Hub: Provides latest information about the 2021 Tokyo Olympic Games, includes：
    * Countdown to the next match 
    * Event calendar of all the incoming and past events
    * Info about the background & story of each country
    * Match Highlights
* AI Olympics Judge - ML model for AQA (Action Quality Assessment) using C3D-AVG-MTL network architecture: use artificial intelligence (multi-task learning) to assess how well divers perform; better ensure the rigor of competition and avoid controversy
* Medal Predictions - ML model for medal prediction (ARIMA model and linear regression): by studying all past Olympic records from 1896-2016, OLYMPEDIA provides an accurate estimate of the number of medals each country would win and performs analysis on the relationship between medals and national GDP

## How we built it
### Frondend
* Tech Stacks: HTML5, CSS3/SASS, Javascript, jQuery, Bootstrap, Streamlit
* The frontend was built mainly in HTML5 and CSS3. The overall theme color is consistent with the 2021 Tokyo Olympic Games’ theme color - Emblem Blue. Data and events' information are extracted from the [Olympics](https://olympics.com/en/) official website.

### ML - AI AQA Judge
* Tech Stacks: Python, Scipy, Numpy, Pytorch/Torchvision, PIL, pickle, Shell Script
* Algorithms: C3D-AVG-MTL Network
* Inspired by the paper [“What and How Well You Performed? A Multitask Learning Approach to Action Quality Assessment”](https://openaccess.thecvf.com/content_CVPR_2019/papers/Parmar_What_and_How_Well_You_Performed_A_Multitask_Learning_Approach_CVPR_2019_paper.pdf), we trained a C3D-AVG-MTL network using Pytorch.
* The datasets we used are 20+ videos from past diving competitions (total of 50+ hours). We used excel for annotations and used ffmpeg in shell script to convert them to 6,000,000+ jpeg files as training samples. The C3D-AVG-MTL network architecture is attached.

### ML - Medal Prediction
* Tech Stacks: Python, OS, Scipy, Numpy, Pandas, Matplotlib, Sklearn
* Algorithms: Linear Regression, Logistic Regression, ARIMA (AutoRegressive Integrated Moving Average)
* The metal prediction model is a series of statistical models built using historical individual athletes data. The data includes each athlete's nationality, basic traits such as age, height, and weight, and the athlete's sport and metal. The data are sourced from Kaggle's [120 years of Olympic history: athletes and results](https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results), but it was originally crawled from www.sports-reference.com. The data are first pre-processed to remove invalid entries and null entries. We built three different prediction models. The metal prediction is built using Linear regression and ARIMA mode, predicting how many gold, silver, and bronze medalists each country will produce.

## Challenges we ran into
* Installing a lot of dependencies and running pytorch under CUDA environment.
* Debugging GPU memory allocation error with basically no info given from pytorch.
* Re-adjusting network parameters in order to fix shape mismatch
* Frontend visualization of the diagrams trained in python
* Limited memory in Heroku - some dependencies don't fit

## Accomplishments that we're proud of
* Great teamwork & task distributions! Successfully combined everyone’s work and deployed
* Successfully locate PyTorch CUDA memory leak during the training process
* Successfully processed all the data and have some nice visualization
* Successfully deployed streamlit on Heroku

## What we learned
* Managing PyTorch training and evaluating pipeline
* Utilizing various tools to locate sources of memory leak

## What's next for Untitled
* Extend our AI Judge to other Olympic sports such as Gymnastics, Snowboarding, Skiing, etc.
* Compare our medal predictions to the actual results once the 2021 Tokyo Olympics is done.

* Re-adjusting network parameters in order to fix shape mismatch
* Frontend visualization of the diagrams trained in python
* Limited memory in Heroku - some dependencies don't fit

## Accomplishments that we're proud of
* Great teamwork & task distributions! Successfully combined everyone’s work and deployed
* Successfully locate PyTorch CUDA memory leak during the training process
* Successfully processed all the data and have some nice visualization
* Successfully deployed streamlit on Heroku

## What we learned
* Managing PyTorch training and evaluating pipeline
* Utilizing various tools to locate sources of memory leak

## What's next for Untitled
* Extend our AI Judge to other Olympic sports such as Gymnastics, Snowboarding, Skiing, etc.
* Compare our medal predictions to the actual results once the 2021 Tokyo Olympics is done.
