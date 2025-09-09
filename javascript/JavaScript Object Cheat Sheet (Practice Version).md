

// Sample object
let student = {
  name: "Arjun",
  age: 20,
  grade: "A"
};


<h2>1️⃣ Accessing keys & values,</h2>


// Keys

for (let key in student) console.log(key); 

// or

console.log(Object.keys(student)); 

// Values
for (let key in student) console.log(student[key]); 

// or

console.log(Object.values(student));

// Key-Value pairs

for (let key in student) console.log(key, ":", student[key]);

// or

console.log(Object.entries(student));


<h2>2️⃣ Adding / Updating / Deleting properties</h2>

// Add property

student.city = "Palakkad";        // dot notation

student["pincode"] = 678001;      // bracket notation

// Update property

student.grade = "B";               // dot notation

student["grade"] = "B";            // bracket notation

// Delete property
delete student.age;


<h2>3️⃣ Counting properties</h2>

// Count keys manually
let count = 0;
for (let key in student) count++;
console.log(count);

// Check if object is empty
let isEmpty = true;
for (let key in student) { isEmpty = false; break; }
console.log(isEmpty); // true if empty

<h2>4️⃣ Checking for a property</h2>


// Manual
for (let key in student) {
  if (key === "grade") console.log("Exists");
}

// Built-in
console.log(Object.hasOwn(student, "grade"));
console.log(Object.keys(student).includes("grade"));


<h2>5️⃣ Finding max/min values</h2>

let marks = { math: 90, science: 85, english: 88 };

// Max
let maxVal = -Infinity, maxKey = "";
for (let key in marks) {
  if (marks[key] > maxVal) {
    maxVal = marks[key];
    maxKey = key;
  }
}
console.log(maxKey, ":", maxVal);

// Max & Min in one loop
let minVal = Infinity, minKey = "";
for (let key in marks) {
  if (marks[key] > maxVal) { maxVal = marks[key]; maxKey = key; }
  if (marks[key] < minVal) { minVal = marks[key]; minKey = key; }
}
console.log(`Max: ${maxKey} : ${maxVal} | Min: ${minKey} : ${minVal}`);

<h2>6️⃣ Merging objects</h2>


let obj1 = { a: 1, b: 2 };
let obj2 = { b: 3, c: 4 };

// 1. Spread operator
let merged = { ...obj1, ...obj2 };  // { a:1, b:3, c:4 }

// 2. Object.assign
Object.assign(obj1, obj2);          // obj1 modified: { a:1, b:3, c:4 }

// 3. Manual loop
for (let key in obj2) obj1[key] = obj2[key];
✅ Key point: If a key exists in both objects, the later value overwrites the previous one.

<h2>7️⃣ Converting object to array</h2>

// Key-value pairs
let arr = [];
for (let key in student) arr.push([key, student[key]]);
console.log(arr);

// Or using built-in
console.log(Object.entries(student));

<h2>8️⃣ Type checking in objects</h2>

js
Copy code
// Count string values
let count = 0;
for (let key in student) {
  if (typeof student[key] === "string") count++;
}
console.log(count);
✅ Tips & Notes
for…in loop → iterate over keys

Object.keys() → array of keys

Object.values() → array of values

Object.entries() → array of [key, value] pairs

Spread vs Object.assign → spread creates a new object, Object.assign can mutate existing

Overwriting keys → if a key exists in multiple objects, the last assignment wins


