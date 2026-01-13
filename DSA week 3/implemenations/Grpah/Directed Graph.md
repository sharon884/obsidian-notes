
class Graph {
    constructor() {
        this.adjacencyList = {};
    }

    addVertex(v) {
        if (!this.adjacencyList[v]) {
            this.adjacencyList[v] = [];
        }
    }

    addEdge(from, to) {
        if (!this.adjacencyList[from] || !this.adjacencyList[to]) return;
        this.adjacencyList[from].push(to);
    }

    removeEdge(from, to) {
        if (!this.adjacencyList[from]) return;

        this.adjacencyList[from] =
            this.adjacencyList[from].filter(v => v !== to);
    }

    removeVertex(v) {
        if (!this.adjacencyList[v]) return;

        for (let vertex in this.adjacencyList) {
            this.adjacencyList[vertex] =
                this.adjacencyList[vertex].filter(neigh => neigh !== v);
        }

        delete this.adjacencyList[v];
    }
}
