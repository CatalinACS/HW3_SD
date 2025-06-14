# Graph Analysis Project

## Overview

This project implements a graph-based system for analyzing actor relationships in movies. The system processes input data to find connected components, calculate degrees of kinship between actors, and identify critical edges in the graph structure.

**Development Time:** 2 weeks and 2 days

## Features

1. **Connected Component Analysis**: Identifies the largest connected component and stores it in a binary search tree
2. **Degree of Kinship**: Calculates minimum distance between actors using Breadth-First Search (BFS)
3. **Critical Edge Detection**: Implements Tarjan's algorithm to find critical connections

## Implementation Timeline

### Week 1: Foundation and Core Structure
- Implemented basic data structures and file processing functions
- Used `fscanf` with loop iteration for input file parsing
- **Requirement 1 Completion:**
  - Found connected component with maximum nodes
  - Stored component in a binary search tree
  - Implemented in-order traversal for ascending order output
- **Debugging Phase:** Resolved multiple Valgrind errors in the Productions function (2-3 days)

### Week 2: Advanced Features and Optimization
- **Requirement 2 Implementation:** Added `Degree` function for kinship calculation
- **Major Debugging Session:** 
  - Addressed SIGSEGV errors using GDB
  - Extensive Valgrind error resolution (2-3 days)
- **BFS Implementation:** 
  - Calculated the minimum distance between nodes
  - Added validation functions for actor presence in the tree
- **Memory Management:** Implemented proper memory deallocation

### Final Stage: Critical Edge Analysis
- **Requirement 3 Completion:** Implemented in 2 days
- **Tarjan's Algorithm Research and Implementation**
- **Complex Condition Checking:** 
  - Implemented 14 validation conditions in `CriticalEdges` function
  - Added letter-based relationship verification between actor names

## Data Structures

### Actor Representation
```
actor->name: Actor's name (string)
actor->code: Unique identifier to prevent duplicates
```

### Tree Structure
- Binary search tree with left/right ordering
- Uses `Compare_Names` function for proper alphabetical ordering
- Duplicate prevention built-in

### Graph Structure
- **Object**: Generic storage for node numbers or actor names
- **Number_of_nodes**: Total node count
- **Adjency_List**: Vector of adjacency lists for each node
- **Next**: Pointer for linked list traversal
- **Actor_Compare**: Function pointer for actor comparison

### Data Access Example
```c
(char *)Graph->Adjency_List[1]->head->Object
```
Retrieves the first actor's name in the graph.

## Key Algorithms

### Breadth-First Search (BFS)
- Used for calculating the degree of kinship
- Represents the minimum distance between any two actors
- Validates actor presence before calculation

### Tarjan's Algorithm
- Implemented for critical edge detection
- Complex condition validation system (14 conditions)
- Analyzes character relationships in actor names

## File Structure

### Main Components
- **Graph initialization and construction**
- **Binary tree management**
- **File I/O operations**
- **Memory management functions**

### Key Variables
- `Name_Movie`: Movie name storage
- `Names_Actors`: Actor name collection
- `Name_Actor1`, `Name_Actor2`: Individual actor identifiers
- Used for both tree/graph construction and memory cleanup

## Output Format

- **In-order traversal** for sorted actor output
- **Newline separation** for proper formatting
- **Binary tree structure** maintains alphabetical ordering

## Development Challenges

1. **Memory Management**: Extensive Valgrind error resolution
2. **Segmentation Faults**: Required GDB debugging sessions
3. **Algorithm Complexity**: Tarjan's algorithm implementation
4. **Data Structure Integration**: Binary tree and graph coordination

## Technical Notes

- No duplicate actors in final tree structure
- Proper memory deallocation at function completion
- Robust error handling throughout implementation
- Scalable design for large datasets

## Conclusion

This project successfully demonstrates advanced graph algorithms, efficient data structure management, and complex debugging techniques. The implementation provides a solid foundation for actor relationship analysis in film databases.
