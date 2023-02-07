# 넓이 우선 탐색(BFS)
**Write** : 2023-01-31 01:27
**Tag** : #Algorithme #알고리즘이론
***
시작 정점으로부터 가까운 정점을 우선 탐색하는 알고리즘
- 사용하는 경우 : 두 노드 사이의 최단 경로 혹은 임의의 경로를 찾고 싶을 때

## BFS의 특징
- BFS는 시작 정점으로부터 거리가 가까운 정점의 순서로 탐색한다.
- 노드의 방문여부를 반드시 검사해야 한다.
- BFS는 재귀적으로 동작하지 않는다.
- BFS는 방문한 노드들을 차례로 저장한 후 꺼낼 수 있는 큐(Queue)를 사용한다.
- 즉, 선입선출 원칙으로 탐색
- 일반적으로 큐를 이용해서 반복적 형태로 구현하는 것이 가장 잘 동작한다.

## BFS의 수행 과정
![image](https://user-images.githubusercontent.com/56426044/215669031-79ecd910-6fd9-4ac1-a90a-4af2d4a5bf87.png)
## 구현하기

```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

int N = Integer.parseInt(br.readLine()); // 정점의 개수
int M = Integer.parseInt(br.readLine()); // 간선의 개수
int V = Integer.parseInt(br.readLine()); // 시작 노드의 번호

ArrayList<Integer>[] list = new ArrayList[N + 1];
boolean[] visited = new boolean[N + 1]; // 노드 방문 여부 확인을 위한 리스트

for (int i = 1; i <= N; i++) {  
    list[i] = new ArrayList<>();  
}

bfs(V);
```

```java
private static void bfs(int V) {  
    Queue<Integer> que = new LinkedList<Integer>();  
    que.offer(V);  
    visited[V] = true;  
  
    while (!que.isEmpty()) {  
        int cur = que.poll();  
  
        for (int i = 0; i < list[cur].size(); i++) {  
            if (!visited[list[cur].get(i)]) {  
                visited[list[cur].get(i)] = true;  
                que.offer(list[cur].get(i));  
            }  
        }  
    }  
}
```