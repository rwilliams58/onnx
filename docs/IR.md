Open Neural Network Exchange (ONNX)
=========

ONNX is an open specification that consists of the following components:

1)  A definition of an extensible computation graph model

2)  Definitions of built-in operators and standard data types

__Notes on language in this and all related documents__:

1. The use of SHOULD, MUST, MAY and so on in this document is consistent with [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

2. The use of 'list' shall denote an ordered collection of items, 'set' shall denote an unordered collection of unique elements, and 'bag' an unordered collection of possibly non-unique elements.

Extensible computation graph model
----------------------------------

ONNX specifies the portable, serialized format of the computation graph. It may not be the form a framework chooses to use and
manipulate. For example, a framework may keep the graph in memory in a format that it finds more efficient to
manipulate for optimization passes. We make use of protobuf2 (with oneof, added in protobuf 2.6.1) for the serialized format.

### Graphs

Each computation dataflow graph is structured as a list of nodes that form a graph. These nodes MUST be free of cycles.
Nodes have one or more inputs and one or more outputs, and each node is a call to an operator.
