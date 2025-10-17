

function selection(ar) {
    for ( let i = 0; i< ar.length -1; i++ ) {
        let mini = i; 
        for( let j = i+1; j< ar.length; j++ ) {
            if ( ar[j] > ar[mini] ) {
                mini = j;
            }
        } 
        if ( mini !== i ){
             let temp = ar[i];
             ar[i] = ar[mini];
             ar[mini] = temp;
        }
    };
    
    return ar;
};

console.log(selection([8,3,4,5,2,6,1]))
