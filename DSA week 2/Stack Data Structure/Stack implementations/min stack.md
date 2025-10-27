class Stack {
    constructor() {
        this.stack1 = [];
        this.stack2 = [];
    };
    
    
    push( element ) {
        if ( this.stack1.length === 0 && this.stack2.length === 0 ) {
            this.stack1.push(element);
            this.stack2.push(element);
            return;
        } 
        
        let top = this.stack2[this.stack2.length-1];
        if ( top > element ) {
            this.stack1.push(element);
            this.stack2.push(element);
        }else {
            this.stack1.push(element);
            this.stack2.push(top)
        }
    };
    
    
    pop() {
        this.stack1.pop();
        this.stack2.pop();
        return;
    };
    
    getmin() {
        return this.stack2[this.stack2.length-1];
    };
    print(){
        return console.log(this.stack1)
    }
};

const stack = new Stack ;
stack.push(10)
stack.push(100)
stack.push(1000)
stack.push(1)
stack.push(2)
stack.push(0)
stack.print()
console.log(stack.getmin());
stack.pop();
stack.print();
console.log(stack.getmin());
