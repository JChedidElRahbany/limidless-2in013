IDs = "no forgetting" = exponential time and space complexity = exhaustive enumeration over possibilities
solutions : variable elimination, junction tree, decomposition
exact IDs = slow
local generalisation )= LIMIDs = less slow
d-separation = identifying relevant variables
# Graphical models
$\mathcal{M}$ is a model defined by the tuple
$\langle \mathbf{X}, \mathbf{D}, \mathbf{F}\rangle$ where
$\mathbf{X} = \{X_1,\dots,X_n\}$ the *discrete* random variables
$\mathbf{D}=\{D_1,\dots,D_n\}$ their corresponding domains of values
$\mathbf{F} = \{F_1(\mathbf{X}_1),\dots,F_r(\mathbf{X}_r)\}$ the relations between the variables (arcs in the graph) or the utility function over those variables, here $F_k \in \mathbf{F}$ is defined over a subset $\mathbf{X}_k \subseteq \mathbf{X}$, and its scope is denoted $\text{sc}(F_k)$ 
and we define $P(\mathbf{X}) = \frac{1}{Z}\prod_{F_k \in \mathbf{F}}F_k(\mathbf{X}_k)$ as the joint probabilitiy of $\{X_1,\dots,X_n\}$ 
and $Z$ is to normalise $P(X)$ to ensure that that $\sum_{\mathbf{X}} P(X) = 1$  
Join-tree (junction tree) is obtained by moralising the graph and triangulating, letting us do exact inference thru message passing
Join-graph allows for loops resulting in a strcture thats not a tree, but allows of approximate inference thru loopy message propagation