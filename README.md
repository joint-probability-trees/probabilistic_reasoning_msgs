# Welcome to the probabilistic_reasoning_msgs package

This package contains interface definitions for probabilistic reasoning
with ROS services. A common type for describing variables is a json serialized
dictionary mapping from variables from values. This datatype is inspired from
jpt.variables.VariableAssignment and further documentation can be read in
the jpts documentation (TODO reference to online hosted documentation).

An example for such a datastructure is 

`{"symbolic": "A", "integer": [1, 2, 3], "numeric": [0., 0.5]}`

describes that the variable named `symbolic` has the value `A`,
the variable named `integer` has the value `1, 2` or `3` and the variable named `numeric` is in the range of `0` to `0.5`.
asks the model for the most probable explanation

Defined inference types are
- Marginal probabilities and conditional probabilities via the infer service. 
(srv/infer.srv)
- Most probable explanations (modes) via the mpe service. (srv/mpe.srv)
- Sampling from the MPE state. (srv/sample_mpe.srv)
- Applying "permanent" evidence to the model. (srv/apply_evidence.srv) 

Further information about the limits probabilistic inference is found in
http://starai.cs.ucla.edu/papers/ProbCirc20.pdf.