
# Chatbots
## Rule-based Systems
By picking the most probable keyword from a sentence, and apply the most probable rule to this keyword. The keyword should be as interesting as possible, such as words referring to entities, events and thoughts, to make the response meaningful.

In an early NLG system **ELIZA**, a smart mechanism is applied -- **memory**. That is, it recognizes a set of keywords, transfer a certain part of that sentence and store it in the memory. Afterwards if the system finds no response to the current utterance, it could search the memory for help.

Later systems even are designed to have a state of mind such as fear and angry. This state could affect the choice of response.

## IR-based Systems
Another way to make response to an utterance is to directly retrieve a existing sentence in a corpus. In such a system, a similarity function is designed, and each response is selected according to the similarity score. In general, two methods could be used: choosing the sentence with the highest score and choosing the response to the sentence with the highest score. However, according to Jurafsky, the former seems to be better, which may be due to the inefficiency of the similarity measurement (feature representation included).

## Sequence-to-Sequence Systems
The similarity of **machine translation** and **Response Gneration** has long been discussed. Early work was to apply the models of SMT to NLG. However this doesn't work well because the alignment of the utterance and response are not strict. Also, the response could be extremely diverse and not restricted to a certain form. After seq2seq mechanisms are designed, people find this method more suitable for NLG systems, as its generation process $p(r|s)$ are controlled by hidden variables, where the distribution is not handcrafted nor restricted to a rigid scope. However this flexibility could also be a flaw -- it's harder for us to manage the state of the conversation as it is controlled by an unexplannable process. So it's hard for a vanilla seq2seq model to respond in a multi-turn dialogue.
