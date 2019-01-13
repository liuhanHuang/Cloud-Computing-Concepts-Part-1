# Membership Protocol

All cloud computing systems need to run a membership protocol in order to detect process (node) failures, and to incorporate new and leaving nodes. 

This project is about implementing such a membership protocol. Since it is infeasible to run a thousand cluster nodes (peers) over a real network, an implementation of an emulated network layer (EmulNet) is provided here. This membership protocol implementation will sit above EmulNet in a peer-to-peer (P2P) layer, but below an App layer. Think of this like a three layer protocol stack with Application, P2P, and EmulNet as the three layers (from top to bottom).

There are several implementations of membership protocols: all-to-all heartbeating, gossip-style heartbeating, or SWIM-style membership. In this project, gossip-style protocol is used. This protocol should satisfy:

1) Completeness all the time: every non-faulty process must detect every node join, failure, and leave;
2) Accuracy of failure detection when there are no message losses and message delays are small.
3) When there are message losses, completeness must be satisfied and accuracy must be
high. 
4) It must achieve all of these even under simultaneous multiple failures.