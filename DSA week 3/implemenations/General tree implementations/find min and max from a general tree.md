

class General {
    constructor(value) {
        this.value = value;
        this.children = [];
    };
    
    
    addChild(value) {
        this.children.push(value);
    }
};


const a = new General(10)
const b = new General(102)
const c = new General(103)
const d = new General(104)
const e = new General(105)
const f = new General(103)
const g = new General(102)
const h = new General(101);

a.addChild(b)
a.addChild(c)
a.addChild(d)
b.addChild(e)
b.addChild(f)
b.addChild(g)
b.addChild(h);

function findMax ( root ) {
    let max = root.value;
    for ( let child of root.children ) {
        let childMax  = findMax(child);
        max = Math.max(max,childMax);
    };
    return max;
};

console.log(findMax(a));



function findMin( root ) {
    let min = root.value;
    for ( let child of root.children ) {
        let childmin = findMin(child);
        min = Math.min(min,childmin);
    };
    
    return min;
};


console.log(findMin(a))