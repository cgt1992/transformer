# transformer
Two text files containing parallel sentences (seperated by '\n' characters) in two languages are required to train the model. See an example of this in the data/ folder (french.txt and english.txt).

To begin training, run this code:

python train.py -src_data path/lang1.txt -trg_data path/lang2.txt -src_lang lang1 -trg_lang lang2
The spacy tokenizer is used to tokenize the text, hence only languages supported by spacy are supported by this program. The languages supported by Spacy and their codes are:

English : 'en'
French : 'fr'
Portugese : 'pt'
Italian : 'it'
Dutch : 'nl'
Spanish : 'es'
German : 'de'

For example, to train tan English->French translator on the datasets provided in the data folder, you would run the following:

python train.py -src_data data/english.txt -trg_data data/french.txt -src_lang en -trg_lang fr
Additional parameters:
-epochs : how many epochs to train data for (default=2)
-batch_size : measured as number of tokens fed to model in each iteration (default=1500)
-n_layers : how many layers to have in Transformer model (default=6)
-heads : how many heads to split into for multi-headed attention (default=8)
-no_cuda : adding this will disable cuda, and run model on cpu
-SGDR : adding this will implement stochastic gradient descent with restarts, using cosine annealing
-d_model : dimension of embedding vector and layers (default=512)
-dropout' : decide how big dropout will be (default=0.1)
-printevery : how many iterations run before printing (default=100)
-lr : learning rate (default=0.0001)
-load_weights : if loading pretrained weights, put path to folder where previous weights and pickles were saved
-max_strlen : sentenced with more words will not be included in dataset (default=80)
-checkpoint : enter a number of minutes. Model's weights will then be saved every this many minutes to folder 'weights/'
