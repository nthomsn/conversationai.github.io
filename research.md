[Back to Conversation AI Research Overview](index.md)

# Research resources

This page outlines the high level questions we are exploring. Further related research can be found on the [WikiDetox outline of related work](https://meta.wikimedia.org/wiki/Research:Detox/Resources).

We also have a page that provides [a brief introduction to ML](ml_intro.md) to help make this research easier to understand.

## Public datasets

One of our contributions is to produce datasets to support research:

   * [Wikipedia Human Annotations of Personal Attacks on Talk Pages](https://figshare.com/articles/Wikipedia_Detox_Data/4054689): 100k Comments from wikipedia each with 10 annotations by the 4000 annotators who contributed to the effort. Each comment annotation notes whether the annotator considers the comment to be a personal attack or not.
   * [Wikipedia Machine Annotations of Talk Pages](https://figshare.com/articles/Wikipedia_Talk_Corpus/4264973): machine-labelled annotations for every English Wikipedia talk page comment from 2001 to 2015, approximately 95 million comments to support large scale data analysis.
   * To submit a link to an existing public dataset, or get help creating new public data sets for related research please fill out [this form](https://goo.gl/forms/z3JatRhT5x53Xa0I2).
   * [Wikipedia Human Annotations of Toxicity on Talk Pages](https://figshare.com/articles/Wikipedia_Talk_Labels_Toxicity/4563973): 160k human labelled annotations based on asking 5000 crowd-workers to rate Wikipedia comments according to thier toxicity (likely to make others leave the conversation). Each comment was rated by 10 crowd-workers.

## Research questions

The following are our key research questions.

### How might machine learning methods help online conversations?

We hypothesise that machine learning can help focus human attention more effectively. Our initial research is summerized in our blog post [Algorithms And Insults: Scaling Up Our Understanding Of Harassment On Wikipedia](https://medium.com/jigsaw/algorithms-and-insults-scaling-up-our-understanding-of-harassment-on-wikipedia-6cc417b9f7ff). 

### Machine learning to help understand harassment at scale?

In [Ex Machina: Personal Attacks Seen at Scale](https://arxiv.org/abs/1610.08914), we outline how crowdsourcing and machine learning can be used to analyze personal attacks at scale, and applies the methods to help understand the challenge on Wikipedia.

### What role does toxic language have in reducing the number of viewpoints in a discussion?

### What tools are needed to make robust open debate on important issues easier at scale?

### How might machine learning based tool be used by communities, commenters and authors?

We've developed [an opensource moderation tool](https://github.com/conversationai/conversationai-moderator/) to [enable the New York Times to spend more moderator time supporting their community](https://www.nytimes.com/2017/06/13/insider/have-a-comment-leave-a-comment.html).

### What aspects of a conversation can machine learning understand?

Can machine learning methods understand the emotional impact of language?

How much of the structure of a conversation can machine learning approaches uncover?

### What are the risks and challenges of using machine learning to assist online conversations?

What unintended and unfair biases might machine learning models contain? What impact might such biases have? What are the best ways to identify these biases? and what can be done mitigate them?

 * See [Attacking discrimination with smarter machine learning](https://research.google.com/bigpicture/attacking-discrimination-in-ml/) for a great introduction to the problem. Challenges related machine learning bias, fairness and algorithmic bias are outlined further on our [unintended bias page](bias.md).

 * In [Measuring and Mitigating Unintended Bias for Text Classification](https://github.com/conversationai/unintended-ml-bias-analysis/blob/master/presentations/measuring-mitigating-unintended-bias-paper.pdf) we have developed methods for measuing the unintended bias in a text classifier according to terms that appear in the text, as well as approaches to help mitigate them.

### How might machine learning based tool be gamed?

 * Word based models, including the CNN we developed for toxicty, can be tricked easily by creative misspellings. Using character level models can help address this, but require more data and their training suffers from [the vanishing gradient problem](https://en.wikipedia.org/wiki/Vanishing_gradient_problem).

 * Models based on character-level ngrams fed into feed-forward networks, like our TOXICITY_FAST model, can be easily gamed by adding additional ngrams after the initial comment that counter the signal from the problematic ngrams. This can be addressed by using RNNs and CNNs, like our TOXICITY model which take account of more of the textual context.

 * The practical impact of gaming ML models is an open research question, and is likely to depend on way the ML is applied. Moreover, there are different threat models for different applications of ML: gaming of an authorship experience is quite different to the recieving suggestions and considering retraining on them.

 * The research of [Cheng et. al.](https://arxiv.org/abs/1702.01119) and [Wulczyn et. al.](https://arxiv.org/abs/1610.08914) suggest that the majority of toxic contributions are not from people who would be incentivised to game models, but from people having a 'bad day'.

### How might ML be misused to censor or reduce viewpoints in a conversation?

ML is a very general technology and can be used in many ways. Part of our research is into possible mis-uses of such technology, for example, we've published a survey paper on [Network Traffic Obfuscation and Automated Internet Censorship
](https://arxiv.org/abs/1605.04044).
