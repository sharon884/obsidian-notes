
class BST {
    constructor(value) {
        this.value = value;
        this.left = null;
        this.right = null;
    };
    
    
    insert(value) {
        if ( value < this.value ) {
            if ( this.left === null ) {
                this.left = new BST(value);
            }else {
                this.left.insert(value);
            }
        }else if ( this.value < value ) {
            if ( this.right === null ) {
                this.right = new BST(value);
            }else {
                this.right.insert(value);
            }
        }
    };
    
    
    serch(value) {
        if ( this.value === value ) {
            return true;
        };
        
        if ( this.value > value && this.left !== null ) {
            return this.left.serch(value);
            
        }else if ( this.value < value && this.right !== null ) {
            return this.right.serch(value);
        };
        
        return false;
    }
};


const root = new BST(10);
root.insert(20);
root.insert(2);
root.insert(4);
root.insert(50);
console.log(root.serch(50))