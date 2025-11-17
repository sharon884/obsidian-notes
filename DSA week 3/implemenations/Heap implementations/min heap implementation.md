
class Heap {
    constructor() {
        this.arr = [];
    };
    
    
    getParrent(index) {
        return Math.floor((index-1)/2);
    };
    
    getleft(index){
        return (2*index)+1;
    };
    
    getright(index) {
        return ( 2* index ) +2;
    };
    
    swap(i,j) {
        [this.arr[i], this.arr[j]] = [this.arr[j], this.arr[i]];
    }
    
    insert(value) {
        this.arr.push(value);
         this.heapifyup(this.arr.length-1);
    };
    
    heapifyup(index) {
        while( index > 0 ) {
            let parrent  = this.getParrent(index);
            if ( this.arr[index] < this.arr[parrent] ) {
                this.swap(index,parrent);
                index = parrent;
            }else {
                break;
            }
        }
    }
    
    display(){
        console.log(this.arr);
        return;
    }
    
};






const heap = new Heap();
heap.insert(10)
heap.insert(109)
heap.insert(130)
heap.insert(102)
heap.insert(104)
heap.display()



