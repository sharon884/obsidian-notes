

class General {
    constructor(value)  {
        this.value = value;
        this.children = [];
    };
    
    addChild(node) {
        this.children.push(node);
    }
};


const a = new General(10);
const b = new General(20);
const c = new General(30);
const d = new General(40);

a.addChild(b)
a.addChild(c)
a.addChild(d);


b.addChild(new General(50));
b.addChild(new General(60));
b.addChild(new General(70));
b.addChild(new General(80));

function preorder(root) {
    if (!root) return;
    console.log(root.value);
    for ( let child of root.children ) {
        preorder(child)
    }
}



preorder(a);


function postorder(root) {
    if ( !root ) return ;
    for ( let child of root.children ) {
        postorder(child);
    }
        console.log(root.value);
};

postorder(a)