
//binary search tree 

class Bst {
    constructor(value) {
        this.value = value;
        this.left = null;
        this.right = null;
    };
    
    
    insert(value) {
        if ( value < this.value ) {
            if ( this.left === null ) {
                 this.left = new Bst(value);   
            }else {
                this.left.insert(value);
            }
        } else if ( value > this.value ) {
             if ( this.right === null ) {
                 this.right = new Bst(value);
             }else {
                 this.right.insert(value);
             }
        }
    }
    
    preorder(root = this) {
        if ( !root) return ;
        console.log(root.value);
        this.preorder(root.left);
        this.preorder(root.right);
    };
    
    postorder(root= this){
        if ( !root ) return;
        this.postorder(root.left);
        this.postorder(root.right);
        console.log(root.value)
    }
};


const bst = new Bst(90);
bst.insert(20)
bst.insert(200)
bst.insert(201)
bst.insert(203)
bst.insert(2033)
bst.insert(204)
// bst.preorder()
bst.postorder()