


class Binary { 
 constructor ( value ) {
     this.value = value;
     this.left = null;
     this.right = null;
 };
 
 
 insert( value ) {
     if ( this.value > value ) {
         if ( this.left == null ) {
             this.left = new Binary ( value);
         }else {
             this.left.insert(value);
         }
     }else {
         if ( this.right === null ) {
             this.right = new Binary(value);
         }else {
             this.right.insert(value);
         }
     }
 }

};




function isFullBinary ( root, visited = new Set()) {
    
    if ( !root ) return true;
    if ( visited.has( root )) return false;
    visited.add(root);
    
    const children = [];
    if ( root.left ) children.push(root.left);
    if ( root.right ) children.push(root.right);
    if ( children.length === 1 ) return false;
    
    return isFullBinary(root.left,visited ) && isFullBinary(root.right,visited );
};


const root = new Binary(10);
root.insert(5);
root.insert(20);
console.log(isFullBinary(root))








