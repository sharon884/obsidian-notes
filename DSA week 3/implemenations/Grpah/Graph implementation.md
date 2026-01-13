
class Graph {
    constructor() {
        this.adjacencyList = {};
    }

    addVertex(v) {
        if (!this.adjacencyList[v]) {
            this.adjacencyList[v] = [];
        }
    }

    addEdge(v1, v2) {
        if (!this.adjacencyList[v1] || !this.adjacencyList[v2]) return;

        if (!this.adjacencyList[v1].includes(v2)) {
            this.adjacencyList[v1].push(v2);
            this.adjacencyList[v2].push(v1);
        }
    }

    removeEdge(v1, v2) {
        if (!this.adjacencyList[v1] || !this.adjacencyList[v2]) return;

        this.adjacencyList[v1] =
            this.adjacencyList[v1].filter(v => v !== v2);

        this.adjacencyList[v2] =
            this.adjacencyList[v2].filter(v => v !== v1);
    }

    removeVertex(v) {
        if (!this.adjacencyList[v]) return;

        for (let neighbor of this.adjacencyList[v]) {
            this.removeEdge(v, neighbor);
        }

        delete this.adjacencyList[v];
    }
}
