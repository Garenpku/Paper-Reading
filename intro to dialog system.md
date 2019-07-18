
# Chatbots
## Rule-based Systems
By picking the most probable keyword from a sentence, and apply the most probable rule to this keyword. The keyword should be as interesting as possible, such as words referring to entities, events and thoughts, to make the response meaningful.

In an early NLG system **ELIZA**, a smart mechanism is applied -- **memory**. That is, it recognizes a set of keywords, transfer a certain part of that sentence and store it in the memory. Afterwards if the system finds no response to the current utterance, it could search the memory for help.

Later systems even are designed to have a state of mind such as fear and angry. This state could affect the choice of response.

## IR-based Systems
Another way to make response to an utterance is to directly retrieve a existing sentence in a corpus. In such a system, a similarity function is designed, and each response is selected according to the similarity score. In general, two methods could be used: choosing the sentence with the highest score and choosing the response to the sentence with the highest score. However, according to Jurafsky, the former seems to be better, which may be due to the inefficiency of the similarity measurement (feature representation included).

## Sequence-to-Sequence Systems
The similarity of **machine translation** and **Response Gneration** has long been discussed. Early work was to apply the models of SMT to NLG. However this doesn't work well because the alignment of the utterance and response are not strict. Also, the response could be extremely diverse and not restricted to a certain form. After seq2seq mechanisms are designed, people find this method more suitable for NLG systems, as its generation process $p(r|s)$ are controlled by hidden variables, where the distribution is not handcrafted nor restricted to a rigid scope. However this flexibility could also be a flaw -- it's harder for us to manage the state of the conversation as it is controlled by an unexplannable process. So it's hard for a vanilla seq2seq model to respond in a multi-turn dialogue.

# Frame Based Dialog Agents
To model a conversation in a multi-turn scene, we have to explicitly model the state of the current conversation. The state could be seen as the information of previously discussed topics. Imagine you are taking part in a ongoing conversation about a book. By the time you can say something relevant to their topic, you have to be informed that they've finished talking about the writer and are giving opinions about the plot. With those in mind, you can say something about the characters in the book (continue the discussion of the content), or instead ask them about where you can buy the book. This shows the basic understanding of a dialog: people choose a topic, and chat about the elements that comprise of this topic one by one. When speaking, they can talk about one or several elements at a time, or they can even switch to other topics and set it as the ground of the current dialog.

**Frame** is such an ontology that are utilized to put our daily dialogs under control. A frame is a scene, the ground of people's discussion. Associated with frames there are **frame elements**, which are the basic parts to talk about in this scene. In this ontoloty there are more information defined such as the relation between frames and properties of frame elements.

Frame and similar ontologies are welcomed in task-oriented dialogs. In those dialogs, men are required to give only the information relevant to a certain topic, such as flight tickets booking and route planning. The dialogs are not for chatting but for retrieving information from the database, so the response don't have to be diverse. The machine just have to detect the domain and the frame they are talking about, and extract information from utterances to fill into the slots(frame elements). 

Associated with dialogs there are four main parts which form a pipeline for a dialog system -- NLU, dialogue state manager, policy maker and NLG. Such a system is better defined in domain-specific scenes than open domain scenes. As a simple illustration, NLU is to detect intention and extract slot information from utterances; DSM is to organize the input information from NLU within a pre-defined structure (for example the frame ontology); policy maker is to query the databse and fetch the useful information; NLG is to organize the retrieved information into natural language sentences.

# Comparison between domain-specific and open-domain dialos 
In open-domain fields, people tend to use end-to-end seq2seq methods, in order to get more diverse responses. But for most models dialog state manager is missing, which makes the multi-turn dialog uncontrollable. Let's first think about the difficulties of incorporating DSM into open-domain dialog systems:

1.The dialog will have a main thread and several auxiliary threads. In a daily conversation, a person might say something that is loosely connected to their ongoing topic but still can evoke some frames, for example: "Last time we talked about War and Peace. *I don't know how you think of this book but I love it.* Its epiction of the war is so impressing..." Here the frame **Text** is evoked, and within this frame people can talk about its topic, title, author and so on. But the italic sentence is not part of this frame. Instead, it evokes another frame, though after this sentence the frame comes to the end. As we can see here, jumping between frames are more often in open-domain dialogs and some are not really the main topic people concern.

2.The relations of frames within the main thread. While talking, people can expand a subpart of the current topic as a new main topic, or just shift to a brand-new topic that has nothing to do with the current one. (TO BE CONTINUED)
