# 🎯 Graphs — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../dsa.md) · [Trees Patterns](trees-patterns-tier1.md) · [Arrays Patterns](arrays-patterns-tier1.md) |
| **Status** | ✅ Complete — Graphs (6th in the Tier-1 pattern series) |
| **Kind** | Structure file (pattern-organized) |
| **Scope** | Directed & undirected graphs, grids and DAGs, organized by **pattern**, Tier-1 / MAANG |
| **Coverage** | 9 patterns · 70 questions |
| **Related** | Next in series → `heaps-patterns-tier1.md` |

---

## 📖 Read this first — how to use the bank (and why it's built this way)

**Why pattern-first?** At Tier-1/MAANG the interview is a **pattern-recognition** game — you solve a
*new* problem by matching it to a pattern you know. This bank is organized by the **pattern that
cracks the problem**, not as a flat list.

**The one mental model for graphs:** *first recognize it's a graph* — grid cells, words, lock states,
and courses are all **nodes**; adjacency is the edges. Then pick the tool:
- **BFS** → shortest path in an *unweighted* graph, or level-by-level.
- **DFS** → connectivity, paths, cycles, components.
- **Union-Find** → dynamic connectivity ("are these connected?", merging groups).
- **Topological Sort** → ordering under dependencies (DAG).
- **Dijkstra / Bellman-Ford** → shortest path with *weights*.

The genuinely hard step is usually noticing the graph — once you do, the algorithm is one of the above.

