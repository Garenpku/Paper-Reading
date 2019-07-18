This paper introduces a neural method for the NLG module of a dialog system. 

Formally we want to model the probability $p(\textbf{w}|\textbf{d};\theta)$, where $d$ is the semantic input (for example the dialog act together with slots and values $action(s(v))$ ). We use a RNN as the language model to provide the probability distribution so that we can choose $argmax_w\ p(w|\textbf{d};\theta)$ = $ \Pi_{i=1}^np(w_i|w_{1:i-1},\textbf{d};\theta)$.

As stated in the paper, if we simply map the semantic input to a vector $d$ as input and send it to LSTM, due to the problem of gradient vanishing its effect will gradually diminish. If feeding $d$ at each step, we'll face the problem of **duplication** of the semantic labels. 

Following the thoughts of *memory* and *forget* in LSTM, the authors designed another gate for the semantic part. That gate takes the last state and current output as input, renews gate state and changes the weight paid on semantic part, formally written as:
$$
\begin{align}
r_t &= \sigma(W_{wr}w_t + W_{hr}h_{t-1})\\
d_t &= r_t \circ d_{t-1}
\end{align}
$$
And the cell state of LSTM is updated as:
$$
c_t = f_t \circ c_{t-1} + i_t \circ \hat{c}_t + tanh(W_{dc}d_t)
$$
More improvements are tried in this paper, which we leave out here. For full paper see [this link](https://arxiv.org/pdf/1508.01745.pdf).

