# cs6910_assignment3
# DL
'''3k & sonagara'''
## report link : https://wandb.ai/sonagara/DL_A3_Q5_final_final/reports/Assignment-3--Vmlldzo3MDkyMjA
the problem descriptions are in the report link

## the DL_A3_Q2 contains codes for q2 and q4, and DL_A3_Q5 contains code for q5 and q6


## set variables
num_encoder_tokens = 30 (uniuqe input tokens + 2 for '\t' and '\n') , 
num_decoder_tokens = 70 (unique target tokens + 1 for '\n) , 
we have used gujarati data set

## tokenize(data,vocab_size)
data - arrar of words , 
vocab_size = uniue tokens for data , 
returns temp - tokenized data  , dictionary - for char to int, tokenizer - tokenizer for data

## load_and_preprocess()
returns encoder_input_data - conversion of char ot int with required padding , decoder_input_data - conversion of char ot int with required padding, decoder_target_data - this is one hot encoding 

## load_val_data(data_path = path for val data)
returns encoder_input_data , decoder_input_data, decoder_target_data (same as load_and_process)

## create_model(m_name="LSTM",n_e_layers=1,n_d_layers=1,latent_dim = 100,embedding_size = 16,dropout = 0 , recurrent_dropout = 0) (given are default values)
n_e_layers = no of encoder layers ,
n_d_layers = no of decoder layers , 
returns model

## train() - to run sweep
swwep_config = for sweep configuration

## train_best() 
all values for model can be set inside this function , 
- it will save the model in file names "s2s" -for q2 and as "s2sa" for q5

## load_test_data()
returns encoder_input_data - conversion of char ot int with required padding , input_texts - array of input words ,target_texts -array of target words

## save_csv()
for saving inference made on test data

# functions specificaly for DL_A3_Q2 file
## enc_dec(m_name="LSTM" ,latent_dim = 100, n_e_layers = 1,n_d_layers = 1) (given are default values) 
returns encoder_model, decoder_model

## decode_sequence(input_seq,encoder_model,decoder_model)
returns decoded sentence for input_seq

## test_acc(m_name="LSTM" ,latent_dim = 100, n_e_layers = 1,n_d_layers = 1) (given are defualt values)
- for running inference on test data
returns test_word_accuracy

## grid()
for plotting some of the input and generted test output.


# functions specificaly for DL_A3_Q5 file
## enc_dec_attention(m_name="LSTM",n_e_layers=1,n_d_layers=1,latent_dim = 100) (given are defualt values)
returns encoder_model , decoder_model ,atten_layer ,dense_layer 

## decode_sequence_attention(input_seq,encoder_model,decoder_model,decoder_dense,atten_layer)
returns decoded sentence - for input_seq , atten_states - array of attention states for deocded_sentence

## test_acc_attention(m_name="LSTM" ,latent_dim = 100, n_e_layers = 1,n_d_layers = 1) (given are defualt values)
returns test_word_accuracy

## attention_heat_map(m_name="LSTM", latent_dim =100 ,n_e_layers = 1 ,n_d_layers = 1) (given are defualt values)
- plots attentionmaps for first 9  test inputs

## cstr(s, color='black')
s = string / charcter
color = color name
- it retruns the html tag 

## print_color(t)
t = [(charcter ,color code),...] 
- it prints the t 

## get_clr(value)
value = any +ve floating point
returns color code for vlaue

## visualize(m_name="LSTM", latent_dim =100 ,n_e_layers = 1 ,n_d_layers = 1)  (given are defualt values)
- prints the weighted  color coded input for ith output character

