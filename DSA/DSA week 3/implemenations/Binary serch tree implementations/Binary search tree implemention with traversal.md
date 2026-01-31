
class BST {
    constructor ( value ) {
        this.value = value ;
        this.left = null;
        this.right =null;
    };
    
    insert( value  ) {
        let newNode = new BST ( value );
        if ( this.value > value ) {
            if ( this.left === null ) {
                this.left = newNode;
            }else {
                this.left.insert(value);
            }
        }else {
            if ( this.right === null ) {
                this.right = newNode;
            }else {
                this.right.insert(value);
            }
        }
    };
    
     post( node = this ) {
        if ( !node) return;
        this.post(node.left);
        this.post(node.right);
        console.log(node.value);
    };
    
    
     pre ( node = this ) {
        if ( !node ) return;
        console.log(node.value);
        this.pre(node.left);
        this.pre(node.right);
    };
    
     inn ( node = this) {
        if ( !node ) return ;
        this.inn(node.left);
        console.log(node.value);
        this.inn(node.right);
    };
    
   level ( node = this ) {
       if ( !node ) return ; 
       let queue = [ node ];
       while ( queue.length > 0 ) {
           let current = queue.shift();
           console.log(current.value);
           if ( current.left) {
               queue.push(current.left);
           };
           
           if ( current.right ) {
               queue.push(current.right);
           };
       }
   }
};

