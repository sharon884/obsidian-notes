
class Heap {
    constructor() {
        this.arr = [];
    };
    
    
    getParrent(i) {
        return Math.floor((i-1)/2);
    };
    
    getleft(i) {
        return 2 * i + 1;
    };
    
    getright(i) {
        return 2*i+2;
    };
    
    
    swap(i,j) {
        [this.arr[i],this.arr[j] ] = [ this.arr[j], this.arr[i]];
    };
    
    
    insert(value){
        this.arr.push(value);
        this.heapifyup(this.arr.length-1);
    };
    
    
    heapifyup(index) {
        while ( index > 0) {
            let parrentIndex = this.getParrent(index);
            if ( this.arr[index] > this.arr[parrentIndex] ) {
                this.swap(index,parrentIndex);
                index = parrentIndex;
            }else {
                break;
            }
        }
    }
    display(){
        console.log(this.arr);
        return;
    };
};


const heap = new Heap();
heap.insert(1);
heap.insert(1);
heap.insert(122);
heap.insert(12);
heap.insert(13);
heap.display()
