### UNIVERSIDAD NACIONAL DE COSTA RICA, CAMPUS SARAPIQUÍ
#### EIF420O - Inteligencia Artifical
#### Ejercicio Asincrónico - Semana 8
#### Rutas Inteligentes desde CSV
###### Hecho por:
- Jamyr González García
- Kevin Venegas Bermúdez

## Summary
This Python program implements the A* pathfinding algorithm to determine the shortest route between two points in a graph constructed from CSV data.

## Requirements
This program uses some libraries and takes data from 2 .csv files.

### Dependencies
- Python 3.x
- Required packages:
  - csv
  - networkx
  - matplotlib
  - heapq 
  - math 

### Files
- `Nodes.csv` format:
```csv
Name,X,Y
A,1.5,2.0
B,3.0,4.0
```

- `Edges.csv` format:
```csv
Source,Destination,Weight
A,B,5.0
B,C,3.2
```

## Functionality Explanation

### 1. Data Loading
The program reads two CSV files:
- `Nodes.csv`: Contains point names with X,Y coordinates
- `Edges.csv`: Specifies connections between points with weights

Key features:
- Minimum requirements (15 nodes, 40 edges)
- Comprehensive error handling for:
  - Missing files
  - Permission issues
  - Data format errors

### 2. Graph Construction
The system builds a directed graph using:
- `networkx` for graph operations
- `matplotlib` for visualization

Visualization includes:
- Node positioning with spring layout
- Custom styling for nodes and edges
- Weight labels on connections

### 3. Pathfinding Implementation
The A* algorithm features:
- Two heuristic options:
  1. Euclidean distance (geometric straight-line)
  2. Step count (uniform cost per move)
- Priority queue for efficient node exploration
- Path reconstruction from goal to start

### 4. User Interaction
The program guides users through:
1. Available node display
2. Source and destination selection
3. Input validation
4. Clear results presentation

### 5. Results Comparison
For each heuristic, the program displays:
- The optimal path
- Total cost
- Number of nodes expanded
- Comparative analysis

## Execution Flow
1. Data loading and validation
2. Graph construction and visualization
3. User input collection
4. Path calculation using both heuristics
5. Results display and comparison

## Error Handling
The program handles this kind of errors:
- Missing or corrupt data files
- Invalid coordinate values
- Permission issues on files
- Nonexistent node selections

## Example Output
```
============================================================
========== WELCOME TO INTELLIGENT ROUTE FROM CSV ===========
============================================================

We're here to help you find the shortest path between two points.
To do this, we need you to specify your starting point and destination.

Available points are:
A, B, C, D, E

Choose source node: A
Choose destination node: E

============================================================
Great! 
We'll find the best route from:
A → E
============================================================

Results using Euclidean Heuristic:
Route: A → C → E
Total cost: 15.2
Expanded nodes: 4

Results using Step-Based Heuristic:
Route: A → B → E
Total cost: 18.0
Expanded nodes: 3

Comparison:
Euclidean: cost=15.2, expanded nodes=4
Step-Based: cost=18.0, expanded nodes=3
```