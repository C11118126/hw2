# hw2
import matplotlib.pyplot as plt
import networkx as nx

tasks = {
    1: {"description": "研擬計畫", "duration": 1, "predecessors": []},
    2: {"description": "任務分配", "duration": 4, "predecessors": [1]},
    3: {"description": "取得硬體", "duration": 17, "predecessors": [1]},
    4: {"description": "程式開發", "duration": 70, "predecessors": [2]},
    5: {"description": "安裝硬體", "duration": 10, "predecessors": [3]},
    6: {"description": "程式測試", "duration": 30, "predecessors": [4]},
    7: {"description": "撰寫使用手冊", "duration": 25, "predecessors": [5]},
    8: {"description": "轉換檔案", "duration": 20, "predecessors": [5]},
    9: {"description": "系統測試", "duration": 25, "predecessors": [6]},
    10: {"description": "使用者訓練", "duration": 20, "predecessors": [7, 8]},
    11: {"description": "使用者測試", "duration": 25, "predecessors": [9, 10]},
}


G = nx.DiGraph()


for task_id, task_info in tasks.items():
    G.add_node(task_id, label=task_info['description'], duration=task_info['duration'])


for task_id, task_info in tasks.items():
    for predecessor in task_info["predecessors"]:
        G.add_edge(predecessor, task_id)


pos = nx.spring_layout(G)

plt.figure(figsize=(10, 8))
nx.draw(G, pos, with_labels=True, node_size=2000, node_color="lightblue", font_size=10, font_weight='bold')
nx.draw_networkx_edge_labels(G, pos, edge_labels={(u, v): f"{tasks[v]['duration']}天" for u, v in G.edges()})
plt.title("PERT/CPM 圖 - 任務依存關係")
plt.show()
