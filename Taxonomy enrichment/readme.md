**Taxonomy Enrichment**

1. Competition

https://codalab.lisn.upsaclay.fr/competitions/539

2. Description of the task

Taxonomies are tree structures which organize terms into a semantic hierarchy.
Taxonomic relations (or hypernyms) are “is-a” relations: cat is-a animal, banana is-a
fruit, Microsoft is-a company, etc. This type of relations is useful in a wide range of
natural language processing tasks for performing semantic analysis. The goal of this
semantic task is to extend an existing taxonomy with relations of previously unseen
words.
Multiple evaluation campaigns for hypernym extraction (SemEval-2018 task 9),
taxonomy induction (Semeval-2016 task 13, SemEval 2015 task 17), and most notably
for taxonomy enrichment (SemEval-2016 task 14) were organized for English and other
western European languages in the past. However, this is the first evaluation campaign
of this kind for Russian and any Slavic language. Moreover, the task has a more
realistic setting as compared to the SemEval-2016 task 14 taxonomy enrichment task
1
http://www.dialog-21.ru/evaluation/
http://www.dialog-21.ru/evaluation/2020/disambiguation/taxonomia/
3
https://codalab.lisn.upsaclay.fr/competitions/539
4
https://github.com/dialogue-evaluation/taxonomy-enrichment
2as the participants are not given the definitions of words but only new unseen words in
context.
More concretely, the goal of this task is the following: Given words that are not yet
included in the taxonomy, we need to associate each word with the appropriate
hypernyms from an existing taxonomy. For example, given the input word “утка” (duck)
we expect you to provide a list of its most probable 10 candidate hypernym synsets the
word could be attached to, e.g. “animal”, “bird”, and so on. Here a word may refer to
one, two or more “ancestors” (hypernym synsets) at the same time.

3 Evaluation metrics

Evaluated using the Mean Average Precision (MAP)
and Mean Reciprocal Rank (MRR) scores. MAP score pays attention to the whole range
of possible hypernyms, whereas MRR looks at how close to the top of the list a first
correct prediction is. In addition to that, the F1 score will be computed to evaluate the
performance of the top 1 prediction of the methods. MAP will be the official metric to
rank the submissions.
