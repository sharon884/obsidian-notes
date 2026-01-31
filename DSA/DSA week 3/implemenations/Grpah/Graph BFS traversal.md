
function bfs(start) {
    let queue = [];
    let visited = new Set();

    visited.add(start);
    queue.push(start);

    while (queue.length) {
        let vertex = queue.shift();
        console.log(vertex);

        for (let neigh of this.adjacencyList[vertex]) {
            if (!visited.has(neigh)) {
                visited.add(neigh);
                queue.push(neigh);
            }
        }
    }
}
