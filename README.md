![Alt text](https://raw.githubusercontent.com/Imranharun/2300968-11-Imr-Sentiment_Analytics-Platinum/master/logo%20binar/logo%20binar.png)

# Sentiment Analytics Service

This project contains Sentiment Analytics AI for any messages. Its main feature to classify whether a message has **Negative** or **Positive** sentiment in its sentence / message automatically.

The main purpose of the service is user can easily classify a sentiment of a message, which most commonly used in **Product Review** and **Social Media Feedbacks** analytics. Although, this service comes in **API form** and has AI models in it, the models were sampled / made in **Bahasa Indonesia**/**Indonesian language**, so it will only work properly with **Indonesian** language.

Since the tool process words and sentences, it's fully aware that some of the messages are not always ***clean text***(contains: emoji, RT, etc), thus the tool also capable to clean the sentences we input, before it continues to begin the **Sentiment Analytics** process.

The tool uses **SQLite3** to fetch & store data into database and **FastAPI** to generate **SwaggerUI** for its services.

## How to run the API?
 
First thing first, you need to download and open the terminal in your source-code, and follow these steps to install the needed aspects before we get to run the API.

There are a few things that required to be installed in your environment and the AI models before you get to run the API.

## Prerequisites  & Installing (CONDA)

1. Create conda virtual environment:


``
conda create --n openai_env python=3.9
``

2. Activate your environment:


``
conda activate openai_env
``

3. Install All Depedencies:


``
pip install -r requirements.txt
``


4. Run / Hit the API with:


``
make run
``


***If you have issues on the first one, try the Alternative Command***


``
uvicorn main:app --reload --log-level debug --port 8200
``


# The usage of its service & The expected output

There are 3 main API services that you can use, which will be explained briefly on how to use it and the expected output for each service / feature.

1. Default

        Ignore this one, this is just the default route from the API. Which its expected output is to check whether the API successfully running or not.
2. Cleansing API

        It will perform text-cleansing on your data.

3. Sentiment API

        It will perform Sentiment Analytics on your text data.

4. Database API

        It will show you the Database you've created along the process of this tool.

To fully understand the each functions have been mentioned above, please check the tutorial below.

![Altimage](https://cdn.discordapp.com/attachments/1080523743534784592/1161646620874653756/image.png?ex=65390eb8&is=652699b8&hm=67332397e88a5a5e046c4b185c929547dbe6297f642b95355250e14cd7edf984&)


## Cleansing API: Text Cleansing

This service will let you cleanse/remove the following aspects below from your words/sentence:

    1. Hashtags attached to a word
    2. Symbols
    3. Emojis
    4. Word: user (after being lowered case by the cleansing code) - user as Twitter text context
    5. 'ø', 'ù', 'º', 'ð', etc
    6. Repeated words
    7. /n or enter
    8. Spaces

Any words/sentences you input that has the following aspects mentioned above will be ***cleansed***.

### How to use Cleansing API (Text Cleansing)

These are the following steps to use it:

    1. Click on the service, and it will ask you to try it out.
    2. The sentence box will now be able to be inputted, you may input any words / sentence.
    3. Hit the Execute button
    4. The output will be shown in the Server Responses section. 

## Sentiment API

This service will perform **Sentiment Analytics** on the words/sentence you input. It will automatically classify whether your message is ***Negative*** or ***Positive***.

It has 7 models you can choose, each models has their own scoring system, but the expected output are the same. The differences between each models are **execution time** and **accuracy**.

There are two features with the same idea/purpose, although the usage of both services have different steps.

### How to use the Sentiment API: Sentiment Analytics

![Altimage](https://cdn.discordapp.com/attachments/1080523743534784592/1161650238172450926/image.png?ex=65391217&is=65269d17&hm=b110703ad0447494130bd3fb5bc7b0a9decd2334eba7c554a57ed4a451f63705&)

This feature will label your text **Negative** or **Positive** as the output.

These are the following steps to use it:

    1. Click on the service, and it will ask you to try it out.
    2. The sentence box will now be able to be inputted, you may input any words / sentence.
    3. There will be a drop down, it contains 7 AI models you can choose, please choose one or stay with the default.
    4. Hit the Execute button.
    5. The output will be shown in the Server Responses section.

### How to use the Sentiment API: Upload-File

The purpose of this feature is to let you do Sentiment Analytics in bulk

![Altimage](https://cdn.discordapp.com/attachments/1080523743534784592/1161653705788104714/image.png?ex=65391551&is=6526a051&hm=3bf29686b974dd1dd1a84603a1257bbc308c8abd49d9a2e57d1f8a51b21743c9&)

This feature will let you upload a .csv file and it will insert the data into the databse then it will perform the Sentiment Analytics to label each data.

These are the following steps to use it:

    1. Click on the service, and it will ask you to try it out.
    2. The file box will now be available and now you can choose your .csv file.
    3. Hit the Execute button
    4. All the data from your .csv will be labelled and shown in the Server Responses section.

There are a couple things you must know to get the service runs properly:

    1. Your .csv may only contain 1 column
    2. The column name must be "tweets"
    3. There are no restriction on how many rows you can have.

## Database API

In this service, you can check the databse you've inputted from the Sentiment API, there are 2 features inside this service. Each of these services use SQL Syntax to perform their service.

1. Get Data:


This will let you see all the database data that have been inserted before.

2. Get Data by Sentiment:


This will let you see all the database data that have been inserted before with **SORTING** feature based on the Sentiment each data.

### How to use Database API: Get Data

    1. Click on the service, and it will ask you to try it out.
    2. It will show no paramter, only Execute button.
    3. Hit the Execute button.
    4. The output will be shown in the Server Responses section.

### How to use Database API: Get Data by Sentiment

![Altimage](https://cdn.discordapp.com/attachments/1080523743534784592/1161655769054322819/image.png?ex=6539173d&is=6526a23d&hm=1488d9c43dab5724418ddcfe7d790ed0a05da80588911ac7cac23ed78f897b24&)

    1. Click on the service, and it will ask you to try it out.
    2. Choose the Sentiment from the dropdown.
    3. Hit the Execute button.
    4. The output will be shown in the Server Responses section.


# Model Descriptions

To get the Sentiment Analytics running, we need AI Model behind its action. Thus these models are the ones who perform Sentiment Analytics in the process of each function/features we have talked about in the Tutorial section above.

![Altimage](https://github.com/Imranharun/2300968-11-Imr-Sentiment_Analytics-Platinum/blob/master/visualization/sentiment.png?raw=true)

As you can see that we have 7 AI Models that can be chosen in the **Sentiment Analytics**, here are the lists.

There are 7 models in this API:

1. [huggingface (ayameRushia)](https://huggingface.co/ayameRushia/bert-base-indonesian-1.5G-sentiment-analysis-smsa)
2. NN (Neural Network)
3. RNN (Recurrent Neural Network)
4. LSTM (Long Short Term Memory Network)
5. LSTM Fine Tuned
6. NN Fine Tuned
7. RNN Fine Tuned

        Fine Tuned Version: This version applied with k-fold cross validation.

## Loss & Accuracy Each Models

Here are the visualization on each Accuracy & Loss from each AI models based on the training & testing with [IndoNLP/Indonlu Dataset](https://github.com/IndoNLP/indonlu/tree/master/dataset).

Model: NN (MLP), RNN & LSTM
![Alt image](https://github.com/Imranharun/2300968-11-Imr-Sentiment_Analytics-Platinum/blob/master/visualization/visualization%20model%201.png?raw=true)

With Cross Validation & Without
![Alt image](https://github.com/Imranharun/2300968-11-Imr-Sentiment_Analytics-Platinum/blob/master/visualization/model%20with%20cv.png?raw=true)

### Overall Loss & Accuracy from both Models

![Alt image](https://github.com/Imranharun/2300968-11-Imr-Sentiment_Analytics-Platinum/blob/master/visualization/all%20accuracy.png?raw=true)
