class StackNode {
    
    constructor(data){
    this.data = data; 
    this.next = null;
};

}



class StackLinkedList {
    
    constructor() {
        this.head = null;
    };
    
    
    push(element) {
        const newNode = new StackNode(element);
        if ( !this.head ) {
            this.head = newNode;
            return;
        };
        
        newNode.next = this.head;
        this.head = newNode;
    };
    
    
    pop(){
            if (!this.head) return "underflow";
         let poped = this.head.data;
      this.head = this.head.next;
      return poped
    }
    

        peek() {
    return this.head ? this.head.data : null;
   }

    
    
    isEmpty () {
        return this.head ? false : true;
    };
    
    
    size () {
        let count = 0;
        if ( !this.head ) {
            return count;
        }
        let current = this.head;
        while ( current) {
            count = count +1;
            current = current.next;
        }
        return count
        
    }
    
    
    print(){
        let current = this.head;
        let result = "";
        while (current) {
            result = result + current.data+"<-";
            current = current.next;
        };
        result = result + null;
        console.log(result)
    }
    
};



const stack = new StackLinkedList;
stack.push(10);
stack.push(20);
stack.push(30);
stack.push(49);
console.log(stack.pop())
stack.print();
console.log(stack.peek());
console.log(stack.size());
console.log(stack.isEmpty())