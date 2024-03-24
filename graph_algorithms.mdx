
# Graph Algorithms

Graph algorithms are algorithms used to solve problems on graphs, which are data structures consisting of nodes (vertices) and edges that connect these nodes. Here are three important topics in graph algorithms:

## Graphs

A graph is a collection of nodes (vertices) and edges that connect pairs of nodes. Graphs can be directed (edges have a direction) or undirected (edges do not have a direction). They are used to model relationships between objects or entities.

```java
import java.util.*;

public class Graph {
    private int V;
    private LinkedList<Integer> adj[];

    public Graph(int v) {
        V = v;
        adj = new LinkedList[v];
        for (int i = 0; i < v; ++i)
            adj[i] = new LinkedList();
    }

    public void addEdge(int v, int w) {
        adj[v].add(w);
    }

    public void BFS(int s) {
        boolean visited[] = new boolean[V];
        LinkedList<Integer> queue = new LinkedList<Integer>();
        visited[s] = true;
        queue.add(s);
        while (queue.size() != 0) {
            s = queue.poll();
            System.out.print(s + " ");
            Iterator<Integer> i = adj[s].listIterator();
            while (i.hasNext()) {
                int n = i.next();
                if (!visited[n]) {
                    visited[n] = true;
                    queue.add(n);
                }
            }
        }
    }

    public static void main(String args[]) {
        Graph g = new Graph(4);
        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(2, 3);
        g.addEdge(3, 3);
        System.out.println("Breadth First Traversal starting from vertex 2:");
        g.BFS(2);
    }
}
```

## Traversing Graphs

Graph traversal refers to the process of visiting all the nodes of a graph in a systematic way. Breadth-first search (BFS) and depth-first search (DFS) are two common traversal algorithms.

```java
import java.util.*;

public class GraphTraversal {
    private int V;
    private LinkedList<Integer> adj[];

    public GraphTraversal(int v) {
        V = v;
        adj = new LinkedList[v];
        for (int i = 0; i < v; ++i)
            adj[i] = new LinkedList();
    }

    public void addEdge(int v, int w) {
        adj[v].add(w);
    }

    public void DFSUtil(int v, boolean visited[]) {
        visited[v] = true;
        System.out.print(v + " ");
        Iterator<Integer> i = adj[v].listIterator();
        while (i.hasNext()) {
            int n = i.next();
            if (!visited[n])
                DFSUtil(n, visited);
        }
    }

    public void DFS(int v) {
        boolean visited[] = new boolean[V];
        DFSUtil(v, visited);
    }

    public static void main(String args[]) {
        GraphTraversal g = new GraphTraversal(4);
        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(2, 3);
        g.addEdge(3, 3);
        System.out.println("Depth First Traversal starting from vertex 2:");
        g.DFS(2);
    }
}
```

## Calculating Shortest Paths

Finding the shortest path between two nodes in a graph is a common problem in graph theory. Dijkstra's algorithm and Bellman-Ford algorithm are two popular algorithms for calculating shortest paths.

```java
import java.util.*;

public class ShortestPath {
    private int dist[];

    public ShortestPath(int n) {
        dist = new int[n];
        Arrays.fill(dist, Integer.MAX_VALUE);
    }

    public void dijkstra(int graph[][], int src) {
        boolean visited[] = new boolean[graph.length];
        dist[src] = 0;
        for (int count = 0; count < graph.length - 1; count++) {
            int u = minDistance(dist, visited);
            visited[u] = true;
            for (int v = 0; v < graph.length; v++)
                if (!visited[v] && graph[u][v] != 0 &&
                        dist[u] != Integer.MAX_VALUE && dist[u] + graph[u][v] < dist[v])
                    dist[v] = dist[u] + graph[u][v];
        }
    }

    public int minDistance(int dist[], boolean visited[]) {
        int min = Integer.MAX_VALUE, min_index = -1;
        for (int v = 0; v < dist.length; v++)
            if (!visited[v] && dist[v] <= min) {
                min = dist[v];
                min_index = v;
            }
        return min_index;
    }

    public static void main(String args[]) {
        int graph[][] = new int[][]{{0, 4, 0, 0, 0, 0, 0, 8, 0},
                                    {4, 0, 8, 0, 0, 0, 0, 11, 0},
                                    {0, 8, 0, 7, 0, 4, 0, 0, 2},
                                    {0, 0, 7, 0, 9, 14, 0, 0, 0},
                                    {0, 0, 0, 9, 0, 10, 0, 0, 0},
                                    {0, 0, 4, 14, 10, 0, 2, 0, 0},
                                    {0, 0, 0, 0, 0, 2, 0, 1, 6},
                                    {8, 11, 0, 0, 0, 0, 1, 0, 7},
                                    {0, 0, 2, 0, 0, 0, 6, 7, 0}};
        ShortestPath t = new ShortestPath(graph.length);
        t.dijkstra(graph, 0);
        System.out.println("Shortest distances from source vertex 0:");
        for (int i = 0; i < t.dist.length; i++)
            System.out.println("Vertex " + i + ": " + t.dist[i]);
    }
}
```

These algorithms are fundamental to graph theory and are used extensively in various applications such as network routing, social network analysis, and recommendation systems. Understanding their implementations and characteristics is crucial for solving graph-related problems efficiently.
