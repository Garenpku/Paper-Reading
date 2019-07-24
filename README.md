This repository tries to give a comprehensive field search about dialog systems. For a general introduction see [this article](https://github.com/Garenpku/Paper-Reading/blob/master/intro%20to%20dialog%20system.md).

# Open-domain Dialog Agents

# Domain-specific Dialog Agents

## Natural Language Understanding
This part takes the automatic speech recognition (ASR) hypotheses as input and map them to semantic annotations. The semantic types to be predicted are oriented to the pre-defined ontology. In my understanding, semantic parsing and semantic role labeling can both be variants of the NLU task.

## Dialog State Tracker
This part takes annotated utterance from NLU module as input and generate several probability distributions:

1.**Goals**. For every slot the module should give a probability distribution over all possible values.

2.**Requested slots**. A reported probability for each requestable slot that has been requested by the user.

Sometimes people combine this module and NLU together to map ASR hypotheses directly to state distributions. This can avoid the error caused by imperfectness of NLU module.

[Rule-Based Belief Tracker](https://www.aclweb.org/anthology/W13-4067)

[Neural Belief Tracker](https://github.com/Garenpku/Paper-Reading/blob/master/Neural%20Belief%20Tracker.pdf)

[Word-Based Dialog State Tracker with RNN](https://github.com/Garenpku/Paper-Reading/blob/master/Word-Based%20DST%20with%20RNN.pdf)

## Policy Maker


## Natural Language Generator
This module takes the raw sentence, dialog state and the policy made by the system as input and generates a natural language sentence. Generally speaking rule-based, template-based and sequence mothods are used in this module.

[Semantically Conditioned LSTM for NLG](https://github.com/Garenpku/Paper-Reading/blob/master/Semantically%20Conditioned%20LSTM%20for%20NLG.pdf)

[Template-Based NLG](https://github.com/Garenpku/Paper-Reading/blob/master/Template-Based%20NLG.pdf)

### Knowledge-based Generation

[Usage of WordNet in Natural Language Generation](https://www.aclweb.org/anthology/W98-0718) 

# Datasets

[Ubuntu Dialog Corpus](https://arxiv.org/abs/1506.08909)  This corpus is collected from Ubuntu chat logs. Its topics are mostly about computer technology issues, which contains lots of terms, parameters and domain-specific actions. Alhough UDC contains massive data, it is a highly noisy dataset. Several papers using this dataset utilized a handcrafted term set and action set, to cope with the property of domain-specific.

[British National Corpus](https://www.english-corpora.org/bnc/) This corpus also contains massive dialogs, scripted from audio records of people's dialy dialogs. Being a **open-domain** dataset, its scenes include class, chitchatting, discussion about a certain topic and so on. To note that, as a real *spoken dialog* dataset, it is more difficult to model such dialogs because it requires better understanding of previous topics and an utterance frequently connects to the utterance at a distance. Also, people often introduce some auxiliary sentences such as "Well I think you are partly right but...", "What makes you think so?" and "Let me think... Oh I remember it!". In a word, a real daily dialog always involves pragmatic issues, whose meaning should be understood with not only the surface form of the utterances but also **knowledge of real world, previous experience between speakers, deictic issues and speech acts behind the sentences**. These issues make BNC a difficult corpus to handle.

[DailyDialog](https://arxiv.org/abs/1710.03957) This is also an open-domain dataset, whose dialogs are collected from websites serving for English learners to practice English in daily life. From the discription of its paper, this dataset has several properties: 1) written English; 2) the topic flow is relatively traceable as speakers are expected to talk about a certain topic; 3) external knowledge is less required as speakers are temporarily matched to talk. Thus it's easier than BNC.

[Twitter Dialog Corpus](https://github.com/Phylliida/Dialogue-Datasets/blob/master/TwitterConvCorpus.txt) Twitter dialogs are short and noisy, with frequent typos and internet words. Sentences are often incomplete.

[Wizard of Wikipedia](https://arxiv.org/abs/1811.01241) This dataset is created by crowdsourcing (and indeed with higher quality), where the user is expected to talk or ask about a certain topic and the wizard are given relevant knowledge from wikipedia and respond to the user. Within this topic the dialog goes deeper until the end. This dataset is also **written language**. It could also be used to carry out a multi-task learning combining **information retrieval** and **response generation**.

[Switchboard](https://catalog.ldc.upenn.edu/LDC97S62) Another spoken-language dataset. This serves as the base for [Jurafsky's work on Dialog Acts](https://web.stanford.edu/~jurafsky/ws97/manual.august1.html), with which a new DA tag set is defined. People in the field of discourse analysis found dialog acts useful for analyzing the structure of a discourse, for example see [this article](https://www.aclweb.org/anthology/W98-0319).
