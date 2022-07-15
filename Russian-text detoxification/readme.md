**Text Detoxification in Russian**
1. Competition link

Ru Detoxification competition: https://codalab.lisn.upsaclay.fr/competitions/532

2. Text Detoxification

2.2.1 Introduction
GThe Internet has facilitated the spread of toxicity and hate speech. Much work has been done in the
direction of offensive speech detection. However, it has become essential not only to
detect toxic content but also to combat it in smarter ways. While some social networks
block sensitive content, another solution can be to detect toxicity in a text which is being
typed in and offer a user a non-offensive version of this text. This task can be
considered a style transfer task, where the source style is toxic, and the target style is
neutral/non-toxic. The task of style transfer is the task of transforming a text so that its
content and the majority of properties stay the same, and one particular attribute (style)
changes. This attribute can be the sentiment, the presence of bias, the degree of
formality, etc. Considering the task of detoxification, it has already been tackled by
different groups of researchers, as well as a similar task of transforming text to a more
polite form. However, all these works deal only with the English language. As for
Russian, the methods of text style transfer and text detoxification have not been
explored before.

2.2.2 Task formulation
You have a great chance to be the first participant in the competition of automatic
detoxification of Russian texts to combat offensive language. Such a kind of textual
style transfer can be used, for instance, for processing toxic content in social media.
5
https://www.aclweb.org/anthology/P19-1325/While much work has been done for the English language in this field, it has never been
solved for the Russian language yet.
We define the detoxification task as the task of style transfer: from the toxic style to the
non-toxic style. We want to rewrite the sentence and preserve the context.
We define the task of style transfer as follows. Let us consider two corpora 𝐷
𝑥 2 , …, 𝑥 𝑛 } and 𝐷
𝑌
= { 𝑦 1 , 𝑦 2 , …, 𝑦
𝑚
} in two different styles – 𝑠
(non-toxic), respectively. The task is to create a model 𝑓
all possible texts with styles 𝑠
Х
and 𝑠
𝑌
𝜃
sentence 𝑥 with the style 𝑠
the style 𝑠
𝑌
𝑌
𝑌
) of transferring a
to the sentence 𝑦 ′ which saves the content of 𝑥 and has
be parallel or non-parallel. We focus on the transfer 𝑠
style, and 𝑠
(toxic) and 𝑠
. The task of selecting the optimal set of
. The parameters are maximised on the corpora 𝐷
𝑌
= { 𝑥 1 ,
: 𝑋 → 𝑌 , where 𝑋 and 𝑌 are
parameters 𝜃 for 𝑓 consists maximising the probability 𝑝(𝑦’ | 𝑥, 𝑠
Х
Х
Х
Х
→ 𝑠
𝑌
Х
and 𝐷
, where 𝑠
𝑌
Х
which can
is the toxic
is neutral.

2.2.3 Evaluation metrics
To perform a comprehensive evaluation of a style transfer model, we need to make sure
that it (i) changes the text style, (ii) preserves the content, and (iii) yields a grammatical
sentence. The majority of works on style transfer use individual metrics to evaluate the
three parameters. In our competition we use the following metrics:
1) Style transfer accuracy: a classifier that evaluates the toxicity class of a rewritten
sentence
2) ChF: character n-gram F score between the rewritten sentence and the manually
detoxified reference

2.2.4 Methods
In the context of this assignment, you will solve a style transfer task on the dataset of
comparative sentences provided by the course team. You will need to train a model and
submit your solution to the CodaLab competition:
https://codalab.lisn.upsaclay.fr/competitions/532 .
You are free to use any methods and/or models for style transfer or pretrained models
for text generation (GPT, T5, etc.). Here are some baselines you may want to improve:Duplicate this is a naive baseline that amounts to performing no changes to the input sentence.
It represents a lower bound of the performance of style transfer models, i.e. it helps us check
that the models do not contaminate the original sentence.
Delete: this method eliminates toxic words based on a predefined toxic words vocabulary. The
idea is often used on television and other media: rude words are bleeped out or hidden with
special characters (usually an asterisk). The main limitation of this method is vocabulary
incompleteness: we cannot collect all the rude and toxic words. Moreover, new offensive words
and phrases can appear in the language that can be also concatenated with different prefixes
and suffixes. On the other hand, this method can preserve the content quite well, except for the
cases when toxic words contain meaning that is essential for the understanding of the whole
text.
Retrieve: This method is targeted at improving the accuracy of style transfer. For a given toxic
sentence, we retrieve the most similar non-toxic text from a corpus of non-toxic samples. In this
case, we get a safe sentence. However, the preservation of the content depends on the corpus
size and is likely to be very low.

2.2.5 Expected output
Example of the input and model output are presented below:
As output we expect a paraphrased (rewritten) toxic sentence in a more neutral
(non-toxic) style. For each input sentence x i we expect a corresponding rewritten
sentence y i .

Code in the notebook outperforms competition baseline
