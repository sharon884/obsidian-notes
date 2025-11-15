
class BinarySerch {
    constructor ( value ) {
        this.value = value;
        this.left = null;
        this.right  = null;
    };
    
    
    insert( node ) {
        if ( this.value > node ) {
            if ( this.left === null ) {
                this.left = new BinarySerch(node);
            }else {
                this.left.insert(node);
            }
        }else {
            if ( this.right == null ) {
                this.right = new BinarySerch(node);
            }else {
                this.right.insert(node);
            }
        }
    }
};


function isValidBinary( root, min = -Infinity, max = Infinity ) {
     
     if ( !root ) return true;
     
     if ( root.value <= min || root.value  >= max ) {
         return false;
     };
     
     return    isValidBinary(root.left,min, root.value  ) &&    isValidBinary(root.right,root.value, max)
}














