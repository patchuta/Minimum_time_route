# Minimum_time_route
Minimum_time_route
 

I have created the above node diagram with the given data. All the nodes represent the airport codes and lines represent the routes.  The number of hours has been mentioned on the route line/path. It is based on Dijstras’s algorithm.
A python dictionary has been defined with all the nodes as keys and hours as the values.
Each node is a key and has a value which again a dictionary. 
The value dictionary has keys as destination airport nodes and the value as number of hours to reach from predecessor key node. The python dictionary is 

route = {
 'DUB':{'LHR':1,'CDG':2,'ORD':6},
 'LHR':{'DUB':1,'BKK':9,'NYC':5},
 'CDG':{'DUB':2,'BKK':9,'BOS':6},
 'ORD':{'LAS':2,'DUB':6},
 'BKK':{'SYD':11,'LHR':9,'CDG':9},
 'NYC':{'LAS':3,'LHR':5},
 'SYD':{'LAS':14,'LAX':13,'BKK':11},
 'BOS':{'CDG':6,'LAX':4},
 'LAX':{'SYD':13,'LAS':2,'BOS':4},
 'LAS':{'LAX':2,'ORD':2,'SYD':14,'NYC':3}
  }


The following elements has been defined to solve the problem.
shorttest_time={} 
shortest time or history and which is basically going to stored in the shortest the minimum cost to reach to a particular path. It records the coststo leads to that node which is basically going to be updated as we move along the route.

track_predecessor = {} 
keep track of the (predecessor node) path that has led us to this node to that node.

unseenNodes = route 
to iterate through the entire nodes so that we should not miss the shortest path.
infinity = 999999 # infinity can basically considered a very large number which is cumulative costs all the edges.

track_path = []
Which holds the nodes which led us to reach the goal /end node.
That means all the nodes from the source/start node to end/goal node. The sequence of nodes in this list is the optimal/short test path.

Initially, cost to reach the source node is zero (0) and infinity to all other nodes.

While loop -1

This makes or ensures that we have explored all the path.
We will compare all possible route costs and take the minimum cost path/route.

path_options

Once we reach minimum cost node , what are all the path options we can take.The ‘path_options’ will hold the path options.
In the ‘route’ dictionary, the minimum cost node has a value which again a dictionary. The value (dictionary) contains all the possible routes/paths as keys and respective hours as values.
With these values we will try to find shortest time to follow.

While loop -2

We would like traverse back from the end node and add them to the track_path list except the start node as the start node does not have predecessor.
After coming out of the loop, start node has been added.
