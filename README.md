## `Approach`

Our approach is to use `text re-odering`, using a pre-trained language model (PLM), in our case `BERT`. Basically text re-odering require us to build a model that can predict the ordering of a sequence of disorder texts.

## `Requirements:`
1. The `transformers` library from HuggingFace to import BertTokenizer, BertForNextSentencePrediction is used. 
The tokenizer is used to tokenize the senteces used in the Next-Sentence-Prediction Model. The `bert-base-multilingual-cased` as pretrained weights are used to support cased text and several languages.
2. The `tensorflow` library is used to build the tensors for the model.
Finally, `tensorflow.keras` is used later to compute the softmax from the logits in the Next-Sentence-Prediction task.

## `User Case`
