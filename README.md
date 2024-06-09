SensicalNonSense



SNL Weekend Update is a popular American comedy-news show that presents a mix of international news and satire in a humorous manner. I made this project to explore some interesting NLP libraries and tools that can make use of episodes from the Weekend update show to answer pop culture or even mundane queries.

Step 1: Creating a Corpus:

Finding a playlist of episodes of the SNL Weekend update, we extract the video ID from the videos. The characters after 'v=' in a youtuve video link identifies the video ID. We extract this ID as a substring. We use YouTube Data API to get the video subtitles transcript as a json file. This json files has text along with duration and timestamps of each dialogue, we remove the timestamps and save the texts as a .txt file. This forms our Corpus.

We then clean the data or unnecesary characters and empty lines.

Step 2: Tokenization of Corpus:

We use NLTK library to form tokens using sentence grammar and punctuations.

Step 3: Using Hugging-Face tokens:

We use AutoModelForQuestionAnswering and AutoTokenizer from transformers to train the model which is distilbert-base-uncased-distilled-squad on our context. Our context here is the Corpus.

Step 4: Testing:

We notice that in initial runs when we give smaller videos to train the model, it giver wierd replies, but as we increase the dataset, we start to get sensible, yet satirical answers, thus the name SensicalNonSense.

Question: How is the weather? Answer: ICE BREAKER

Corpus Analysis/Overview

Total Tokens: 101619

Unique Words (Types): 8783

Number of Hapax Legomena: 4225
