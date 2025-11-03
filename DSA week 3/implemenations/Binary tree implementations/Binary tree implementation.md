class BinaryNode {
    constructor(value) {
        this.value = value;
        this.left = null;
        this.right =null;
    };
    
    insertLeft( value ) {
        const newNode = new BinaryNode(value);
        this.left = newNode;
        return newNode;
    };
    
    insertRight(value) {
        const newNode = new BinaryNode(value);
        this.right = newNode;
        return newNode;
    }
};

const root = new BinaryNode(10);
const left = root.insertLeft(20);
const right = root.insertRight(30);

left.insertLeft(40);
right.insertLeft(50);
right.insertLeft(60);
right.insertRight(70);

