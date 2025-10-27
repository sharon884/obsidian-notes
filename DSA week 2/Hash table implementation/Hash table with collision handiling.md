
Hash table with collisin handling 
using techinque ->  separae chaining ( open hashing );

class HashTable {
    constructor(size) {
        this.table = new Array(size).fill();
        this.size = size;
    };
    
    
    hash(key) {
        let total = 0;
        for ( let i =0; i < key.length; i++ ) {
             total = total + key.charCodeAt(i);
        }
       return total = total % this.size;
    };
    
    
    set( key, value ) {
        let index = this.hash(key);
        if ( !this.table[index] ) {
            this.table[index] = [];
        };
        
        for ( let pair of this.table[index] ){
            if ( pair[0]  === key ){
                pair[1] = value;
                return;
            }
        };
        
        this.table[index].push([key,value])
    };
    
    get ( key ) {
        let index = this.hash(key);
        if ( !this.table[index] ) {
            return undefined;
        };
        
        for ( let pair of this.table[index] ) {
            if ( pair[0] === key ) {
                return pair[1];
            }
        }
        
        return undefined;
    };
    
    print(){
        console.log(this.table);
        return;
    }
};

const table = new HashTable(5);
table.set("name", "sharon");
table.set("age", 20);
table.set("dis", "palakkad");
table.print()
console.log(table.get("age"))
