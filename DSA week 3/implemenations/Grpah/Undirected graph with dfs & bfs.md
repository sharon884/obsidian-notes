
class Graph {
    constructor () {
        this.adjecencyList ={};
    };
    
    addVertex ( v ) {
        if ( !this.adjecencyList[v] ) {
            this.adjecencyList[v] = [];
        }
    };
    
    addEdge ( v1, v2 ) {
        if ( !this.adjecencyList[v1] || !this.adjecencyList[v2] ) {
            return;
        };
        
        this.adjecencyList[v1].push(v2);
        this.adjecencyList[v2].push(v1);
    };
    
    
    removeEdge( v1 ,v2 ) {
        if ( !this.adjecencyList[v1] || !this.adjecencyList[v2] ) {
            return ;
        };
        
        this.adjecencyList[v1] = this.adjecencyList[v1].filter((a) => a != v2);
        this.adjecencyList[v2] = this.adjecencyList[v2].filter((a) => a != v1);
    };
    
    removeVertex ( v1 ) {
        if ( !this.adjecencyList[v1] ) {
            return;
        };
        
        while ( this.adjecencyList[v1].length ) {
            let edge = this.adjecencyList[v1].pop();
            this.removeEdge(v1,edge);
        };
        
        delete this.adjecencyList[v1];
    };
    
    dfs ( start, visited = new Set() ) {
        
       visited.add(start);
       console.log(start);
       for ( let neigh of this.adjecencyList[start] ) {
           if ( !visited.has(neigh) ) {
               this.dfs(neigh,visited )
           }
       }
        
    }; 
    
    bfs ( start ) {
        let visited = new Set();
        let queue = [];
        
        visited.add(start);
        queue.push(start );
        
        while ( queue.length > 0 ) {
            
            let vertex = queue.shift();
            console.log(vertex);
            for ( let neigh of this.adjecencyList[vertex] ) {
                if ( !visited.has(neigh) ) {
                    visited.add(neigh);
                    queue.push(neigh);
                }
            }
        }
    }
};



const graph = new Graph();
graph.addVertex("A");
graph.addVertex("b");
graph.addVertex("c");
graph.addVertex("d");
graph.addVertex("e");
graph.addEdge("A","b");
graph.addEdge("A","c");
graph.addEdge("A","d");
graph.addEdge("A","e");
graph.dfs("A");
graph.bfs("A")