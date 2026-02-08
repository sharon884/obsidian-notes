

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
    
    
    printList(){
        let current = this.head;
        let result = "";
        while ( current ){
            result = result + current.data + "=>";
            current = current.next;
        }
        result = result + null;
        console.log(result);
    }
};




const list = new LinkedList;
list.append(10);
list.append(20);
list.append(30);
list.printList();




<h3>result </h3>
10=>20=>30=>null