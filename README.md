Download Link: https://assignmentchef.com/product/solved-cs2040s-tutorial-4
<br>
<h2>Problem 1.           AVL Trees</h2>

<strong>Problem 1.a.           </strong>Trace the deletion of the node with the key 70.

<strong>Problem 1.b.    </strong>Identify the roots of all maximally imbalanced AVL subtrees in the original tree. A maximal imbalanced tree is one with the minimum possible number of nodes given its height <em>h</em>.

<strong>Problem 1.c. </strong>During lectures, we’ve learnt that we need to store and maintain height information for each AVL tree node to determine if there is a need to rebalance the AVL tree during insertion and deletion. However, if we store height as a int, each tree node now requires 32 extra bits. Can you think of a way to reduce the extra space required for each node to 2 bits instead?

<h2>Problem 2.           AVL vs Trie</h2>

<strong>Problem 2.a.            </strong>Transform the given AVL tree with string values into a trie.

<strong>Problem 2.b.            </strong>Insert “acac” to the trie from the previous question.

<strong>Problem 2.c.            </strong>Discuss the trade-offs of using AVL and Trie to store strings.

<h1>1         Problems</h1>

<h2>Problem 3.          kd-Trees</h2>

A kd-tree is another simple way to store geometric data in a tree. Let’s think about 2dimensional data points, i.e., points (<em>x,y</em>) in the plane. The basic idea behind a kd-tree is that each node represents a rectangle of the plane. A node has two children which divide the rectangle into two pieces, either vertically or horizontally.

For example, some node <em>v </em>in the tree may split the space vertically around the line <em>x </em>= 10: all the points with <em>x</em>-coordinates ≤ 10 go to the left child, and all the points with <em>x</em>-coordinates <em>&gt; </em>10 go to the right child.

Typically, a kd-tree will alternate splitting the space horizontally and vertically. For example, nodes at even levels split the space vertically and nodes at odd levels split the space horizontally. This helps to ensure that the data is well divided, no matter which dimension is more important.

All the points are stored at the leaves. When you have a region with only one node, instead of dividing further, simply create a leaf.

Here is an example of a kd-tree that contains 10 points:

<strong>Figure 1: </strong>On the left: the points in the input. On the right: how the points are stored in the kd-tree <strong>Problem 3.a. </strong>How do you search for a point in a kd-tree? What is the running time?

<strong>Problem 3.b. </strong>You are given an (unordered) array of points. What would be a good way to build a kd-tree? Think about what would keep the tree nicely balanced. What is the running time of the construction algorithm?

<strong>Problem 3.c.    </strong>How would you find the element with the minimum (or maximum) x-coordinate in a kd-tree? How expensive can it be, if the tree is perfectly balanced?

<h2>Problem 4.            Tries(a.k.a Radix Trees)</h2>

Coming up with a good name for your baby is hard. You don’t want it to be too popular. You don’t want it to be too rare. You don’t want it to be too old. You don’t want it to be too weird.<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>

Imagine you want to build a data structure to help answer these types of questions. Your data structure should support the following operations:

<ul>

 <li>insert(name, gender, count): adds a name of a given gender, with a count of how many babies have that name.</li>

 <li>countName(name, gender): returns the number of babies with that name and gender.</li>

 <li>countPrefix(prefix, gender): returns the number of babies with that prefix of their name and gender.</li>

 <li>countBetween(begin, end, gender): returns the number of babies with names that are lexicographically after begin and before end that have the proper gender.</li>

</ul>

In queries, the gender can be either boy, girl, or either. Ideally, the time for countPrefix should not depend on the number of names that have that prefix, but instead run in time only dependent on the length of the longest name.

<h2>Problem 5.             (Challenge) Finger Searching</h2>

It seems like it should be easier to find an element that is near an element you’ve already seen, right? That’s what a <strong>finger search </strong>is for. Assume you have a tree of some sort. A finger search is the following query: given the node in the data structure that stores the element <em>x</em>, and given another element <em>y</em>, find the node in the data structure that stores <em>y</em>. Ideally, the running time should depend distance <em>d</em>, which refers to the difference in ranks between <em>x </em>and <em>y</em>, for example, <em>O</em>(log(<em>d</em>)) would be optimal.

Note: this problem is harder compared to the rest of the tutorial.

<strong>Problem 5.a. </strong>Say that we had to implement finger search on a vanilla AVL tree, wtihout any further modifications, what would a very straightforward solution be? Give an example where you cannot do better than just directly searching for <em>y</em>, given the node <em>x</em>.

<strong>Problem 5.b. </strong>What if you are allowed to use other kinds of data structures to implement efficient finger search? For example, a tree with all keys at the leaf level. What sort of running time do you get?

<a href="#_ftnref1" name="_ftn1">[1]</a> The website <a href="https://www.babynamewizard.com/voyager">https://www.babynamewizard.com/voyager</a> let’s you explore the history of baby name popularity!