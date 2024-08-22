from collections import deque

# Definition for a binary tree node.
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def bfs(root):
    if not root:
        return []

    queue = deque([root])
    result = []

    while queue:
        node = queue.popleft()
        result.append(node.val)
        if node.left:
            queue.append(node.left)
        if node.right:
            queue.append(node.right)

    return result




#  EXAMPLE

The key to understanding how this works lies in how the nodes are enqueued and dequeued, maintaining the order of traversal. Let's break it down step by step:

1. **Initialization**:
   - `if not root: return []`: If the root is `None`, the function returns an empty list because there's no tree to traverse.
   - `queue = deque([root])`: Initializes a queue with the root node. The `deque` is used because it allows efficient appending and popping from both ends.
   - `result = []`: Initializes an empty list to store the values of the nodes as they are visited.

2. **While Loop**:
   - `while queue:`: The loop continues as long as there are nodes in the queue.

3. **Processing Nodes**:
   - `node = queue.popleft()`: Dequeues the node at the front of the queue.
   - `result.append(node.val)`: Appends the value of the dequeued node to the `result` list.

4. **Enqueue Child Nodes**:
   - `if node.left: queue.append(node.left)`: If the dequeued node has a left child, it is enqueued.
   - `if node.right: queue.append(node.right)`: If the dequeued node has a right child, it is enqueued.

### Why It Works Level by Level

The key to the level-by-level traversal is the order in which nodes are enqueued and dequeued:

- **Enqueueing Order**: When a node is processed, its children are enqueued from left to right. This ensures that all nodes at the current level are enqueued before any nodes at the next level.
- **Dequeueing Order**: Nodes are dequeued in the order they were enqueued. This means nodes at the current level are processed before any nodes at the next level.

### Example

Consider the following binary tree:

```
     1
   /   \
  2     3
 / \   / \
4   5 6   7
```

**Initialization**:
- Queue: [1]
- Result: []

**Iteration 1**:
- Dequeue: 1
- Enqueue: 2, 3
- Queue: [2, 3]
- Result: [1]

**Iteration 2**:
- Dequeue: 2
- Enqueue: 4, 5
- Queue: [3, 4, 5]
- Result: [1, 2]

**Iteration 3**:
- Dequeue: 3
- Enqueue: 6, 7
- Queue: [4, 5, 6, 7]
- Result: [1, 2, 3]

**Iteration 4**:
- Dequeue: 4
- Enqueue: (None)
- Queue: [5, 6, 7]
- Result: [1, 2, 3, 4]

**Iteration 5**:
- Dequeue: 5
- Enqueue: (None)
- Queue: [6, 7]
- Result: [1, 2, 3, 4, 5]

**Iteration 6**:
- Dequeue: 6
- Enqueue: (None)
- Queue: [7]
- Result: [1, 2, 3, 4, 5, 6]

**Iteration 7**:
- Dequeue: 7
- Enqueue: (None)
- Queue: []
- Result: [1, 2, 3, 4, 5, 6, 7]

The `queue` ensures that nodes are processed in the order they were added, and since child nodes are added from left to right, the traversal happens level by level.
