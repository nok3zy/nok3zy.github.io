---
title: "Shortest Path"
excerpt : ""
categories:
  - 알고리즘
tags :
  - algorithm, dijkstra, Floyd-Warshall, Bellman-Ford
---

# 최단경로 문제
> 두 노드를 잇는 최단 경로를 찾는 문제를 최단경로 문제라고 한다.    
> 보통 가중치가 있는 그래프에서 그 가중치들의 합이 최소가 되게 하는 경로를 찾는 것이 목적이다. 

## 최단 경로 알고리즘
> - 다익스트라 알고리즘    
> - 벨만-포드 알고리즘 
> - 플로이드-와샬 알고리즘

## 다익스트라 알고리즘
> 가장 기본적인 최단경로 알고리즘이라고 해도 무방함.    
> heap 을 이용한 알고리즘.    
> 

<code>

        from heapq import heappop,heappush
        # distance : 시작점부터의 거리.
        distance = [sys.maxsize]*number_of_nodes
        heap = [(weight,node)] 
        while heap:
          cur_w, cur = heappop(heap)
          if distance[cur] < cur_w : continue
          for nxt_w,nxt in graph[cur]:
            if distance[nxt] > distance[cur] + nxt_w:
              distance[nxt] = distance[cur] + nxt_w
              heappush(heap, (distance[nxt],nxt) )

</code>

## 벨만-포드 알고리즘
> 다익스트라 알고리즘과 달리 음수 간선에서도 유효하다.    
> 
>
>
>

## 플로이드-와샬 알고리즘 
> i에서 k 로 가는 최단경로를 찾기 위해서 i->j->k 의 경로를 비교를 한다.     
> 

<code>

        for i in range(n):
          for j in range(n):
            for k in range(n):
              if adj[i][k] < adj[i][j]+adj[j][k]:
                adj[i][k] = adj[i][j]+adj[j][k]


</code>