**How to work through it:** per pattern → read the **🔍 recognize it when…** cue, then solve top-down
(easy → hard). Solve from the prompt; the `input → output` example is only to confirm you understood
the question. Goal: **name the pattern in under 60 seconds** on a new problem.

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> **Always** mark nodes *visited* to avoid infinite loops. **See also:** pure matrix manipulation (rotate/spiral/search) → [Arrays bank → Matrix](arrays-patterns-tier1.md#p9).

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [Grid Traversal (Flood Fill / Islands)](#p1) | 12 | a 2D grid where you explore connected cells (4/8-directional) |
| 2 | [Graph Traversal (Adjacency / Components)](#p2) | 8 | a general graph — explore, clone, or count connected components |
| 3 | [Topological Sort](#p3) | 8 | ordering under dependencies in a DAG — "prerequisites", "build order" |
| 4 | [Union-Find (DSU)](#p4) | 9 | dynamic connectivity, merging groups, detecting a redundant edge |
| 5 | [BFS Shortest Path (unweighted)](#p5) | 8 | fewest steps/edges in an unweighted graph or implicit state-space |
| 6 | [Weighted Shortest Path (Dijkstra / Bellman-Ford)](#p6) | 8 | cheapest path with edge weights, possibly with hop limits |
| 7 | [Minimum Spanning Tree](#p7) | 5 | connect all nodes at minimum total edge cost |
| 8 | [Bipartite & Cycle Detection](#p8) | 6 | 2-coloring feasibility, or detecting a cycle |
| 9 | [Advanced Graph](#p9) | 6 | bridges/articulation, Eulerian path, or a specialized algorithm |

---

<a id="p1"></a>
## 1 · Grid Traversal — Flood Fill / Islands (12)

> 🔍 **Recognize it when…** the input is a 2D grid and you explore connected cells (usually
> 4-directional) via DFS or BFS — count/measure regions, or spread from multiple sources.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Flood Fill | 🟢 | `image, sr=1, sc=1, color=2 → recolored region` | ⭐⭐ |
| 2 | Island Perimeter | 🟢 | `[[0,1,0,0],[1,1,1,0],[0,1,0,0],[1,1,0,0]] → 16` | ⭐⭐ |
| 3 | Number of Islands | 🟡 | `grid of '1'/'0' → 3` | ⭐⭐⭐ |
| 4 | Max Area of Island | 🟡 | `grid → 6` | ⭐⭐⭐ |
| 5 | Number of Closed Islands | 🟡 | `grid → 2` | ⭐⭐ |
| 6 | Count Sub Islands | 🟡 | `grid1, grid2 → 3` | ⭐⭐ |
| 7 | Number of Distinct Islands | 🟡 | `grid → 1` | ⭐⭐ |
| 8 | Surrounded Regions | 🟡 | `board → border-connected 'O' kept, rest → 'X'` | ⭐⭐⭐ |
| 9 | Rotting Oranges (multi-source BFS) | 🟡 | `[[2,1,1],[1,1,0],[0,1,1]] → 4` | ⭐⭐⭐ |
| 10 | Pacific Atlantic Water Flow | 🟡 | `heights → cells reaching both oceans` | ⭐⭐⭐ |
| 11 | 01 Matrix (distance to nearest 0) | 🟡 | `[[0,0,0],[0,1,0],[1,1,1]] → [[0,0,0],[0,1,0],[1,2,1]]` | ⭐⭐⭐ |
| 12 | Making A Large Island | 🔴 | `grid → 3` | ⭐⭐ |

<a id="p2"></a>
## 2 · Graph Traversal — Adjacency / Components (8)

> 🔍 **Recognize it when…** you're given a general graph (edge list / adjacency) and must explore it,
> clone it, or count connected components.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Find if Path Exists in Graph | 🟢 | `n=3, edges=[[0,1],[1,2],[2,0]], src=0, dst=2 → true` | ⭐⭐ |
| 2 | Find the Town Judge | 🟢 | `n=2, trust=[[1,2]] → 2` | ⭐⭐ |
| 3 | Number of Provinces | 🟡 | `[[1,1,0],[1,1,0],[0,0,1]] → 2` | ⭐⭐⭐ |
| 4 | Number of Connected Components in an Undirected Graph | 🟡 | `n=5, edges=[[0,1],[1,2],[3,4]] → 2` | ⭐⭐⭐ |
| 5 | Clone Graph | 🟡 | `adjacency list → deep copy` | ⭐⭐⭐ |
| 6 | Keys and Rooms | 🟡 | `[[1],[2],[3],[]] → true` | ⭐⭐ |
| 7 | All Paths From Source to Target (DAG) | 🟡 | `[[1,2],[3],[3],[]] → [[0,1,3],[0,2,3]]` | ⭐⭐⭐ |
| 8 | Minimum Number of Vertices to Reach All Nodes | 🟡 | `n=6, edges → [0,3]` | ⭐⭐ |

<a id="p3"></a>
## 3 · Topological Sort (8)

> 🔍 **Recognize it when…** items have ordering constraints in a DAG — "prerequisites", "build order".
> Kahn's BFS (indegree = 0 queue) or DFS post-order.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Course Schedule (can finish?) | 🟡 | `numCourses=2, [[1,0]] → true` | ⭐⭐⭐ |
| 2 | Course Schedule II (an order) | 🟡 | `numCourses=4, prereqs → [0,1,2,3]` | ⭐⭐⭐ |
| 3 | Find Eventual Safe States | 🟡 | `graph → [2,4,5,6]` | ⭐⭐ |
| 4 | Minimum Height Trees | 🟡 | `n=4, edges=[[1,0],[1,2],[1,3]] → [1]` | ⭐⭐ |
| 5 | Parallel Courses (min semesters) | 🟡 | `n=3, relations=[[1,3],[2,3]] → 2` | ⭐⭐ |
| 6 | Course Schedule IV (reachability queries) | 🟡 | `→ [true,false]` | ⭐⭐ |
| 7 | Alien Dictionary | 🔴 | `["wrt","wrf","er","ett","rftt"] → "wertf"` | ⭐⭐⭐ |
| 8 | Sort Items by Groups Respecting Dependencies | 🔴 | `→ a valid ordering` | ⭐ |

<a id="p4"></a>
## 4 · Union-Find — DSU (9)

> 🔍 **Recognize it when…** you answer dynamic connectivity ("are these connected?"), merge groups, or
> detect a redundant/extra edge. Use union-by-rank + path compression.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Number of Operations to Make Network Connected | 🟡 | `n=4, connections=[[0,1],[0,2],[1,2]] → 1` | ⭐⭐⭐ |
| 2 | Redundant Connection | 🟡 | `[[1,2],[1,3],[2,3]] → [2,3]` | ⭐⭐⭐ |
| 3 | Graph Valid Tree | 🟡 | `n=5, edges=[[0,1],[0,2],[0,3],[1,4]] → true` | ⭐⭐⭐ |
| 4 | Accounts Merge | 🟡 | `accounts → merged by shared email` | ⭐⭐⭐ |
| 5 | Most Stones Removed with Same Row or Column | 🟡 | `stones → 5` | ⭐⭐ |
| 6 | Satisfiability of Equality Equations | 🟡 | `["a==b","b!=a"] → false` | ⭐⭐ |
| 7 | Smallest String With Swaps | 🟡 | `"dcab", pairs=[[0,3],[1,2]] → "bacd"` | ⭐⭐ |
| 8 | Number of Islands II (online) | 🔴 | `positions → island count after each add` | ⭐⭐ |
| 9 | Redundant Connection II (directed) | 🔴 | `→ edge to remove` | ⭐⭐ |

<a id="p5"></a>
## 5 · BFS Shortest Path — unweighted (8)

> 🔍 **Recognize it when…** you need the *fewest steps/edges* in an unweighted graph or an implicit
> state-space (words, lock combos, board positions). BFS explores level by level.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Shortest Path in Binary Matrix | 🟡 | `[[0,1],[1,0]] → 2` | ⭐⭐⭐ |
| 2 | Open the Lock | 🟡 | `deadends, target="0202" → 6` | ⭐⭐ |
| 3 | Shortest Bridge | 🟡 | `grid of two islands → 1` | ⭐⭐ |
| 4 | Snakes and Ladders | 🟡 | `board → 4` | ⭐⭐ |
| 5 | Jump Game III | 🟡 | `[4,2,3,0,3,1,2], start=5 → true` | ⭐⭐ |
| 6 | Minimum Genetic Mutation | 🟡 | `"AACCGGTT" → "AACCGGTA", bank → 1` | ⭐⭐ |
| 7 | Word Ladder | 🔴 | `"hit" → "cog", wordList → 5` | ⭐⭐⭐ |
| 8 | Word Ladder II (all shortest sequences) | 🔴 | `→ every shortest transformation` | ⭐⭐ |

<a id="p6"></a>
## 6 · Weighted Shortest Path — Dijkstra / Bellman-Ford (8)

> 🔍 **Recognize it when…** edges have weights and you want the cheapest/shortest path — Dijkstra
> (non-negative weights, min-heap) or Bellman-Ford (hop limits / negative edges).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Network Delay Time (Dijkstra) | 🟡 | `times=[[2,1,1],[2,3,1],[3,4,1]], n=4, k=2 → 2` | ⭐⭐⭐ |
| 2 | Cheapest Flights Within K Stops (Bellman-Ford) | 🟡 | `n=4, flights, src=0, dst=3, k=1 → 700` | ⭐⭐⭐ |
| 3 | Path with Maximum Probability | 🟡 | `n=3, edges, start=0, end=2 → 0.25` | ⭐⭐ |
| 4 | Path With Minimum Effort | 🟡 | `heights → 2` | ⭐⭐⭐ |
| 5 | The Maze II (rolling ball shortest distance) | 🟡 | `maze, start, dest → 12` | ⭐⭐ |
| 6 | Find the City With Smallest Number of Neighbors (Floyd-Warshall) | 🟡 | `→ city 3` | ⭐⭐ |
| 7 | Swim in Rising Water | 🔴 | `grid → minimum time` | ⭐⭐ |
| 8 | Minimum Cost to Reach Destination in Time | 🔴 | `→ minimum cost within maxTime` | ⭐ |

<a id="p7"></a>
## 7 · Minimum Spanning Tree (5)

> 🔍 **Recognize it when…** you connect *all* nodes at minimum total edge cost — Kruskal (sort edges +
> DSU) or Prim (min-heap from a seed node).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Min Cost to Connect All Points | 🟡 | `[[0,0],[2,2],[3,10],[5,2],[7,0]] → 20` | ⭐⭐⭐ |
| 2 | Connecting Cities With Minimum Cost | 🟡 | `n=3, connections → 6` | ⭐⭐ |
| 3 | Optimize Water Distribution in a Village | 🔴 | `n=3, wells, pipes → 3` | ⭐ |
| 4 | Checking Existence of Edge Length Limited Paths | 🔴 | `edgeList, queries → [false,true]` | ⭐⭐ |
| 5 | Find Critical and Pseudo-Critical Edges in MST | 🔴 | `→ [[critical],[pseudo-critical]]` | ⭐ |

<a id="p8"></a>
## 8 · Bipartite & Cycle Detection (6)

> 🔍 **Recognize it when…** you test 2-colorability ("split into two groups") or detect a cycle in a
> directed (DFS colors) or undirected (DSU / DFS parent) graph.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Is Graph Bipartite? | 🟡 | `[[1,3],[0,2],[1,3],[0,2]] → true` | ⭐⭐⭐ |
| 2 | Possible Bipartition | 🟡 | `n=4, dislikes=[[1,2],[1,3],[2,4]] → true` | ⭐⭐ |
| 3 | Detect Cycle in a Directed Graph | 🟡 | `graph → true / false` | ⭐⭐ |
| 4 | Detect Cycle in an Undirected Graph | 🟡 | `graph → true / false` | ⭐⭐ |
| 5 | Flower Planting With No Adjacent | 🟡 | `n=4, paths → [1,2,3,1]` | ⭐⭐ |
| 6 | Divide Nodes Into the Maximum Number of Groups | 🔴 | `→ max groups or -1` | ⭐ |

<a id="p9"></a>
## 9 · Advanced Graph (6)

> 🔍 **Recognize it when…** the problem needs a specialized algorithm — bridges/articulation points
> (Tarjan), an Eulerian path (Hierholzer), or a BFS/Dijkstra variant with extra state.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Evaluate Division (weighted DFS) | 🟡 | `a/b=2, b/c=3; query a/c → 6.0` | ⭐⭐⭐ |
| 2 | Reconstruct Itinerary (Eulerian / Hierholzer) | 🔴 | `tickets → ["JFK","MUC","LHR","SFO","SJC"]` | ⭐⭐⭐ |
| 3 | Shortest Path Visiting All Nodes (BFS + bitmask) | 🔴 | `graph → 4` | ⭐⭐ |
| 4 | Number of Ways to Arrive at Destination (Dijkstra + count) | 🔴 | `→ 4` | ⭐⭐ |
| 5 | Find All People With Secret | 🔴 | `n, meetings, first → people who know it` | ⭐⭐ |
| 6 | Critical Connections in a Network (bridges, Tarjan) | 🔴 | `→ [[1,3]]` | ⭐⭐⭐ |

---

## ✅ Definition of Done

- [ ] Given a new problem, I can spot when it's **secretly a graph** (grid / words / states = nodes).
- [ ] I reach for the right tool by reflex: BFS (unweighted) · DFS (connectivity/cycles) · Union-Find
      (dynamic connectivity) · Topo sort (DAG order) · Dijkstra (weighted).
- [ ] I implement Union-Find and Dijkstra from scratch, and always mark nodes visited.
- [ ] I've solved every 🟡 and attempted every 🔴 (Alien Dictionary, Word Ladder, MST, bridges).
- [ ] I handle edge cases: disconnected graph, self-loops, cycles, single node, empty graph.

> **Series:** Arrays ✅ · Strings ✅ · Linked List ✅ · Stacks & Queues ✅ · Trees ✅ · Graphs ✅ ·
> next → `heaps-patterns-tier1.md`, then the paradigm files dp → backtracking.
