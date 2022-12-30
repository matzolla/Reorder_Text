## `Approach`

Our approach is to use `text re-odering`, using a pre-trained language model (PLM), in our case `BERT`. Basically text re-odering require us to build a model that can predict the ordering of a sequence of disorder texts.

## `Requirements:`
1. The `transformers` library from HuggingFace to import BertTokenizer, BertForNextSentencePrediction is used. 
The tokenizer is used to tokenize the senteces used in the Next-Sentence-Prediction Model. The `bert-base-multilingual-cased` as pretrained weights are used to support cased text and several languages.
2. The `tensorflow` library is used to build the tensors for the model.
Finally, `tensorflow.keras` is used later to compute the softmax from the logits in the Next-Sentence-Prediction task.
3. A `GPU` for longer sentences.

## `User Case`
Let's take the toy example of the paper Is [Everything in Order? A Simple Way to Order Sentences](https://aclanthology.org/2021.emnlp-main.841.pdf).
Using this example of `5 sentences` shuffled the objective was to recover the exact sequence (order) of the sentences.

`correct_order=['The forecast called for rainy','I packed my raincoat','It never rained','Instead it started to snow',
      'The weather is never predictable']`. You may decide to change the content of this text and compute the ordering again.
      
## `Performance and discussion`

Suprisingly running a `BERT` model to predict next-sentence probability give a quite descent accuracy of `40%` averagely. This might change as the shuffling changes. The Paper [Everything in Order? A Simple Way to Order Sentences](https://aclanthology.org/2021.emnlp-main.841.pdf) also investigated the effect of placing a text at a far index from it's original index in the text corpus. This might affect the accuracy as well
