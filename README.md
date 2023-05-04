Download Link: https://assignmentchef.com/product/solved-cse-6140-assignment-1
<br>



Please upload:

<ul>

 <li>a PDF cover letter indicating with whom you worked (if applicable), the sources you used, and if you wish, your impressions about the assignment (what was fun, what was difficult, why…);</li>

 <li>a PDF with your solutions of Problems 1, 2 and 3;</li>

 <li>a PDF of your report for Problem 4;</li>

 <li>a single zip file of your code, README, results for Problem 4.</li>

</ul>

Each file name should start by &lt;GTusername&gt;_HW1.

Please type your answers in L<sup>A</sup>TEX. You may handwrite them if you wish, but if we cannot read your handwriting, you will not receive points for your answer.

Note that MSTs (Problem 4) will be discussed in class on Sept. 5 (see course schedule on T-Square).

<h1>1           Algorithm design and complexity</h1>

The problem consists of finding the lowest floor of a building from which a box would break when dropping it. The building has <em>n </em>floors, numbered from 1 to <em>n</em>, and we have <em>k </em>boxes. There is only one way to know whether dropping a box from a given floor will break it or not. Go to that floor and throw a box from the window of the building. If the box does not break, it can be collected at the bottom of the building and reused.

The goal is to design an algorithm that returns the index of the lowest floor from which dropping a box will break it. The algorithm returns <em>n </em>+ 1 if a box does not break when thrown from the <em>n</em>-th floor. The cost of the algorithm, to be kept minimal, is expressed as the number of boxes that are thrown (note that re-use is allowed).

<ol>

 <li>For <em>k </em>≥dlog(<em>n</em>)e, design an algorithm with <em>O</em>(log(<em>n</em>)) boxes thrown.</li>

 <li>For <em>k &lt; </em>dlog(<em>n</em>)e, design an algorithm with boxes thrown.</li>

</ol>

√

<ol start="3">

 <li>For <em>k </em>= 2, design an algorithm with <em>O</em>( <em>n</em>) boxes thrown.</li>

</ol>

<h1>2           Greedy 1</h1>

A 30 foot long water pipe in Bob’s garden has sprung leaks at multiple spots along its seam. As useful as it might be as an irrigation tool, Bob wants to plug the leaks with thin strips of sealant. Each such strip is 9 inches in length and shockingly expensive, so laying down strip after strip in succession along the seam is not a smart idea; and Bob is most definitely a smart man.

How can Bob employ the most efficient greedy algorithm, such that all <em>n </em>leaks are plugged with the minimum number of strips? Assume each leak to be tiny in comparison to the sealing strip length. Also state the time complexity of the algorithm and prove its correctness using the concepts of Greedy Choice and Optimal Substructure Properties.

<h1>3           Greedy 2</h1>

You are on a hike along the Appalachian Trail when you happen upon an abandoned mine. Against your better judgement, you venture inside and find a large deposit of various precious minerals. Luckily, you have a bag and a pickaxe with you, but you can’t carry everything. Therefore, you must figure out how much of each mineral to take to maximize the value of your bag.

Formally: Given a bag with weight limit <em>L</em>, and a list of <em>n </em>minerals, where mineral <em>i </em>has value <em>v<sub>i </sub></em>and weight <em>w<sub>i</sub></em>, design a greedy algorithm to maximize the value of items you pack in your bag. (Note: <em>v<sub>i </sub></em>is the value of the entierty of item <em>i</em>, so if you decide you only want to take half of item <em>i </em>you only get value ). Prove your algorithm gives the optimal result using an <strong>exchange argument</strong>.

<h1>4           Programming Assignment</h1>

You are to implement <em>either </em>Prim’s or Kruskal’s algorithm for finding a Minimum Spanning Tree (MST) of an undirected graph, and evaluate its running time performance on a set of graph instances. The 13 input graphs are RMAT graphs [<strong>?</strong>], which are synthetic graphs with power-law degree distributions and small-world characteristics.

<h2>4.1         Static Computation</h2>

