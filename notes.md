### Information Accretion (IA)

Information accretion is a measure of how much information is added to an ontology annotation by node $v$ given that its parents $pa(v)$ are already annotated. It is defined as:
$$ ia(v) = \log_2 \frac{1}{Pr(v|pa(v))} = \log_2 \frac{Pr(Pa(v))}{Pr(Pa(v)|v)Pr(v)}.$$

Since annotation of the term corresponding to node $v$ implies the annotation of terms $Pa(v)$ to guarantee a consistent subgraph we have that $Pr(Pa(v)|v)=1$ and therefore:
$$ ia(v) = \log_2 \frac{Pr(Pa(v))}{Pr(v)}.$$

To calculate these probabilities, we use the observed annotations in a dataset as the empirical distribution on which to estimate the probabilities. Thus, Pr(v) is computed as the number of examples (proteins) annotated with the term corresponding to node v (divided by the total number of proteins) and Pr(Pa(v)) as the number of examples annotated with the terms corresponding to nodes Pa(v) (divided by the total number of proteins).

To avoid division by zero, a Laplace smoother is used
$$\overline{ia}(v) = \log_2 \frac{Pr(Pa(v))+1}{Pr(v)+1}.$$

### Protein language models

A protein language model is a machine learning model that is specifically designed to predict masked or incomplete parts of protein sequences. This type of model is useful because it is able to learn the underlying patterns and structure of a protein "language" in order to make educated guesses about missing or masked data. 

