# Eager Execution
- standard execution method
- means operations are executed by python and run operation by operation and return results back to python

# Graph Execution
- enables portability outside of python
- tends to offer better performance 
- tensor operations are being executed as a TF Graph
- Graphs are data structures that contain a set of tf.Operation objects which represent units of computation; and tf.Tensor objects, which represent the units of data that flow between operation
- Since these graphs are datastructures they can be saved, run and restored outside of python
- example: two-layer neural network as graph
![[Pasted image 20240708162031.png]]

- functions can be used as graphs by using the tf.graphs decorator
- python specific logic (if, else statements, loops) need to undergo an extra step to become part of the graph, TF uses TF.autograph for that
- the code of the tf.function in this mode only gets executed once per created graph, therefore things like print statements don't get called if the function is called but only when a graph is created

### Polymorphism
- Every TF function consists of several graphs. A tf.Graph is specialized to a specific input. 
- Every time the function gets called with new arguments (shape or dtypes), it creates a new graph for that specific argument