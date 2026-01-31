
const ar = [ 4,5,6,7, 8, 9,1,2];

function insertion (ar ) {
    for( let i = 1; i < ar.length-1; i++ ) {
        let current = ar[i];
        let j = i-1;
        
        while( j>= 0 && ar[j] > current ) {
            ar[j+1] = ar[j];
            j--;
        }
        
        ar[j+1] =current;
    }
};

console.log(insertion)