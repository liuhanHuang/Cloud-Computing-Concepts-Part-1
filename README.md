# Membership Protocol

All cloud computing systems need to run a membership protocol in order to detect process (node) failures, and to incorporate new and leaving nodes. 

This project is about implementing such a membership protocol. Since it is infeasible to run a thousand cluster nodes (peers) over a real network, an implementation of an emulated network layer (EmulNet) is provided here. This membership protocol implementation will sit above EmulNet in a peer-to-peer (P2P) layer, but below an App layer. Think of this like a three layer protocol stack with Application, P2P, and EmulNet as the three layers (from top to bottom).
