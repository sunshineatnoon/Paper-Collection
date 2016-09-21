# k-means++: The advantages of careful seeding

## Contributions
New initialization method to make k-means more accurate and fast.

## Algorithm (Initialization of k-means)
1. Choose an initial center uniformly at random from dataset X.
2. choose the next center c = x' with probability, D(x) is the distance bewteen x and the closest center that we've already choosen.

   ![](https://raw.githubusercontent.com/sunshineatnoon/Paper-Collection/master/images/kmean%2B%2B.png)
3. Repeat Step 1 until we choose a total of k centers.
4. Continue the standard k-means algorithm.

## TL;DR
1. The above initialization algorithm makes intuitive sense. By choosing the point that is far from its assigned center to be the next center, one can get k centers that are distant from each other. This way kmeans will converge faster and more likely to stop at a better minima. 
2. [sklearn](http://scikit-learn.org/stable/modules/clustering.html#k-means) has a good implementation of this algorithm.
## Reference
Arthur D, Vassilvitskii S. k-means++: The advantages of careful seeding[C]//Proceedings of the eighteenth annual ACM-SIAM symposium on Discrete algorithms. Society for Industrial and Applied Mathematics, 2007: 1027-1035.
