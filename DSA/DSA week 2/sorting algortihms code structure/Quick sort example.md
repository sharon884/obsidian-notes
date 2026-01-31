
function quick(arr) {
 
 if ( arr.length <= 1) return arr;

 const pivot = arr[arr.length-1];
 let left = [];
 let right = [];
 
 for ( let i = 0; i < arr.length-1; i++ ) {
     if ( arr[i] < pivot) {
         left.push(arr[i]);
     }else {
         right.push(arr[i]);
     }
 };
 
 return [...quick(left),pivot,...quick(right)];
 
};

console.log(quick([55,3,55,2,55]))