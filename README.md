In this report we present our finetuned noisy speech to coher-ent text model which was created by 
finetuning the pretrained Multilingual Lexical Normalization model based on the ByT5architecture. 
Our work uses the danish version of the multi-lexnorm model whice we finetune on our audiobook data 
to correct noisy speech transcripts generated from audiobooksby an automatic speech recognition model.

The code for the finetuning and testing can be found in Finetuning-Danish-LLM.ipynb 
The data file noisy_danish_data.txt is used for finetuning and testing/
You can download the jupyter notebook and retraini the model on your own data.

More details about the project, LLM, error metrics etc can be found in the Coherent-text-generation-report.pdf
