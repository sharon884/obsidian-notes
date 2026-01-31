
What is Polymorphism?

**Poly = many**  
**Morph = forms**

 **Polymorphism means the same method behaves differently for different objects.**

One action → multiple behaviors.



Why do we need Polymorphism? 

Polymorphism helps us:

- Avoid big `if / else` blocks
    
- Write flexible code
    
- Add new features without changing old code
    
- Use inheritance properly
    

This is **core to scalable systems**.





Real-world analogy
### “Speak” example

- Human speaks → language
    
- Dog speaks → bark
    
- Cat speaks → meow
    

Same action: **speak()**  
Different behavior.

That is polymorphism.




Code example

### Parent class

`class Animal { 

speak() {     console.log("Animal makes a sound");   } 

}`

### Child classes

`class Dog extends Animal { 

speak() {     console.log("Dog barks");   }

}  

class Cat extends Animal { 

speak() {     console.log("Cat meows");   }

}`

---

### Using polymorphism

`function makeAnimalSpeak(animal: Animal) { 

animal.speak();

}  

makeAnimalSpeak(new Dog()); // Dog barks 

makeAnimalSpeak(new Cat()); // Cat meows`

👉 Same function  
👉 Same method call  
👉 Different output

That is **real polymorphism**.



## Key rule of Polymorphism 

> **Parent reference, child object**

`let animal: Animal;


animal = new Dog();
animal.speak(); // Dog barks  


animal = new Cat(); 
animal.speak();  // Cat meows`

This line explains polymorphism completely.

---

## Polymorphism vs If-Else (WHY it matters)

### ❌ Without polymorphism

`if (type === "dog") { 

bark();

} else if (type === "cat") {

meow(); 

}`

Problems:

- Hard to extend
    
- Must edit existing code
    
- Violates Open/Closed Principle
    

---

### With polymorphism

`animal.speak();`

Benefits:

- Clean
    
- Extendable
    
- No modification needed
    

---

## Types of Polymorphism 

You only need to know this much:

- **Runtime polymorphism** → Method overriding (MOST IMPORTANT)
    
- **Compile-time polymorphism** → Method overloading (conceptual)
    

---

##  Interview-ready one-liner

> “Polymorphism allows the same method to behave differently based on the object, enabling flexible and extensible code.”


