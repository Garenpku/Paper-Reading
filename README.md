This repository tries to give a comprehensive field search about dialog systems. For a general introduction see [this article](https://github.com/Garenpku/Paper-Reading/blob/master/intro%20to%20dialog%20system.md).

# Open-domain Dialog Agents

# Domain-specific Dialog Agents

# Datasets
[DailyDialog](https://arxiv.org/abs/1710.03957)

[Ubuntu Dialog Corpus](https://arxiv.org/abs/1506.08909)  This corpus is collected from Ubuntu chat logs. Its topics are mostly about computer technology issues, which contains lots of terms, parameters and domain-specific actions. Alhough UDC contains massive data, it is a highly noisy dataset. Several papers using this dataset utilized a handcrafted term set and action set, to cope with the property of domain-specific.

[British National Corpus](https://www.english-corpora.org/bnc/) This corpus also contains massive dialogs, scripted from audio records of people's dialy dialogs. Being a **open-domain** dataset, its scenes include class, chitchatting, discussion about a certain topic and so on. To note that, as a real *spoken dialog* dataset, it is more difficult to model such dialogs because it requires better understanding of previous topics and an utterance frequently connects to the utterance at a distance. Also, people often introduce some auxiliary sentences such as "Well I think you are partly right but...", "What makes you think so?" and "Let me think... Oh I remember it!". In a word, a real daily dialog always involves pragmatic issues, whose meaning should be understood with not only the surface form of the utterances but also **knowledge of real world, previous experience between speakers, deictic issues and speech acts behind the sentences**. These issues make BNC a difficult corpus to handle.
