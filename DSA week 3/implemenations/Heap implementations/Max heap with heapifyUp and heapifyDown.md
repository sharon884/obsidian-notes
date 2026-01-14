

class MaxHeap {
    constructor () {
        this.arr = [];
    };
    
    getParrent( index ) {
        return Math.floor(( index -1) /2);
    };
    
    getLeft( index ) {
        return Math.floor((2*index)+1);
    };
    
    getRight( index ) {
        return Math.floor((2*index)+2);
    };
    
    swap( i, j ) {
        [this.arr[i], this.arr[j] ] = [ this.arr[j], this.arr[i] ];
    };
    
    insert( value ){
        this.arr.push(value);
        this.heapifyUp( this.arr.length-1);
    };
    
    heapifyUp( index ) {
        while ( index > 0 ) {
            let parrent = this.getParrent(index);
            if ( this.arr[index ] > this.arr[parrent] ) {
                this.swap(index,parrent);
                index = parrent;
            }else {
                break;
            }
        }
    };
    
    heapifyDown( index ) {
        let size = this.arr.length;
        while ( true ) {
            
            let largest = index;
            let left = this.getLeft(index);
            let right = this.getRight(index);
            
            if ( left < size && this.arr[left] > this.arr[largest ] ) {
                largest = left;
            };
            
            if ( right < size && this.arr[right] > this.arr[largest] ) {
                largest = right;
            };
            
            if ( largest !== index ) {
                this.swap(largest,index);
                index = largest;
            }else {
                break;
            }
            
        }
    }
}