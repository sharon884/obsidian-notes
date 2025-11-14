
class BinaryNode {
    constructor( value ) {
        this.value = value;
        this.left = null; 
        this.right = null;
    };
    
    insert(node) {
        if ( this.value > node  ) {
            if ( this.left == null ) {
                this.left = new BinaryNode(node);
            }else {
                this.left.insert(node);
            }
        }else {
            if ( this.right  == null ) {
                this.right = new BinaryNode(node);
            }else {
                this.right.insert(node);
            }
        }
    };
    
};


function isCompleteBinary ( root  , flag = false ) {
      
      if ( !root  ) return true;
      const queue = [ root ];
      while ( queue.length > 0 ) {
        let   node = queue.shift();
          if ( node === null ) {
              flag = true;
          };
          
          if ( flag ) {
              if ( node ) {
                  return false;
                  break;
              }
          }else {
              queue.push(node.left);
               queue.push(node.right);
          }
      }
      
      return true ;
}










