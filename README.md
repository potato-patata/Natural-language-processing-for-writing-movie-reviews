# Natural language processing for writing movie reviews
Aim of this project was to efficiently generate texts using LSTM and RNN models for writing own reviews using IMDB dataset (Dataset consists 50000 rows).
1. Extracting positive, negative and mixed reviews from the dataset
2. Pre - processing: Map chars to integers.
Because we will be training on a character level, we need to relate each unique character with a number. I created two dictionary one from character to integer and one to transform back to character. Then, we need to split up the text into subsequences that is create an array with next character, next character will act as a target class. After splitting the data, reshaping was done as neural networks cannot understand string, therefore they were converted to Boolean vectors to easily predict the next character.
3. Building model:
Multi – layer LSTM network was built. Whole dataset was not used for text generation, as it requires extensive computing power to perform this task therefore for positive and negative reviews 10% of the total data was used individually.
4. Generating text:
A helper function was used. This function samples an index from an array of probabilities with some temperature. Temperature is a scaling factor applied to the outputs of our dense layer before applying the SoftMax activation function. In a nutshell, it defines how conservative or "creative" the model's guesses are for the next character in a sequence.
5. Evaluating results by calculating perplexity:
Perplexity is the inverse probability of the test set, normalized by the number of words. Model with lowest perplexity is said to be more efficient in predicting correct sequence of words.
Our best model for text generation at temperature 0.2 was one with negative reviews with perplexity 3.587.
## Dataset
IMDB dataset having 50K movie reviews was used for natural language processing or Text analytics.
This is a dataset for binary sentiment classification containing substantially more data than previous benchmark datasets. They provide a set of 25,000 highly polar movie reviews for training and 25,000 for testing.

https://www.kaggle.com/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews
