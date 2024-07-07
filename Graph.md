# Graph representations
You can be given a list of edges and you have to build your own graph from the edges so that you can perform a traversal on them. 
The common graph representations are:
 
Adjacency matrix
Adjacency list
Hash table of hash tables 

Note: Using a hash table of hash tables would be the simplest approach during algorithm interviews. 
It will be rare that you have to use an adjacency matrix or list for graph questions during interviews.

# Graph question pattern:

    1. In algorithm interviews, graphs are commonly given in the input as 2D matrices 
       where cells are the nodes and each cell can traverse to its adjacent cells (up/down/left/right)
    2. It is important that you be familiar with traversing a 2D matrix
    3. When traversing the matrix, always ensure that your current position is within the boundary of the matrix and has not been visited before.

# Time Complexity
  |V| is the no of vertices while |E| is the no of edges

Depth-first search	        O(|V| + |E|)
Breadth-first search	      O(|V| + |E|)
Topological sort	          O(|V| + |E|)

# Things to look out for during interviews

    1. A tree-like diagram could very well be a graph that allows for cycles and a naive recursive solution would not work. 
        In that case you will have to handle cycles and keep a set of visited nodes when traversing.
    2. Ensure you are correctly keeping track of visited nodes and not visiting each node more than once. Otherwise your code could end up in an infinite loop.

# Corner Cases

  1. Empty graph
  2. Graph with one or two nodes
  3. Disconnected graphs
  4. Graph with cycles


# Graph search algos
  1. COMMON: BFS, DFS,
  2. UNCOMMON: Topological Sort, Dijkstra's algorithm
  3. Almost never: Bellman-Ford algorithm, Floyd-Warshall algorithm, Prim's algorithm, Kruskal's algo (You interviewer doesn't know them either)



# DEPTH FIRST SEARCH TEMPLATE : STACK USED

    Depth-first search is a graph traversal algorithm which explores as far as possible along each branch before backtracking. 
    A stack is usually used to keep track of the nodes that are on the current search path.
    This can be done either by an implicit recursion stack, or an actual stack data structure

    TEMPLATE: doing depth-first searches on a matrix


    def dfs(matrix):
      if not matrix:
        return []


      rows,cols = len(matrix), len(matrix[0])

      visited = set()

      directions = ((0,1),(0,-1),(1,0), (-1,0))

      def traverse(i,j):
        if (i,j) in visited:
          return

        visited.add((i,j))

        #traverse neighbors
        for direction in directions:
          next_i, next_j = i + direction[0], j + direction[1]
          if 0 <= next_i < rows and 0 <= next_j < cols:
            #Add qs specific checks, where relevant
            traverse(next_i,next_j)

       for i in range(rows):
         for j in range(cols):
           traverse(i,j)

  # BREADTH FIRST SEARCH : QUEUE USED

        Breadth-first search is a graph traversal algorithm which starts at a node 
        and explores all nodes at the present depth, before moving on to the nodes at the next depth level.
        A queue is usually used to keep track of the nodes that were encountered but not yet explored.

         It is important to use double-ended queues and not arrays/Python lists as dequeuing for double-ended queues is O(1) but it's O(n) for arrays.

         TEMPLATE: doing breadth-first searches on a matrix'
         
         from collections import deque

         def bfs(matrix):
         if not matrix:
           return []

          rows,cols = len(matrix), len(matrix[0])
          visited = set()
          directions = ((0,1),(0,-1), (1,0),(-1,0))


          def traverse(i,j):
            queue = deque([i,j])
            while queue:
              curr_i,curr_j = queue.popleft()
              if (curr_i, curr_j) not in visited:
                visited.add((curr_i,curr_j))

                #Traverse neighbors
                for direction in directions:
                  next_i, next_j = curr_i +directions[0], curr_j + directions[1]
                  if 0 <= next_i <= rows and 0 <= next_j <= cols:
                    #Add in s related specific check where relevant
                    queue.append((next_i,next_j))

          for i in range(rows)
            for j in range(cols):
              traverse(i,j)

         


# TOPOLPGICAL SORTING

    A topological sort or topological ordering of a directed graph is a linear ordering of its vertices 
    such that for every directed edge uv from vertex u to vertex v, u comes before v in the ordering

    A topological sort is a graph traversal in which each node v is visited only after all its dependencies are visited.

    WHY USED:
        Topological sorting is most commonly used for scheduling a sequence of jobs or tasks which has dependencies on other jobs/tasks
        The jobs are represented by vertices, and there is an edge from x to y if job x must be completed before job y can be started.
        e.g taking courses in university where courses have pre-requisites.

        EXAMPLE CODE: Where the edges is an array of two-value tuples and the first value depends on the second value.
         form collections import deque
        def graph_topo_sort(num_nodes,edges):

          nodes, order, queue = {} , [], deque()

          for node_id in range(num_nodes):
            nodes[node_id] = { 'in' : 0, 'out' : set() }

          for node_id, pre_id i edges:
            nodes[node_id]['in'] += 1
            nodes[pre_id]['out'].add(node_id)
          for node_id in nodes.keys():
            if nodes[node_id]['in'] == 0:
              queue.append(node_id)

           while len(queue):
             node_id = queue.pop()
             for outgoing_id in nodes[node_id]['out']:
               nodes[outgoing_id]['in'] -= 1
               if nodes[outgoing_id]['in'] == 0:
                 queue.append(outgoing_id)
              order.append(node_id)
            return order if len(order) == num_nodes else None

        print(graph_topo_sort(4, [[0, 1], [0, 2], [2, 1], [3, 0]]))
        # [1, 2, 0, 3]
