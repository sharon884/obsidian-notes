class Bt {
    constructor(value) {
        
    this.value = value;
    this.left = null;
    this.right = null;
};


insertright ( value ) {
    const newNode = new Bt(value);
    this.right = newNode;
    return newNode;
    
}

insertleft( value ) {
    const newNode = new Bt(value);
    this.left = newNode;
    return newNode;
};
};
    


const a = new Bt(10);
const b = new Bt(103);
const c = new Bt(101);
const d = new Bt(102);
const e = new Bt(105);
const f = new Bt(104);
const g = new Bt(108);
const h = new Bt(106);
const i = new Bt(109);


a.left = b;
a.right = c;
b.left = d;
b.right = e;
c.left = f;
c.right = g;
d.left = h;
d.right = i;



function postOrder(root) {
    if ( !root ) return;
    postOrder(root.left);
    postOrder(root.right);
    console.log(root.value)
};


// postOrder(a)


function preorder(root) {
    if ( !root ) return;
    console.log(root.value);
    preorder(root.left);
    preorder(root.right);
};

// preorder(a)


function inorder(root) {
    if ( !root) return;
    inorder(root.left)
    console.log(root.value);
    inorder(root.right);
};

inorder(a)