# APBFT
This code improves the traditional PBFT consensus protocol by assigning scores to nodes based on their behavior.
## Related paper
The details of the proposed APBFT protocol can be found on our paper: "APBFT: An Adaptive PBFT Consensus for Private Blockchains".
For citation, please use: 
K. Riahi, M. -e. -A. Brahmia, A. Abouaissa and L. Idoumghar, "APBFT: An Adaptive PBFT Consensus for Private Blockchains," GLOBECOM 2022 - 2022 IEEE Global Communications Conference, Rio de Janeiro, Brazil, 2022, pp. 1788-1793, doi: 10.1109/GLOBECOM48099.2022.10001568.
## How to run the code
We advise opening the whole project in an editor such as VSCode.
In the main.py file, many parameters can be adjusted. Note that all the durations are in seconds.
- In line 9, we define the time limit the client waits before resending the same request if no response was received within that duration. We advise adapting it to the number of nodes in the network (more nodes leads to longer delays).
- In line 10, we set the time limit the nodes wait before asking for a view change if the primary fails in validating the clients requests.
- In line 14, we can change the proportion of nodes we want to keep in the consensus set. The other nodes are eliminated and do not participate in the consensus. "1/2" means that only one-half of the nodes are kept in the consensus. That's exactly the novelty of our proposed APBFT.
- From line 16 to 23, the types of nodes we want to launch in our simulation are defined.
- In line 39, we can define the number of clients sending different requests through the network.
- In line 46, we define the waiting time between the clients requests.

After defining all these parameters, run the main.py file and wait for the consensus to be reached. Once reached, a message will appear, like the following: "Client 0 got reply within 0.045779 seconds. The network exchanged 36 messages" which gives the delay required to validate the actual request as well as the number of exchanged messages through the network.
