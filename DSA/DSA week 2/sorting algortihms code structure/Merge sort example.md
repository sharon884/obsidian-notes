
const arr = [ 1,4,5,7,8,1,2,100];

function mergesort(arr) {
    
    if ( arr.length <= 1) return arr;
    
    let mid = Math.floor((arr.length / 2));
    let left = arr.slice(0,mid);
    let right = arr.slice(mid);
    
    let sortedleft = mergesort(left);
    let sortedright = mergesort(right);
    
    return merge(sortedleft,sortedright );
};

function merge(left,right) {
    
    let result = [];
   let i =0; 
   let j = 0; 
   while ( i < left.length && j < right.length ) {
       if ( left[i] < right[j] ) {
          result.push(left[i]);
          i++;
       }else {
           result.push(right[j]);
           j++;
       }
   };
   
   return result.concat(left.slice(i)).concat(right.slice(j));
};


console.log(mergesort(arr))