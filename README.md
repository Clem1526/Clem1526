import json # for file IO
import networkx as nx # for the graphs
from random import randint # pseudo-randomness
import matplotlib.pyplot as plt # for the drawings
from networkx.readwrite import json_graph # for output
     

G = nx.Graph() # simple undirected graph
n = 7 # graph order (= number of vertices)
m = 2 * n # graph size (= number of edges)
     

G.add_nodes_from(range(1, n + 1)) # add vertices 1, 2, ..., n

while len(G.edges) < m: # add edges until the goal size is reached
    v = randint(1, n) # pick a vertex uniformly at random
    u = randint(1, n) # pick another
    if v != u: # if they differ, add it
        G.add_edge(v, u) # unit weight by default
     

# set some options for the drawing
opt = { 'node_color': 'green',
        'node_size': 500,
        'width': 3,
        'with_labels': True }
coords = nx.spring_layout(G) # fix the positions
nx.draw(G, pos = coords, **opt) # create a drawing








