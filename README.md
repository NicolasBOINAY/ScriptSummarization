# Movie Script Summarization

This repository contains the code for the project **Using movie plots for unsupervised Movies/TV Series summarization**.
The code is based on th existing project [MultiViewSeq2Seq](https://github.com/GT-SALT/Multi-View-Seq2Seq) which was based on the paper : *Jiaao Chen, Diyi Yang*: Multi-View Sequence-to-Sequence Models with Conversational Structure for Abstractive Dialogue Summarization, EMNLP 2020

## Generating summaries

### Encode conversations

- First you need to get into the [Preprocessing directory](./Preprocessing) where you will find all the notebooks in order to encode the scripts
- Then you first start with the [sentence embeddings](Preprocessing/Sentence_Embeddings.ipynb) which is where you first process your script in order to get only the dialogues segmented into scenes before encoding the dialogues
- The next step is segmenting conversations first in [topic view](Preprocessing/Topic_Segment.ipynb), in this notebook we use the *C99 algorithm* in order to segment conversations based on topics, and then in [stage view](Preprocessing/Stage_Segmentation.ipynb), there we use an *Hidden Markov Model* to get the stage segmntion of the dialogue. 
- Last step is generating segmented data `*.source` for the fairseq framework 

### Decode conversation 
Finally to generate summaries, we use the `Eval_Sum.ipynb` to generate summaries and compare them to the handwritten ones. 

## Data 

The data used in this repository comes from the [Scriptbase Corpus](https://github.com/EdinburghNLP/scriptbase) and we also used the `screenplays_scene_segmentation.py` from [TRIPOD](https://github.com/ppapalampidi/TRIPOD).
In the directory `data` you can find examples of what we did for different movies. 


