# One-more-Algo

# DIJIKSTRA ALGORITHM

# Introduction

This is the third post in the Graph Traversals – Online Classes.

After learning how to move through a graph, we might be interested in learning more. One interesting problem is determining the shortest path between two vertices of a graph.
The problem can be extended and defined in many other forms. I prefer to call it “minimizing the cost”. For e.g.

When we measure the cost in terms of the distances between vertices, it can be called as the Shortest Path.
When we measure the cost in terms of the money spent between vertices, it can be called as the Cheapest Path.
When we measure the cost in terms of the time spent between vertices, it can be called as the Fastest Path.
There can be many more interpretations for this problem. Also, this means that the algorithm can be used to solve variety of problems and not just shortest path ones.

# Avoiding Confusions about shortest path

# There are few points I would like to clarify before we discuss the algorithm.

There can be more than one shortest path between two vertices in a graph.
The shortest path may not pass through all the vertices.
It is easier to find the shortest path from the source vertex to each of the vertices and then evaluate the path between the vertices we are interested in.
This algorithm can be used for directed as well as un-directed graphs
For the sake of simplicity, we will only consider graphs with non-negative edges.
Note : This is not the only algorithm to find the shortest path, few more like Bellman-Ford, Floyd-Warshall, Johnson’s algorithm are interesting as well.

# Explanation – Shortest Path using Dijkstra’s Algorithm

# The idea of the algorithm is very simple.

It maintains a list of unvisited vertices.
It chooses a vertex (the source) and assigns a maximum possible cost (i.e. infinity) to every other vertex.
The cost of the source remains zero as it actually takes nothing to reach from the source vertex to itself.
In every subsequent step of the algorithm it tries to improve(minimize) the cost for each vertex. Here the cost can be distance, money or time taken to reach that vertex from the source vertex. The minimization of cost is a multi-step process.
For each unvisited neighbor (vertex 2, vertex 3, vertex 4) of the current vertex (vertex 1) calculate the new cost from the vertex (vertex 1).
For e.g. the new cost of vertex 2 is calculated as the minimum of the two ( (existing cost of vertex 2) or (sum of cost of vertex 1 + the cost of edge from vertex 1 to vertex 2) )
When all the neighbors of the current node are considered, it marks the current node as visited and is removed from the unvisited list.
Select a vertex from the list of unvisited nodes (which has the smallest cost) and repeat step 4.
At the end there will be no possibilities to improve it further and then the algorithm ends
