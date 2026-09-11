# ☕ Java Data Structures & Algorithms (DSA)

> High-yield Java DSA concepts, Collections framework, tree traversals, and dynamic programming.


---

### 📘 [Entry #3/5] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 03:43 AM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #5/5] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 03:43 AM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #5/31] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 7, 2026, 10:15 PM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #17/31] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #18/31] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #21/31] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #25/31] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #26/31] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #27/31] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 7, 2026, 10:16 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #1/35] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 10:26 AM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #6/35] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 10:26 AM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #14/35] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 10:27 AM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #24/35] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #28/35] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 10:28 AM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #1/31] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 09:12 PM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #12/31] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 09:12 PM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #19/31] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 09:13 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #23/31] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 09:13 PM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #24/31] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 8, 2026, 09:13 PM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #3/31] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 9, 2026, 10:36 AM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #14/31] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 9, 2026, 10:37 AM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #19/31] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #20/31] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #23/31] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #27/31] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #30/31] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 9, 2026, 10:38 AM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #8/30] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 10, 2026, 07:33 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #15/30] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 10, 2026, 07:34 PM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #16/30] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 10, 2026, 07:34 PM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #28/30] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 10, 2026, 07:35 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #30/30] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 10, 2026, 07:35 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #2/27] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 11, 2026, 07:57 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #4/31] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 11, 2026, 07:57 PM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #4/27] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 11, 2026, 07:57 PM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #14/27] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 11, 2026, 07:58 PM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.

---

### 📘 [Entry #3/30] Java Collections Framework: ArrayList vs LinkedList vs HashMap
> **Track:** `JAVA-DSA` | **Updated:** Sep 11, 2026, 08:59 PM

#### 💡 Overview
Choosing the right Java Collection (`ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `PriorityQueue`) with Big-O trade-offs.

#### 💻 Code & Implementation
```java
import java.util.*;

public class CollectionsOverview {
    public static void main(String[] args) {
        // 1. ArrayList: Fast random access O(1), Slow middle insertion O(N)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        System.out.println("ArrayList get(0): " + list.get(0));

        // 2. HashMap: Fast O(1) average lookup, insert, and delete
        Map<String, Integer> studentGrades = new HashMap<>();
        studentGrades.put("Alice", 95);
        studentGrades.put("Bob", 88);
        System.out.println("Alice's grade: " + studentGrades.get("Alice"));

        // 3. PriorityQueue (Min-Heap): O(log N) insertion and removal of minimum element
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.offer(40);
        minHeap.offer(10);
        minHeap.offer(25);
        System.out.println("Smallest element (peek): " + minHeap.poll()); // 10
    }
}
```

#### 🎯 Key Concepts & Takeaways
- `ArrayList` uses a dynamic array internally; contiguous memory provides high cache locality.
- `HashMap` uses hashing and bucket arrays with linked-list / red-black tree collision resolution.
- `PriorityQueue` implements a binary heap, essential for Dijkstra's and Top K problems.

---

### 📘 [Entry #4/30] Graph Traversal Algorithms: BFS & DFS in Java
> **Track:** `JAVA-DSA` | **Updated:** Sep 11, 2026, 08:59 PM

#### 💡 Overview
Building adjacency lists, cycle prevention with visited sets, and shortest path traversal.

#### 💻 Code & Implementation
```java
import java.util.*;

public class GraphTraversal {
    private int vertices;
    private List<List<Integer>> adj;

    public GraphTraversal(int v) {
        this.vertices = v;
        adj = new ArrayList<>(v);
        for (int i = 0; i < v; i++) adj.add(new ArrayList<>());
    }

    public void addEdge(int u, int v) {
        adj.get(u).add(v);
        adj.get(v).add(u); // Undirected graph
    }

    // Breadth-First Search (Shortest path in unweighted graph)
    public void bfs(int startNode) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[startNode] = true;
        queue.offer(startNode);

        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int neighbor : adj.get(node)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    queue.offer(neighbor);
                }
            }
        }
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Adjacency list uses O(V + E) memory space, making it efficient for sparse graphs.
- BFS guarantees the shortest path in unweighted graphs.
- Always track visited nodes with a `boolean[]` or `HashSet` to prevent infinite loops from cycles.

---

### 📘 [Entry #16/30] Binary Tree Traversals in Java: Inorder, Preorder, Postorder & Level-Order
> **Track:** `JAVA-DSA` | **Updated:** Sep 11, 2026, 09:00 PM

#### 💡 Overview
Tree traversal algorithms: Depth-First Search (DFS) and Breadth-First Search (BFS level-order).

#### 💻 Code & Implementation
```java
import java.util.*;

class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int val) { this.val = val; }
}

public class TreeTraversals {
    // 1. Inorder: Left -> Root -> Right (Yields sorted order in BST)
    public static void inorder(TreeNode root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.val + " ");
        inorder(root.right);
    }

    // 2. Level-Order Traversal (BFS using Queue)
    public static List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result = new ArrayList<>();
        if (root == null) return result;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);

        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Integer> currentLevel = new ArrayList<>();

            for (int i = 0; i < levelSize; i++) {
                TreeNode current = queue.poll();
                currentLevel.add(current.val);

                if (current.left != null) queue.offer(current.left);
                if (current.right != null) queue.offer(current.right);
            }
            result.add(currentLevel);
        }
        return result;
    }
}
```

#### 🎯 Key Concepts & Takeaways
- Inorder traversal of a Binary Search Tree (BST) visits nodes in ascending sorted order.
- Level-Order traversal uses a FIFO Queue to visit nodes level by level.
- Time Complexity: O(N) where N is total nodes; Space Complexity: O(H) recursion stack for DFS, O(W) queue width for BFS.
