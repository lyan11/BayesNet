# Project Description
In this project, I implement the variable elimination algorithm used for
inference in Bayesian Networks.

## Description of Files
- bnet.py
    * In this file, I define the following classes:
        - *Variable*: the variables used in the Bayes Net
        - *Factor*: the factors used in the Bayes Net
        - *BN*: Bayes Net structure
    * The following procedures are implemented:
        - *multiply_factors*, *rec_multiply_factors*: These functions implement the factor multiplication algorithm which computes the product between multiple factors and results in a factor compatible with a single instantiation in each factor.
        - *restrict_factor*, *rec_restrict_factor*: These functions implement the factor restriction algorithm which takes as input a single factor, a variable *V* and a value *d* from the domain of that variable; the algorithm then creates and returns a new factor that is the restriction of the input factor to the assignment *V = d*.
        - *sum_out_variable*, *rec_sumout_vars*: These functions implement the variable summation algorithm which eliminates a single variable *v* from a set *F* of factors, and returns the resulting set of factors.
        - *min_fill_ordering*, *min_fill_var*, *compute_fill*, *remove_var*: These functions construct an undirected graph showing variable relations expressed by all conditional probability tables, and eliminate the variable which would result in the least edges to be added post elimination. This heuristic helps in bypassing the NP-hard problem of finding the optimal order in which to eliminate variables.
        - *step_1*, *step_2*, *step_3*, *VE*: The *VE* function implements the variable elimination algorithm, which takes as input a Bayes Net object (instance of BN), a variable that is the query variable *Q*, and a list of variables *E* that are the evidence variables (all of which had some value set as evidence using the variable's *set_evidence* method). The algorithm computes the probability of every possible assignment to *Q* given the evidence specified by the evidence settings of the evidence variables. The function returns these probabilities as a list where every number corresponds to the probability of one of *Q*'s possible values. The *step_1*, *step_2*, and *step_3* helper functions run the sub-procedures that make up the variable elimination algorithm.
- test_cases.py
    * This file contains test cases that ensure that the Variable Elimination algorithm as well as all of its sub-processes are all correctly implemented.

### Technology required to run the code
- Python3
