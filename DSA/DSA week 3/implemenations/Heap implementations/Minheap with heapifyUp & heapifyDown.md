
class Minheap {
    constructor () {
        this.arr = [];
    };
    
    getParrent( index ) {
        return Math.floor((index-1)/2);
    }
    
    getLeft ( index ) {
        return Math.floor((2*index)+1);
    };
    
    getRight( index ) {
        return Math.floor((2* index ) +2);
    };
    
    swap( i, j ) {
        [this.arr[i], this.arr[j] ] = [ this.arr[j], this.arr[i]];
    };
    
    insert( value ) {
        this.arr.push(value);
        this.heapifyUp( this.arr.length-1);
    };
    
    heapifyUp( index ) {
        while ( index > 0 ) {
            let parrent = this.getParrent(index);
            if ( this.arr[parrent] > this.arr[index] ) {
                this.swap(index,parrent);
                index = parrent;
            }else{
                break;
            }
        }
    };
    
    heapifyDown( index ) {
        let size = this.arr.length;
        while ( true ) {
            let smallest = index;
            let left = this.getLeft(index);
            let right = this.getRight(index);
            
            if ( left < size && this.arr[left] < this.arr[smallest] ) {
                smallest = left;
            };
            
            if ( right < size && this.arr[right] < this.arr[smallest] ) {
                smallest = right;
            };
            
            if ( smallest !== index ) {
                this.swap(index,smallest );
                index = smallest;
            }else {
                break;
            }
        }
    }
}