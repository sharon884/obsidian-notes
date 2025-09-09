
| Operation            | Method / Syntax                                                           |
| -------------------- | ------------------------------------------------------------------------- |
| Access key           | `obj.key` / `obj["key"]`                                                  |
| Add key              | `obj.newKey = value` / `obj["newKey"]`                                    |
| Update key           | same as add                                                               |
| Delete key           | `delete obj.key`                                                          |
| Iterate keys         | `for (let key in obj)`                                                    |
| Iterate values       | `obj[key]` / `Object.values(obj)`                                         |
| Iterate key-value    | `for (let key in obj) console.log(key, obj[key])` / `Object.entries(obj)` |
| Count keys           | manual loop with counter                                                  |
| Check empty          | assume true → for loop → false if key found                               |
| Merge objects        | `...` spread / `Object.assign()` / manual loop                            |
| Overwrite behavior   | last assignment wins if key exists                                        |
| Find max / min value | loop through keys, compare values                                         |
| Object → Array       | `arr.push([key, obj[key]])`                                               |




                  ┌─────────────────────┐
                  │     OBJECT          │
                  │ { key: value }      │
                  └────────┬────────────┘
                           │
      ┌────────────────────┼─────────────────────┐
      │                    │                     │
      ▼                    ▼                     ▼
 ┌────────────┐     ┌─────────────┐       ┌─────────────┐
 │ ACCESS     │     │ MODIFY      │       │ ITERATE     │
 └────────────┘     └─────────────┘       └─────────────┘
      │                    │                     │
      │                    │                     │
 ┌────────────┐     ┌─────────────┐       ┌─────────────┐
 │ Keys       │     │ Add Key     │       │ for...in    │
 │ student.name│     │ student.city="X" │   │ Object.keys()│
 │ student[key]│     │ student["pincode"]=123 │ Object.values()│
 └────────────┘     │ Update Key  │       │ Object.entries()│
                    │ student.grade="B" │ └─────────────┘
                    │ Delete Key  │
                    │ delete student.age │
                    └─────────────┘
                           
      ┌─────────────────────────────┐
      │ COUNT / CHECK / TYPES       │
      └─────────────┬──────────────┘
                    │
      ┌─────────────┼─────────────────┐
      │             │                 │
      ▼             ▼                 ▼
 ┌───────────┐ ┌─────────────┐ ┌─────────────┐
 │ Count keys│ │ Check empty │ │ Type check  │
 │ count=0   │ │ isEmpty=true│ │ typeof student[key] │
 │ for key…  │ │ for key…    │ │ e.g. string, number │
 └───────────┘ └─────────────┘ └─────────────┘

      ┌─────────────────────────────┐
      │ MERGING / OVERWRITE          │
      └─────────────┬──────────────┘
                    │
          ┌─────────┼───────────┐
          ▼         ▼           ▼
    ┌─────────┐ ┌─────────────┐ ┌────────────┐
    │ Spread  │ │ Object.assign│ │ Manual     │
    │ {...a,...b}│ │ Object.assign(a,b) │ │ for key in b { a[key]=b[key] } │
    └─────────┘ └─────────────┘ └────────────┘
          │ Overwrites same keys │
          │ Last wins            │

      ┌─────────────────────────────┐
      │ FIND MAX / MIN               │
      └─────────────┬──────────────┘
                    │
      ┌─────────────┼─────────────┐
      ▼             ▼             ▼
 ┌────────────┐ ┌─────────────┐ ┌─────────────┐
 │ Max value  │ │ Min value   │ │ Both in 1 loop │
 │ max=-∞     │ │ min=∞       │ │ if val>max → max=val │
 │ for key in │ │ for key…    │ │ if val<min → min=val │
 └────────────┘ └─────────────┘ └─────────────┘

      ┌─────────────────────────────┐
      │ OBJECT → ARRAY               │
      └─────────────┬──────────────┘
                    │
      ┌─────────────┼──────────────┐
      ▼             ▼
 ┌─────────────┐ ┌─────────────┐
 │ Key-Value Pairs │ │ Values Only │
 │ arr.push([k,v]) │ │ arr.push(obj[k])│
 └─────────────┘ └─────────────┘