The first part of the assignment entails coding either Prim’s or Kruskal’s algorithm to find the cost of an MST given a graph file. You may use the programming language of your choice (either C++, Java, or Python). We provide a wrapper function in all three languages to help you get started with the assignment. You may call your own functions inside the wrapper. We also have implemented a timer in the wrapper that records the running time of your algorithms. To implement these algorithms, you may make use of data structure implementations in the programming language of your choice; e.g. in python, the heapq library may be used for implementing priority queues and set operations may be used for implementing the union-find data structure. In Java, java.util.PriorityQueue may be used for implementing priority queues and java.util.Set may be used for set operations. Use of advanced data structures as opposed to trivial ones for implementation will carry bonus marks. The ‘graph file’ format is as follows:

Line 1: N E (N = number of vertices, E = number of edges)

Every subsequent line contains three integers: u v weight (u = source of edge, v = destination of edge, weight = weight of edge between u and v)

The MST calculation is to be implemented in the computeMST function, as indicated in the wrapper code.

<h2>4.2         Dynamic Recomputation</h2>

The next part of the assignment requires you to update the cost of the MST given new edges to be added to the graph. You are provided with a ‘changes file’ and the format is as follows:

Line 1: N (N = number of changes/edges to be added)

Every subsequent line contains three integers: u v weight (u = source of new edge to be added, v = destination of edge, weight = weight of edge between u and v)

You are to implement the function recomputeMST as indicated in the wrapper code that computes the new MST given the new edge to be added into the graph. You are responsible for maintaining the old MST before recomputing.

Note: it is very easy to complete this part of the assignment by simply adding the new edge and calling your old computeMST function from part 1 (Subsection <strong>??</strong>). The objective is to minimize computation and efficiently recompute the cost of the MST.

<h2>4.3         Execution</h2>

The wrapper code is set up to require three command line arguments: <em>&lt;</em>executable<em>&gt; &lt;</em>graph file.gr<em>&gt; &lt;</em>change file.extra<em>&gt; &lt;</em>output file<em>&gt;</em>. The <em>&lt;</em>graph file<em>&gt; </em>is the one described in Subsection <strong>?? </strong>and the <em>&lt;</em>change file<em>&gt; </em>is the one described in Subsection <strong>??</strong>.

<h2>4.4         Experiments</h2>

You are required to run your code for all 13 input graphs provided. The wrapper functions we provide in C++, Java, and Python describe the following procedure. For each graph:

<ul>

 <li>parse the edges (parseEdges): <strong>to be implemented</strong></li>

 <li>compute the MST using either Prim’s or Kruskal’s algorithm (computeMST): <strong>to be implemented</strong></li>

 <li>write the cost of the initial MST and time taken to compute it to the output file: <strong>provided in wrapper code</strong></li>

 <li>For each line in the <em>&lt;</em>change file<em>&gt;</em>,

  <ul>

   <li>Parse the new edge to be added: <strong>provided in wrapper code</strong></li>

   <li>Call the function recomputeMST: <strong>to be implemented</strong></li>

   <li>Write to the output file the cost of the new MST and the time taken to compute it: <strong>provided in wrapper code</strong></li>

  </ul></li>

</ul>

Name the output files as such: <em>&lt;</em>graph file<em>&gt; </em>output.txt and place them in the folder <em>results</em>.

<h2>4.5         Report</h2>

Write a brief report wherein you:

<ol>

 <li>List which data structures you have used for your choice of algorithm (Prim’s/Kruskal’s). Explain the reasoning behind your choice and how that has influenced the running time of your algorithms, and the theoretical complexity (i.e., specify the big-Oh for your implementation of each of the two algorithms – computeMST and recomputeMST).</li>

 <li>Plots: Plot the running time as the number of edges in the graph increases (across the 13 graphs you were given) for both the static and dynamic calculations, i.e. one plot showing on the x-axis the number of edges the graph has and the y-axis the time for the static MST calculation, and another plot where the y-xis the time needed to insert 100 edges (as given the changes files) using your recomputeMST code. Discuss the results you observe. How does the empirical scaling you observe match your big-Oh analysis? How does the behavior vary with the dynamic recomputation?</li>

</ol>

<h2>4.6         Deliverables</h2>

<ul>

 <li>code for initial, static MST implementation</li>

 <li>code for dynamic MST recomputation</li>

 <li>README, explaining how to run your code</li>

 <li>Report (Subsection <strong>??</strong>)</li>

 <li>output files (13) within the <em>results </em>folder- one for each graph</li>

</ul>


