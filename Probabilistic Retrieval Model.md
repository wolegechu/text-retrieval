# Probabilistic Retrieval Model

## Basic Idea

### Many Different Retrieval Models
- Probabilistic models: $f(d,q) = p(R=1|d,q), \quad R\in \{0,1\}$
    - Classic probabilistic model -> BM25
    - **Language model -> Query Likilihood**
    - Divergence-from-randomness model -> PL2

$$ p(R=1|d,q) \approx p(q|d,R=1)$$

> Means if a user likes document d, how likely would the user enter query q (in order to retrieval d)?
> 
> Assumption: A user formulates a query based on an "**imaginary relevant document**"

### Summary
- Relevance(q,d) = $ p(R=1|d,q) \to p(q|d,R=1)$
- **Query likelihood** ranking function: f(q,d) = p(q|,d)
    - Probability that a user who likes d would pose query q
- How to compute p(q|d)? How to compute probability of text in general? -> **Language Model**

## Statistical Language Model
![](media/15000435843702.jpg)

### Why is a LM Useful?
- Quantify the uncertainties in natural language
- Allows us to answer questions like:
    - Given that we see "John" and "feels", how likely will we see "happy" as opposed to "habit" as the next word? (**speech recognition**)
    - Given that we observe "baseball" three times and "game" once in a news article, how likely is about "sports"?(**text categorization, information retrieval**)
    - Given that a user is interested in sports news, how likely would the user use "baseball" in a query?(**information retrieval**)

    ### The Simplest language Model: Unigram LM
    - Generate text by generating each word INDEPENDENTLY
    - Thus, $p(w_1 w_2 ... w_3)=p(w_1)p(w_2)...p(w_n)$
    - Parameters: {p(w_i)} and the sum is 1
    - Text = sample drawn according to this word distribution

![](media/15000455583240.jpg)
![](media/15000462873656.jpg)
### Summary
- Language Model = probability distribution over text
- Unigram Language Model = word distribution
- Use of a Language Model
    - Representing topics
    - Discovering word associations

