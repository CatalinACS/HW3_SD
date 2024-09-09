# HW3_SD

The task was completed in 2 weeks and 2 days. The implementation ideas came to me successively. In the first week, I implemented the necessary structures, processing functions, and writing functions. I used a 'for' loop and the `fscanf` function to obtain the data from the input file. Also in the first week, I solved requirement 1 of the task. Evidently, there were many errors reported by Valgrind within the 'Productions' function. I spent 2-3 days to resolve all the errors caused by that binary tree vector within the function. The requirement was simple, I had to find the connected component with the most nodes. I saved this component in a binary tree. The interesting part was that the ascending order was obtained by traversing the tree in-order.That's why I chose to use trees in the task. Evidently, another solution was to use the `qsort` function on a `char**` variable. I didn't opt for that.

In the second week, I completed requirement 2 using the `Degree` function. Here I encountered the most obstacles (SIGSEGV -> GDB). Another 2-3 days of this week were necessary for debugging, obviously. I used Valgrind and GDB. Valgrind reported the most errors. The degree of kinship represented the minimum distance from one node to another. I used breadth-first search (BFS) for this. I called other functions within the `Degree` function to obtain a valid result because I had to ensure that the respective actors are present in the tree. I freed the memory and returned the result at the end of the function.

The main idea of the program conceived in the first 2 weeks: Each actor has a name (`actor->name`) and an associated code (`actor->code`) to avoid adding the same actor to the tree. The actors read from the file are added either to the left or right part of the tree (to have the correct order). We have the following content: 10 Film1 3 Actor1->name Actor1 Push_BinaryTree / \ Correct order is obtained with the help of the `Compare_Names` function. Actor2 -> v v Actor3 Actor2->name Actor3->name Film2 ... There will also be no 'duplicates' in the tree (there will be no 2 nodes storing the same actor).

The meanings of the following fields: `Object` -> a generic object that stores the order number of a node or the name of an actor. `Number_of_nodes` -> the number of nodes. `Adjency_List` -> a vector of adjacency lists. `Next` -> move to another node. `Actor_Compare` -> a function that compares actors. Example: `(char *)Graph->Adjency_List[1]->head->Object` stores the name of the first actor in the graph. As I said, many errors in this part of the program. I finished the task after another 2 days. The experience gained in the second week saved me from other errors, obviously.

In these 2 days, I completed requirement 3. I searched for more information about the Tarjan algorithm. The implementation was complex, in the `CriticalEdges` function I checked all the conditions (1-14) to order the actors. All these conditions checked certain relationships between the letters that make up the actors' names. In the `main` function, I initialized the graph and the tree. Again, many problems with Valgrind in this part. The writing function was simple, I used in-order traversal and `'\n'` to have the correct format in the output file. I also used these variables (`char *Name_Movie, **Names_Actors, *Name_Actor1, *Name_Actor2` etc.) to build the tree and the graph. Moreover, they were also used for memory deallocation.

In conclusion, this task was not trivial either.
