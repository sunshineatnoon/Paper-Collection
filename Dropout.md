## Dropout

#### Main Idea
Randomly drop units (along with their connections) from the neural network during training.  If a unit is retained with probability p during training, the outgoing weights of that unit are multiplied by p at test time.

#### Why dropout works?
**From the view of co-adaption**
- Co-adaption: During training, units may change in a way that they fix up the mistakes of the other units.
- Dropout makes each hidden unit more robust and drives it towards creating useful features on its own without relying on other hidden units to correct its mistakes

**From the view of model assemble**

Training a neural network with dropout can be seen as training a collection of 2^n thinned networks with extensive weight sharing, where each thinned network gets trained very rarely, if at all. (n is the number of neurons in a network)

Each iteration sample a random ‘thinned’ network and train it using this batch of data.

When testing, all these networks' predictions are averaged by multiplying activations of each unit by p.

**An interesting and intuitive way to explain why Dropout work**
 > Ten conspiracies each involving five people is probably a better way to create havoc than one big conspiracy that requires fifty people to all play their parts correctly

#### TL;DR
Why does dropout work?
- It avoids co-adaption
- It's a kind of model assemble

#### Reference

Srivastava, Nitish, et al. "Dropout: a simple way to prevent neural networks from overfitting." Journal of Machine Learning Research 15.1 (2014): 1929-1958.
