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
