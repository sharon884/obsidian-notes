

class General {
    constructor( node ) {
        this.value = node;
        this.children = [];
    }
};


const rootNode = new General(10);
const newNode1 = new General(100);
const newNode3 = new General(1100);
const newNode2 = new General(110);
const newNode4 = new General(1040);
const newNode5 = new General(1005);


rootNode.children.push(newNode1,newNode2,newNode3,newNode4,newNode5);

newNode1.children.push(new General(200));
newNode1.children.push(new General(300));

newNode3.children.push(new General(400));


function bfs ( node ) {
    if ( !node ) return ;
    
    let queue = [ node ];
    while ( queue.length > 0 ) {
      let node = queue.shift();
      console.log(node.value);
      
      for ( let child of node.children ) {
          queue.push(child);
      }
    }
};

bfs(rootNode)