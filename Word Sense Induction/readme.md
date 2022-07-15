Word Sense Induction

Competition: https://competitions.codalab.org/competitions/36019

Description of the task

WSI for Slavic languages is available at the
moment.
TLDR of the task: You are given a word, e.g. bank and a bunch of text fragments (aka
“contexts”) where this word occurs, e.g. bank is a financial institution that accepts
deposits and river bank is a slope beside a body of water. We need to cluster these
contexts in the (unknown in advance) number of clusters which correspond to various
senses of the word. In this example, we want to have two groups with the contexts of
the company and the area senses of the word bank. The contexts
(sentences) which share the same meaning should have the same predict_sense_id.
The context will use different meanings of the target word, e.g. bank (area) vs bank
(company) should have different sense identifiers.

Please Read problem description.pdf for full info about the task


