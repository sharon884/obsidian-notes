Mongo Db

# Master MongoDB Concepts (Complete, Clean, Merged)

This document unifies **all MongoDB concepts** from your lists, DOCX files, missing topics, and professional interview requirements. Everything is organized, de-duplicated, and structured from basics → advanced.

---

# 1. **MongoDB Basics**

* What is MongoDB
* NoSQL vs SQL
* Relational vs Non-relational database
* Document-oriented database
* Schema-less design
* BSON vs JSON
* Why MongoDB uses BSON
* Why BSON is faster
* Size limit of one document
* Namespaces
* Type coercion in MongoDB
* Collections vs Documents
* ACID properties (in transactions)

---

# 2. **CRUD Operations**

* insertOne / insertMany
* updateOne / updateMany
* replaceOne
* deleteOne / deleteMany
* insert vs save()
* update vs updateOne
* upsert
* distinct
* Query operators

---

# 3. **Query Operators**

* Comparison operators: $eq, $ne, $gt, $gte, $lt, $lte
* Logical: $and, $or, $nor, $not
* Existential: $exists
* Array operators:

  * $in (true if any matches)
  * $all (true only if all required match)
  * $elemMatch
  * $size
* Regex queries
* $expr (compare fields in the same document)
* $nin vs $nor

---

# 4. **Aggregation Framework**

* Aggregation pipeline flow
* Stages:

  * $match
  * $group
  * $project
  * $sort
  * $limit
  * $skip
  * $lookup
  * $unwind
  * $set
  * $count
  * $sum
  * $avg
  * $min
  * $max
  * $push
  * $addToSet
  * $merge
  * $out
* Single-purpose aggregation
* $unwind (split array into documents)
* $lookup (joining collections)
* Join 2 collections
* MapReduce & splitting
* Accumulator operators

---

# 5. **Array Updates & Modifiers**

* $push → allows duplicates
* $addToSet → no duplicates
* $pop → first / last
* $pull → remove item by condition
* $mul → multiply a value
* $inc → increment
* $set

---

# 6. **Indexes**

* What is an index
* Types of indexing:

  * Single field index
  * Compound index
  * Multikey index
  * Text index
  * Hash index
  * TTL index
  * Sparse index
  * Unique index
* How to create index
* explain() for performance analysis
* Ad-Hoc queries
* Drawbacks of indexing
* Covered queries
* Indexing best practices
* Primary index, secondary index

---

# 7. **Advanced MongoDB Storage & Engine**

* Storage engines

  * WiredTiger
  * In-memory engine
* Journaling
* oplog
* Write concern
* Locks
* Disk I/O
* Capped collection
* isCapped()

---

# 8. **Data Modeling**

* Embedded vs Referenced data
* One-to-one
* One-to-many
* Many-to-many
* Normalization drawbacks
* Views
* Materialized views
* Schema design patterns

---

# 9. **Backup, Restore, & Utilities**

* mongodump
* mongorestore
* Utility commands
* Backup strategies
* Restore strategies

---

# 10. **Sharding (Horizontal Scaling)**

* Why sharding is needed
* Sharded cluster components:

  * Config servers
  * Query router (mongos)
  * Shards
* Shard key
* Chunk splitting & migration
* Types of scaling
* CAP theorem
* How MongoDB solves CAP

---

# 11. **Replication**

* Replica set
* Primary, secondary, arbiter
* Failover process
* oplog replication
* Read preference
* Write concern
* Multi-document consistency
* Replication use cases

---

# 12. **Transactions**

* Multi-document transactions
* ACID in MongoDB
* Commit & Abort
* Transaction use cases

---

# 13. **GridFS**

* Why GridFS is used
* How GridFS stores large files
* chunks collection
* files collection
* Streaming large files
* GridFS advantages

---

# 14. **Bulk Operations**

* bulkWrite
* $inc
* $set
* Upserts in bulk
* Atomicity in bulk operations

---

# 15. **Performance Optimization**

* Query patterns
* Covered queries
* Use of projection
* Avoiding large arrays
* Avoiding too many indexes
* Sharding for scaling
* Replication for read scaling

---

# 16. **Explain & Profiling**

* explain()
* Query planner
* Execution statistics
* Profiling slow queries

---

# 17. **Miscellaneous Concepts**

* MinKey & MaxKey
* Namespace structure
* BSON internal types
* $exists behavior
* Type coercion rules
* Alias fields in aggregation
* Pipeline optimization
* How MongoDB handles ACID internally

---

End of document.
