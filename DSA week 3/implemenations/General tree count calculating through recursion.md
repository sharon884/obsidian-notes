
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



function countof ( root ) {
    if ( !root ) return 0;
    let count  = 1;
    for( let child of root.children ) {
        count = count + countof(child);
    };
    
    return count;
};

console.log(countof(a))