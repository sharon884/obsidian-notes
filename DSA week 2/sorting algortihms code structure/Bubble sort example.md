
let ar = [1,4,2,5,3,6,1];
let swapped = true;

function bubble(ar) {
    
for ( let i = 0; i< ar.length-1; i++ ) {
    swapped = false;
    for ( let j = 0; j < ar.length-1; j++ ) {
        
        if ( ar[j] > ar[j+1] ){
            let temp = ar[j];
            ar[j] = ar[j+1];
            ar[j+1] = temp;
            swapped = true;
        }
    };
    
    if ( !swapped ) {
        break;
    }
}
    return ar;
};

console.log(bubble(ar));


we can make bubble sort more effiecent thorugh the swapped flage varible;
