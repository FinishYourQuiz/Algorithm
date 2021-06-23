<p style="text-align: center; font-weight: bold; font-size: 20pt"> Greedy algorithm</p>

### > **interval Scheduling**
----

### > **An Exchange Argument**

----

### > **Applied to Graph**
<br>

### **1. Some definitions and basic algorithm**
<br>

#### **Connectivity:** 
#### *Connected*: For an undirected graph, every pair of nodes u and v, there is a path from u to v. 
#### *Strongly connected*: For a directed graph, for two every nodes u and v, there is a path from u to v and a path from v to u.
<br>

#### **Trees:** An undirected graph is a tree if it is connected and does not contain a circle.
<br>

#### **Directed Acyclic Graph(DAG):** A directed graph has no cycle.
<br>

#### **Graph Traversal:**
#### *Breath First Search*(BFS) : Explore outwards from s in all possible directions, addig nodes one "layer" at a time.
#### *Depth First Search*(BFS) : Explore outwards from s by going as deeply as possible and only treating when necessary.
<br>

### **2. Topological**
#### - **Topological Ordering:** For a directed graph G, we say that a topological ordering of G is an ordering of its nodes as v1, v2, v3, ..., vn so that for every edge (vi, vj), we have i<j.

<ol type='a' style="font-size: 12pt">
    <li>Properties of Topological
        <ul style="font-size: 10pt; font-weight: bold">
        <li>In every DAG, there is a node v with no incoming edge.</li>
        <li>If G has a topological ordering, then G is a DAG</li>
        <li>If G is a DAG, then G has a topological ordering.</li>
        </ul>
    </li>
    <li>Compute a Topological Ordering
        <br>
        <code style="font-size: 14px">
            Find a node v with no incoming edge and order it first<br>
            Delete v from G<br>
            Recursively compute a topological ordering of G-{v} and append this order after v
        </code>
    </li>

</ol>
<br>

### **2. Shortest Path Algorithm**





