#Reliable approach for image question answering.

1. We have used python and Keras implmentation for Visual and Question Answering with first model being VIS +LSTM. The Following model is explained in our paper 

2. We have implmented second model similar to 2-VIS+BLSTM with an exception that LSTM is not bidirectional. We term the new model as 2-VIS+LSTM and it is supplied with two input features i.e. at the start and at the end of sentences.

3. We have used COCO-QA dataset and it has been explained in detailed in the paper. To download the dataset, follow the link -->  http://www.visualqa.org/

4. The precomputed MS COCO features can be downloaded from the following link --> http://cs.stanford.edu/people/karpathy/deepimagesent/cooco.zip and then extract them in coco_features folder.

5. Download and extract the pretrained common crawl 300D word vectors from http://nlp.stanford.edu/data/glove.840B.300d.zip and extract in the embeddings folder.

6. Use the script 'embedding.py' to generate the embedding matrix and word matrix.    $ python embedding.py -adress path of glove file.

7. Download the pretrained VGG 16 weights from https://drive.google.com/file/d/0Bz7KyqmuGsilT0J5dmRCM0ROVHc/view and place them in the weights folder. This is required for making predictions on your own images.

8.Requirements
	* Python 2.7
	* Numpy
	* Scipy (for loading pre-computed MS COCO features)
	* NLTK (for tokenizer)
	* Keras
	* Theano
	
9.Training the models

	Use python_train.py
	To train the secific model we can do it in following way for example 
	to train the VIS+LSTM model enter `python train.py -model=1`.
	to train the 2-VIS+LSTM model enter `python train.py -model=2`.

10. To specify batch size use `-batch_size`
   To specify options size use `-num_epochs`
   Although the default batch size and number of epoch are 200 and 25 respectively

11.Prediction
	To perform visual question answering on any image use the script `question_answer.py`.
	use the options `-question` to specify the question.
	use the option  `-image` to specify the image.
	to select the particular model please use `-model`. By default, model 2 is selected.

12.* An example of usage is: `python question_answer.py -image="examples/COCO_val2014_000000000136.jpg" -question="Which animal is this?" -model=2`


