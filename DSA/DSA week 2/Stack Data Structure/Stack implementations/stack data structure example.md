
class Stack {
    constructor () {
        this.items = [];
    };
    
    push(element){
        this.items.push(element);
    };
    
    pop(){
        if ( this.items.length == 0 ) return "underflow";
        return this.items.pop();
    };
    
    isEmpty(){
        return this.items.length === 0;
    };
    
    size () {
        return this.items.length;
    };
    
    peek(){
        return this.items[this.items.length-1];
    }
    print(){
        console.log(this.items);
    }
};


const stack = new Stack;
stack.push(10);
stack.push(20);
stack.push(30);
console.log(stack.pop());
console.log(stack.isEmpty());
console.log(stack.size());
console.log(stack.peek());
stack.print()