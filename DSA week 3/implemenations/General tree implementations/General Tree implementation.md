
class TreeNode {
    constructor(value) {
        this.value = value;
        this.children = [];
    };
    
    
    addChild(childNode) {
        this.children.push(childNode);
    };
};



let a  = new TreeNode(100);
let  b = new TreeNode(200);
let c = new TreeNode(300);
let d = new TreeNode(400);


a.addChild(b);
a.addChild(c);
a.addChild(d);

let e = new TreeNode(500);
let f = new TreeNode(600);
let g = new TreeNode(700);

b.addChild(e);
b.addChild(f);
b.addChild(g);




<h3> this trvaerse is an example for the preorder traverse  </h3>


function traverse(node){
    if ( node.value == null ) return node;
    console.log(node.value);
    for ( let child of node.children ) {
        
    traverse(child);
    };
    
}

traverse(a)

