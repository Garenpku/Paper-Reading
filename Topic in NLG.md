Topic can be viewed as a abstract representation associated with words, sentences and documents. It is regarded by most as a latent variable, and in those models, words are generated conditioning on that latent variable. Some higher-level parameters control the chosen of topics of a sentence or document, which are the object of the optimization process.

In mainstream work, a topic is not explicitly given by a pre-defined set. Rather it is understood by the whole vocabulary. Formally, a topic *k* is a vector $t^k$ over the vocabulary *V*. The i-th element $t_i^k$ corresbonds to the i-th word in *V*. As you can see, the meaning of a topic is portraited by the words it prefers. With well-chosen parameters, the topics are expected to be distinct, meaningful and coherent.

The most famous probabilistic topic model is given by [Jordan et. al.(2003)](http://www.jmlr.org/papers/v3/blei03a.html), namely **Latent Dirichlet Allocation**. It is a generative model. Two sets of parameters $\alpha$ and $\beta$ are defined to initialize the whole generation process. For each document indexed as *t*, the "topic ground" $\theta_t$ is sampled from *Dirichlet($\alpha$)*. The length *N* is sample from $Poisson(\epsilon)$. Then for word $w_{1, 2,..., N}$, we first choose a topic *t* from $Multinomial(\theta_t)$, then sample $w_i$ from the given distribution $p(w|t, \beta)$.
# topic generation

# topic detection
