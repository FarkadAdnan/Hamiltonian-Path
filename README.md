# Hamiltonian-Path
Finding the Euler path, Euler circle, Hamiltonian path, and Hamiltonian cycle in a Graph



- https://linktr.ee/farkadadnan
-  By:Farkad Adnan فرقد عدنان - 
 - E-mail: farkad.hpfa95@gmail.com 
- inst : farkadadnan 
- #farkadadnan , #farkad_adnan , فرقد عدنان# 
* facebook : https://www.facebook.com/profile.php?id=100002145048612
* instagram:  https://www.instagram.com/farkadadnan/
* linkedin : https://www.linkedin.com/in/farkad-adnan-499972121/
 <p>
 <a href='https://mobile.twitter.com/farkadadnan'>
        <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/farkadadnan?label=%40farkadadnan&style=social" alt='Twitter' align="center"/>
    </a>
</p>

# ABSTRACT

This project aims to find the Euler path, Euler circle, Hamiltonian path and Hamiltonian cycle in a given graph. We have used the various features that are available in C++ and from now on we have found the things needed in a particular graph. Data structure concepts such as linked lists, two-dimensional matrices, Euler path, Euler circle, Hamiltonian path and Hamiltonian cycle are used to the extent possible.

# INTRODUCTION
- The program aims to obtain Euler’s Path, Euler’s Circuit, Hamiltonian Path and Hamiltonian Cycle.
- An Euler path is a path that crosses every edge exactly once without repeating, if it ends at the initial vertex then it is a Euler cycle. A Hamiltonian path passes through each vertex (note not each edge), exactly once, if it ends at the initial vertex then it is a Hamiltonian cycle. In a Euler path you might pass through a vertex more than once. In a Hamiltonian path you may not pass through all edges.
![CaptureD](https://user-images.githubusercontent.com/35774039/184636665-6715042b-b420-49e7-878d-8c66576ed9a1.PNG)

- A Hamiltonian cycle is a cycle that contains every vertex of the graph hence you may not use all the edges of the graph.
- Euler path is a graph using every edge(NOTE) of the graph exactly once. 
- Euler circuit is a euler path that returns to it starting point after covering all edges

# PROBLEM DEFINITION
- Hamiltonian Paths and Circuits 
- Consider visiting each of the vertices in the below given graphs just once. When we do this we leave the world of Euler and enter the world of Hamilton. Sir William Hamilton actually. He was an Irish mathematician, physicist and astronomer. Named after Sir Hamilton, we now look at Hamiltonian paths and Hamiltonian circuits. 
- A Hamiltonian circuit is a circuit that visits each of the vertices once and only once and ends on the same vertex as it began. For example, in this network the Hamiltonian circuit is marked in red. As it is a circuit, we cannot have repeated edges. We do not need to use all the edges, just visit each vertex once.

![CaptureD](https://user-images.githubusercontent.com/35774039/184637090-b8a761a7-9cfe-46ba-8b78-19f7673b4af4.PNG)

- Other Hamiltonian circuits here include ABDCA,ABDCA, DBACD,DBACD and many others. If a graph has a Hamiltonian circuit then it automatically has a Hamiltonian path. (By just dropping off the last vertex in the circuit we create a path, for example, ABDC and DBAC from above)
- A Hamiltonian path is a path that visits each of the vertices once and only once but can begin and end on different vertices. For example, the Hamiltonian path in the network here could be $ABCDE$ABCDE. In a Hamiltonian path we do not need to use all the edges, we just have to visit all the vertices once.

![CaptureD](https://user-images.githubusercontent.com/35774039/184637507-b0e68962-f36d-491b-a659-37235abe5ba2.PNG)
- Unlike with the Euler paths and Euler circuits, there is no single rule or theorem to help us identify if a Hamiltonian path or Hamiltonian circuit exists. The only thing we can do is look for them.
![CaptureD](https://user-images.githubusercontent.com/35774039/184637625-473db616-32ed-4efb-8837-175dde1a0f4d.PNG)
- Remember, the Hamiltonian path is a path where we visit each of the vertices only once. There are many Hamiltonian Paths here

* [  `  ABCDABCD, ABDCABDC, ADCBADCB, ADBCADBC, ACBDACBD, ACDBACDB, BACDBACD, BADCBADC, BCDABCDA, BCADBCAD, BDACBDAC, BDCABDCA, CABDCABD, CADBCADB, CBDACBDA, CBADCBAD, CDBACDBA, CDABCDAB, DABCDABC, DACBDACB, DBACDBAC, DBCADBCA, DCABDCAB and DCBADCBA. In fact, because each vertex here is connected to every other, then this list is actually all combinations of the four vertices A, B, C and D.` ] 

- The Hamiltonian circuit is a circuit where we visit each of the vertices once, but return to the beginning node. All the above paths can, in this case, be turned into a circuit by returning to the original node.


- If we start at a vertex and trace along edges to get to other vertices, we create a walk through the graph. More precisely, a walk in a graph is a sequence of vertices such that every vertex in the sequence is adjacent to the vertices before and after it in the sequence. If the walk travels along every edge exactly once, then the walk is called an Euler path (or Euler walk). If, in addition, the starting and ending vertices are the same (so you trace along every edge exactly once and end up where you started), then the walk is called an Euler circuit (or Euler tour). Of course if a graph is not connected, there is no hope of finding such a path or circuit. For the rest of this section, assume all the graphs discussed are connected.


# APPLICATIONS
1.  The Seven bridges of Königsberg
2.  The travelling salesman problem (TSP)


# ALGORITHM
For example, a Hamiltonian Cycle in the following graph is {0, 1, 2, 4, 3, 0}. There are more Hamiltonian Cycles in the graph like {0, 3, 4, 2, 1, 0}
```
(0)--(1)--(2)
| / \ | 
| / \ |
| / \ |
(3)-------(4)
```
And the following graph doesn’t contain any Hamiltonian Cycle.
```
(0)--(1)--(2) 
| / \ |
| / \ |
| / \ | 
(3) (4)
```
Following is Fleury’s Algorithm for printing Eulerian trail or cycle 
1. Make sure the graph has either 0 or 2 odd vertices.
2. If there are 0 odd vertices, start anywhere. If there are 2 odd vertices, start at one of them. 
3. Follow edges one at a time. If you have a choice between a bridge and a non-bridge, always choose the non-bridge. 
4. Stop when you run out of edges. The idea is, “don’t burn bridges“ so that we can come back to a vertex and traverse remaining edges. For example let us consider the following graph.
![CaptureD](https://user-images.githubusercontent.com/35774039/184641774-f01e0ddf-aecf-4005-9931-c8c703429238.PNG)
There are two vertices with odd degree, ‘2’ and ‘3’, we can start path from any of them. Let us start tour from vertex ‘2’.
![Euler2](https://user-images.githubusercontent.com/35774039/184641796-0ec632dd-641c-4bd9-abad-793cc684fbfa.png)
There are three edges going out from vertex ‘2’, which one to pick? We don’t pick the edge ‘2-3’ because that is a bridge (we won’t be able to come back to ‘3’). We can pick any of the remaining two edge. Let us say we pick ‘2-0’. We remove this edge and move to vertex ‘0’.
![Euler2](https://user-images.githubusercontent.com/35774039/184641955-05f1ea32-7287-4334-bd55-2c293ccffb6e.png)
There is only one edge from vertex ‘0’, so we pick it, remove it and move to vertex ‘1’. Euler tour becomes ‘2-0 0-1’.
![CaptureD](https://user-images.githubusercontent.com/35774039/184641999-2c7f7b41-d62b-4bd2-882e-2f7bd04453b2.PNG)
There is only one edge from vertex ‘1’, so we pick it, remove it and move to vertex ‘2’. Euler tour becomes ‘2-0 0-1 1-2’
![CaptureD](https://user-images.githubusercontent.com/35774039/184642119-23981380-32a8-4096-b0a7-63ceb504daa7.PNG)
Again there is only one edge from vertex 2, so we pick it, remove it and move to vertex 3. Euler tour becomes ‘2-0 0-1 1-2 2-3’


![CaptureD](https://user-images.githubusercontent.com/35774039/184642306-5c787a65-c624-40a9-aaad-f4ca04e3e9e8.PNG)

There are no more edges left, so we stop here. Final tour is ‘2-0 0-1 1-2 2-3’.

# Results
![2jVyFG5](https://user-images.githubusercontent.com/35774039/184642710-17b9810e-4d84-4411-a186-3f1a669c491e.png)


# REFERENCES:
- Ralph P. Grimaldi. (2011). “Discrete and combinatorial mathematics – 5th edition”, Pearson Education (2011) 
- Kenneth H. Rosen. (1999). “Discrete Mathematics and Its Applications”, McGraw Hill Education; 4th Revised edition (1 January 1999)
- Jean-Paul Tremblay, R. Manohar. (2017). “DISCRETE MATHEMATICAL STRUCTURES WITH APPLICATIONS TO COMPUTER SCIENCE”. McGraw Hill Education; 1 edition (1 July 2017) 
- V.K. Balakrishnan. (2000). “Introductory Discrete Mathematics (Dover Books on Computer Science)”. Dover Publications Inc.; New edition edition (1 February 2000) 
- László Lovász, Jozsef Pelikan, Katalin Vesztergombi. (2003). “Discrete Mathematics: Elementary and Beyond (Undergraduate Texts in Mathematics)”. Springer; 2003 edition (January 27, 2003) C.L. Liu. (2012). “Elements of Discrete Mathematics 4th Edition (English, Paperback, C. L. Liu)”. McGraw Hill Education 
- https://en.wikipedia.org/wiki/Discrete_mathematics


