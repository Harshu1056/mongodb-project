#IntermediateMango Database Query Results

## Dataset Info
- Database: students
- Collection: detail
- Total:  4 students
- Fields: _id, name, subjects, marks

##  Demonstrate How to Use  $Size Operator To Select Documents Whose Marks Array 
Has Three Elements: 

**Query:**
```javascript
db.detail.find({ marks: { $size: 3 } })

```

### Output:
```json
[
  {
    "_id": 1,
    "name": "Laksmi",
    "subjects": [
      "python"
    ],
    "marks": [
      75,
      80,
      90
    ]
  },
  {
    "_id": 4,
    "name": "Akash",
    "subjects": [
      "php"
    ],
    "marks": [
      70,
      80,
      90
    ]
  }
]
```
---

##  Demonstrate How to Use  $Where Operator To Find Array Size Greater Than 1

**Query:**
```javascript
db.detail.find({
  $where: "this.marks.length > 1"
})

```

### Output:
```json
[
  {
    "_id": 1,
    "name": "Laksmi",
    "subjects": [
      "python"
    ],
    "marks": [
      75,
      80,
      90
    ]
  },
  {
    "_id": 2,
    "name": "Shifa Banu",
    "subjects": [
      "c++",
      "java",
      "python"
    ],
    "marks": [
      95,
      80
    ]
  },
  {
    "_id": 4,
    "name": "Akash",
    "subjects": [
      "php"
    ],
    "marks": [
      70,
      80,
      90
    ]
  }
]
```
---