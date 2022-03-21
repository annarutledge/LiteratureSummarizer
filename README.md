# LiteratureSummarizer

## Problem Statement
Can a neural network model for natural language processing be used to create summaries from literary texts?

## Introduction
In this project, powerful pretrained NLP models from the Hugging Face transformers library are finetuned and used to make predictions with the goal of generating summaries based on excerpts or chapters of classic literature. The models are trained on datasets of reference texts (chapters or group of chapters from a selection of books) and human-written summaries of those chapters or sections, and are evaluated based on the predictions, or model-generated summaries, they produce.

## Background
The Hugging Face transformers library is a widely used tool in the world of natural language processing models. The costs of training a highly effective natural language processing model can be very high in time, money, and energy. The Hugging Face library provides a platform for the individuals, companies, and other organizations to utilized powerful models that hve been pre-trained with huge amounts of data and come with a large amount of knowledge and predictive ability. Some of these pre-trained models are deisgned to be especially suited to types of tasks such as translation, text generation, question answering or summarization. Through the Hugging Face interface, these models can then be downloaded, and fine-tuned and further trained to perform even better on specific goals.

## Data
### Data Collection
The data used in this project, including the text and titles of full books and chapter excerpts, was collected through web scraping of websites including novelguide.com and fullbooks.com. The full book texts and summary texts were cross-referenced, the full boiok texts were divided into chapters, and then the full chapter texts were matched up with chapter/section summaries to create a final dataset of texts and summaries of those texts.
### Data Dictionary
#### Summaries & Texts Data
(cleaned_summaries_and_texts.csv)
|Feature|Datatype|Description|
|---|---|---|
|chapter_title|string|descriptive title of book chapter(s) (incl book title)|
|chapter_summary|string|summary of book chapter(s) collected from Novelguide's online summary collection|
|book_title|string|title of the book the chapter(s) is found in|
|chapters|string|shortened designation for chapter(s) (not incl book title)|
chapter_text|string|full text of chapter(s)|
##### For use in the building of models, the cleaned summaries & texts data was split into training, testing, and validation datasets, which were then exported to separate csv files. In models, only the 'chapter_text' and 'chapter_title' features of the data were used.

## Model Fine-Tuning
Three different base pre-trained transformer models were used with the collected datatsets in a fine-tuning process based on the tutorials available on the Hugging Face platform. This process includes initialization of a tokenizer and model with a transformer checkpoint, tokenizing and encoding of the data (the chapter texts & chapter summaries) for input to the model, adjusting of model hyperparameters, and fitting of the model on the testing data, with the validation dataset as a validation set during training. 

## Model Metrics
Natural language processing models cannot all necessarily be evaluated with the same metrics as other neural networks or types of models. For models designed for tasks such as summarization, metrics that can evaluate the quality of predictions containing large amounts of plain or encoded text are need. The primary metric used for summarization models, and the metric used in this project, are Rouge scores. This metric provides a way to calculate recall, precision, and f1-scores for text. There a few different types of Rouge score. Rouge-n considers the amount of matching n-grams in the reference and model texts (for example Rouge2 considers bigrams), RougeL considers text by sentence and looks for the longest matching sequences found in the texts (not necessarily consecutively), and RougeLsum considers longest mathcing sequences over a longer piece of text. For each score, recall is calculated by dividing number of matches found by the total number of words in the reference text, and precision is calculated by dividing number of matches found by the total number of words in the model-produced text. F1-score is computed from precison in recall as it is for typical classification models. The models in this project are evaluated on Rouge1, Rouge2, RougeL, and RougeLsum f1-scores.

## Best Model
 Based on the recorded Rouge scores, the best performing summarization model is model 13, using the sshleifer/distilbart-xsum-1-1 model checkpoint with increased maximum lengths for model inputs, 25 epochs of training with an earlystopping callback, and weight decay rate of 0.1. This model recieved the highest rouge f1-scores for Rouge1, RougeL, and RougeLsum, and a comparable Rouge2 f1-score to the second best performing model (model 08). The predicted summaries generated by the processing of test data with this model still do not meet the final goal of the fine-tuned modeling -to a produce accurate and human readable summaries of reference texts- but does produce text including some full sentences and often obviously related to the context/characters/events described in the associated texts and/or reference summaries. There is further work and development to be done on this model, however it represents progress in the right direction towards achieving desired outcomes.

## Limitations
Primary limitation in this project and in the performance of the final best model is the relatively small size of the dataset used for training. Due to challenges with data collection, the number of book chapters or excerpts and associated summaries was just under 300, which is quite a small sampling of the texts typically included in the classical literature genere. Looking at summaries produced by the test data in the various fine-tuned models, it is obvious that some books are overrepresented simply because thay have mroe chapters to be included in the dataset, and specific words or phrases found often in these texts show up in many generated sumamries, even those for chapters not from these books. This could be addressed by data that is balanced out by including excerpts from a larger set of books.

## Conclusions & Future Directions
Overall this project has not quite achieved its ultimate goal, but the best model built has made significant improvements in performance compared to the baseline model, and the outputs of this model represent progress towards effective readabel summaries. As mentioned above, the primary limitation in, and therefore the primary future step for improvement of this project is the collection of more data to use in model training. This, along with further tuning of hyperparameters to encourage relevancy and readability of produced summaries, should lead to better model performance.
<br>
<br>
The best model built so far in this project has been added to the Hugging Face hub!
Check it out at https://huggingface.co/AnnaR/literature_summarizer