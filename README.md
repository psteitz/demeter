# demeter
Collaborative learning network

## Definitions
A _node_ is an execution unit that responds to messages, performs a computation and then optionally sends messages to other nodes.
Input messages include context headers which are propagated to successors, possibly modified during a node's execution.

Nodes have _features_ that parameterize their execution. Some node features are hard-coded, some are set at design time when creating flows and some may be learned.  Learnable features are called _parameters_.  

Executions of node activations can be influenced by
  1. the context passed in the context header
  2. the values of the node's features when a message comes in
  3. data in the message payload
  4. Other data that the node acquires during execution

A _trajectory_ is a sequence of node activations.

A _generation_ is a set of trajectories realized by a set of nodes.  Generations can be time-based or based on continuing all trajectories until no activated nodes produce any successors.

A _flow_ is a directed graph of node types representing a possible trajectory.  So if $n_1, n_2, n_3$ are node types in a flow, it is possible for some input message to an instance of $n_1$ to leed to execution of an instance of $n_2$ and then an instance of $n_3$. Flows may contain cycles.  Flows don't have to terminate.

An _ensemble_ is the set of nodes involved in a generation.

## Learning
When generations end, final context amd terminal-node specific data are provided to a loss function, which may also acquire and use external data.  The loss function incorporates data from all final nodes in an ensemble.  Based on the loss, parameters in all nodes in the ensemble may be updated.








     
