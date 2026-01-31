
dfs(node, visited = new Set()) {
    visited.add(node);
    console.log(node);

    for (let neighbor of this.adjacencyList[node]) {
        if (!visited.has(neighbor)) {
            this.dfs(neighbor, visited);
        }
    }
}
