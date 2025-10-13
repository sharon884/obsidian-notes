


class Node {
    constructor(data){
        this.data = data;
        this.next = null;
        
    }
};


class LinkedList{
    constructor(){
        this.head = null;
    }
    
    append(data){
        const newNode = new Node(data);
        
        if ( !this.head ) {
            this.head = newNode;
            return;
        };
        
        let current = this.head;
        while(current.next!== null){
            current = current.next;
        }
        current.next = newNode;
    };
    
    
    prepend(data){
        const newNode = new Node(data);
        
        newNode.next = this.head;
        this.head = newNode;
        
        
    };
    
    
     figerout(value) {
         let current = this.head;
         while (current) {
             if (current.data === value ) {
                 console.log(true)
                 return "found";
             };
             current = current.next;
         }
         
         return "not found";
     }
     
    addarvalue(ar){
        for ( let num of ar){
            this.append(num)
        }
    }
    
    printList(){
        let current = this.head;
        let result = "";
        let length = 0
        while ( current ){
            result = result + current.data + "=>";
            current = current.next;
            length = length + 1;
        }
        result = result + null;
        console.log(result);
        console.log(length)
    }
};


const ar = [1,3,4,5,6];

const list = new LinkedList;
list.append(10);
list.append(20);
list.append(30);
list.prepend(8000)
list.addarvalue(ar);
list.printList();
list.figerout(20)







