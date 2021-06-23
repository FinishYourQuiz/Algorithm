<p style="text-align: center; font-weight: bold; font-size: 20pt"> Greedy algorithm</p>

### > **interval Scheduling**
----

### > **An Exchange Argument**

----

### > **Applied to Graph**
<br>

### **1. Some definitions and basic algorithm**
#### **Connectivity:** 
*Connected*: For an undirected graph, every pair of nodes u and v, there is a path from u to v. <br>
*Strongly connected*: For a directed graph, for two every nodes u and v, there is a path from u to v and a path from v to u.

#### **Trees:** An undirected graph is a tree if it is connected and does not contain a circle.

#### **Directed Acyclic Graph(DAG):** A directed graph has no cycle.

#### **Graph Traversal:**
*Breath First Search*(BFS) : Explore outwards from s in all possible directions, addig nodes one "layer" at a time.<br>
*Depth First Search*(BFS) : Explore outwards from s by going as deeply as possible and only treating when necessary.

<br>


### **2. Topological**
#### - **Topological Ordering:** For a directed graph G, we say that a topological ordering of G is an ordering of its nodes as v1, v2, v3, ..., vn so that for every edge (vi, vj), we have i<j.

<ol type='1' style="font-size: 11pt">
    <li>Properties of Topological
        <ul style="font-size: 10pt; font-weight: bold">
        <li>In every DAG, there is a node v with no incoming edge.</li>
        <li>If G has a topological ordering, then G is a DAG</li>
        <li>If G is a DAG, then G has a topological ordering.</li>
        </ul>
    </li>
    <li>Compute a Topological Ordering
        <br>
        <code style="font-size: 12px">
            Find a node v with no incoming edge and order it first<br>
            Delete v from G<br>
            Recursively compute a topological ordering of G-{v} and append this order after v
        </code>
    </li>

</ol>
<br>

### **3. Shortest Path Algorithm: Dijkstra**
<ol style="font-size: 12pt">
    <li> Idea of Algorithm
        <ol start='-1' reversed style="font-size: 15px">
            <li>Create a array A, that keeps track of vertices included in shortest path tree from the start point s.</li>
            <li>Assign a distance value to all vertices in A, assign INFINITE for all points expect assign 0 for s. </li>
            <li>While not meet target t:<br>
                - Select vertex u with minimum value.<br> 
                - For every adjacent vertices v, compare the distance by passing u to v, d0, and distance passing v, d1.<br>
                - If d1 > d0, update the A[i] for v to d0.
            </li>    
        </ol>
    </li>
    <li>Example</li>
</ol>
<br>

### **4. Minimum Spaning Trees**
#### - **Minimum Spaning Trees:** A minimum spaning tree T of a connected graph G is a subgraph of G with same vertices, which is a tree, and among all such trees it is of minimum total length of all edges in T.

#### - **Property:** Let G be a connected graph with all length of edges E of G distinct and S a non empty proper subset of the set of all vertices V of G. Assume that e = (u, v) is an edge such that u in S and v not in S and e is of minimal length among all the edges having this property. Then e must belong to every minimum spaning tree T of G.
<ol style="font-size: 12pt; margin-top: 10px">
    <li> The Kruskal Algorithm
        <ol style="font-size: 14px">
            <li> We order the edges in E in a non-dcreasing order with respect to their weights.</li>
            <li>We build a tree by adding edges, one at each step of construction.</li>
            <li>An edge e<span style="font-size: 10px">i</span> is added at a round of i of construction, if this addition does not cause a cycle in the graph. </li>
            <li>If adding an edge does get a cycle, this edge will be discarded.</li>
            <li>The process terminates when the list of all edges has been exhausted.</li>
        </ol>
    </li>
    <li style="margin-top:5px">Implementation of Kruskal
        <ul>
            <li>Data Structure: Union-Find</li>
            <li>Methods/Operations
                <ul style="font-size: 16px">
                    <li>MakeUnionFind(S) -- O(n)<br>
                        <span style="font-size: 14px">given a set S returns a structure in which all elements are placed into distinct singleton sets. </span>
                    </li>
                    <li>Find(v) -- O(1)<br>
                        <span style="font-size: 14px">given an element v returns the label(set) which v belongs.    </span>
                    </li>
                    <li>Union(A, B) -- O(k log k)<br>
                        <span style="font-size: 14px">given two sets A, B changes the data structure by replaing sets A and b with the set AUB.     </span>
                    </li>
                </ul>
            </li>
            <li>Steps of using methods
                <ol>
                    <li>Use Union-Find data stucture to keep tract of the sets of vertices of the graph, assume the set S = {1, 2, ..., n}</li>
                    <li>Using array A such that A[i] = j means that i belongs to set labeled j,<br>Using array B such that B[i] contains the number of elements labeled as i, and the pointers to the 1st and the last element of a linked list of elements labeled as i.</li>
                    <li>UNION(i, j) of two sets by labeled i and j:
                        <ul>
                            <li> If B[i].number >= B[j].number, update the elements labeled by i in A and B to label of j</li>
                            <li> If B[j].number >= B[i].number, update the elements labeled by j in A and B to label of i</li>
                        </ul>
                    </li>
                </ol>
            </li>
            <li >Overtime of O(m log n)<br>
                <span style="font-size: 11pt">- m: number of edges<br> - n: number of vertices</span>
            </li>
        </ul>
    </li>
</ol>
<br>




