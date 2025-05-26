# BasicMango Database Query Results

## Dataset Info
- Database: student
- Collection: details
- Total: 5 students
- Fields: _id, name, course, batch_year, dob, language,personal_details

## Simple Fetch with Nested Documents, Display Only Name, Personal_Details.Phone_No

**Query:**
```javascript
db.details.find({}, { name: 1, "personal_details.phone_no": 1, _id: 0 })
```

### Output:
```json
[
  {
    "name": "Anand Mishra",
    "personal_details": {
      "phone_no": 8895321456
    }
  },
  {
    "name": "Zoya Akram",
    "personal_details": {
      "phone_no": 9874563698
    }
  },
  {
    "name": "Mahadevaswamy",
    "personal_details": {
      "phone_no": 7845123698
    }
  },
  {
    "name": "Priya Sawant",
    "personal_details": {
      "phone_no": 9997845123
    }
  },
  {
    "name": "Ramya Gowda",
    "personal_details": {
      "phone_no": 6312547896
    }
  },
  {
    "name": "Laksmi"
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "phone_no": 8895321456
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "phone_no": 8895321456
    }
  }
]
```

---

##  Simple Fetch Involving Nested Documents And Sort Name Asc 

### Query:
```javascript
db.details.find({}, { name: 1,"personal_details": 1,   _id: 0 }).sort({ name: 1 })
```

### Output:
```json
[
  {
    "name": "Anand Mishra",
    "personal_details": {
      "Father_name": "Deepak Mishra",
      "phone_no": 8895321456,
      "age": 23,
      "gender": "Male",
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "Father_name": "Deepak Mishra",
      "phone_no": 8895321456,
      "age": 23,
      "gender": "Male",
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "Father_name": "Deepak Mishra",
      "phone_no": 8895321456,
      "age": 23,
      "gender": "Male",
      "City": "Lucknow"
    }
  },
  {
    "name": "Laksmi"
  },
  {
    "name": "Mahadevaswamy",
    "personal_details": {
      "Father_name": "Nanjudaswamy",
      "phone_no": 7845123698,
      "age": 24,
      "gender": "Male",
      "City": "Bangalore"
    }
  },
  {
    "name": "Priya Sawant",
    "personal_details": {
      "Father_name": "Ashok Sawant",
      "phone_no": 9997845123,
      "age": 25,
      "gender": "Female",
      "City": "Mumbai"
    }
  },
  {
    "name": "Ramya Gowda",
    "personal_details": {
      "Father_name": "Arjun Gowda",
      "phone_no": 6312547896,
      "age": 22,
      "gender": "Female",
      "City": "Bangalore"
    }
  },
  {
    "name": "Zoya Akram",
    "personal_details": {
      "Father_name": "Ahmed Javed",
      "phone_no": 9874563698,
      "age": 20,
      "gender": "Female",
      "City": "Hyderabad"
    }
  }
]
```


---

##   Simple Fetch Involving Nested Documents and Sort Name Desc

### Query:
```javascript
db.details.find({}, { name: 1,"personal_details.phone_no": 1,   _id: 0 }).sort({ name: -1})
```

### Output:
```json
[
  {
    "name": "Zoya Akram",
    "personal_details": {
      "phone_no": 9874563698
    }
  },
  {
    "name": "Ramya Gowda",
    "personal_details": {
      "phone_no": 6312547896
    }
  },
  {
    "name": "Priya Sawant",
    "personal_details": {
      "phone_no": 9997845123
    }
  },
  {
    "name": "Mahadevaswamy",
    "personal_details": {
      "phone_no": 7845123698
    }
  },
  {
    "name": "Laksmi"
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "phone_no": 8895321456
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "phone_no": 8895321456
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "phone_no": 8895321456
    }
  }
]
```

---

##   Simple Fetch Involving Nested Documents and Sort Course Asc 

### Query:
```javascript
db.details.find({}, { name: 1, "Course": 1, _id: 0 }).sort({ "Course": 1 })
```

### Output:
```json
[
  {
    "name": "Laksmi"
  },
  {
    "name": "Zoya Akram",
    "Course": "BCA"
  },
  {
    "name": "Anand Mishra",
    "Course": "Btech"
  },
  {
    "name": "Ramya Gowda",
    "Course": "Btech"
  },
  {
    "name": "Anand Mishra",
    "Course": "Btech"
  },
  {
    "name": "Anand Mishra",
    "Course": "Btech"
  },
  {
    "name": "Mahadevaswamy",
    "Course": "MCA"
  },
  {
    "name": "Priya Sawant",
    "Course": "MTech"
  }
]
```

---

##    Simple Fetch Involving Nested Documents And Sort dob  Acs

### Query:
```javascript
db.details.find({}, { name: 1, "dob": 1, _id: 0 }).sort({ "dob": 1 })

```

### Output:
```json
[
  {
    "name": "Laksmi"
  },
  {
    "name": "Zoya Akram",
    "dob": {
      "$date": "2002-11-14T00:00:00Z"
    }
  },
  {
    "name": "Mahadevaswamy",
    "dob": {
      "$date": "2004-05-24T00:00:00Z"
    }
  },
  {
    "name": "Priya Sawant",
    "dob": {
      "$date": "2006-07-30T00:00:00Z"
    }
  },
  {
    "name": "Ramya Gowda",
    "dob": {
      "$date": "2008-08-16T00:00:00Z"
    }
  },
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    }
  },
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    }
  },
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    }
  }
]
```

---
##  Simple Fetch Involving Nested Documents And Sort Dob  Desc

### Query:
```javascript
db.details.find({}, { name: 1, "dob": 1, _id: 0 }).sort({ "dob": -1 })

```

### Output:
```json
[
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    }
  },
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    }
  },
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    }
  },
  {
    "name": "Ramya Gowda",
    "dob": {
      "$date": "2008-08-16T00:00:00Z"
    }
  },
  {
    "name": "Priya Sawant",
    "dob": {
      "$date": "2006-07-30T00:00:00Z"
    }
  },
  {
    "name": "Mahadevaswamy",
    "dob": {
      "$date": "2004-05-24T00:00:00Z"
    }
  },
  {
    "name": "Zoya Akram",
    "dob": {
      "$date": "2002-11-14T00:00:00Z"
    }
  },
  {
    "name": "Laksmi"
  }
]
```

---
##    Simple Fetch Involving Nested Documents And Sort City  Desc 

### Query:
```javascript
db.details.find({}, { name: 1,"personal_details.City": 1,   _id: 0 }).sort({"personal_details.City": -1 })

```

### Output:
```json
[
  {
    "name": "Priya Sawant",
    "personal_details": {
      "City": "Mumbai"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "City": "Lucknow"
    }
  },
  {
    "name": "Zoya Akram",
    "personal_details": {
      "City": "Hyderabad"
    }
  },
  {
    "name": "Mahadevaswamy",
    "personal_details": {
      "City": "Bangalore"
    }
  },
  {
    "name": "Ramya Gowda",
    "personal_details": {
      "City": "Bangalore"
    }
  },
  {
    "name": "Laksmi"
  }
]
```

---
##   Simple Fetch Involving Nested Documents and Use Limit Operator

### Query:
```javascript
db.details.find({}, { name: 1, "personal_details": 1, _id: 0 }).limit(3)

```

### Output:
```json
[
  {
    "name": "Anand Mishra",
    "personal_details": {
      "Father_name": "Deepak Mishra",
      "phone_no": 8895321456,
      "age": 23,
      "gender": "Male",
      "City": "Lucknow"
    }
  },
  {
    "name": "Zoya Akram",
    "personal_details": {
      "Father_name": "Ahmed Javed",
      "phone_no": 9874563698,
      "age": 20,
      "gender": "Female",
      "City": "Hyderabad"
    }
  },
  {
    "name": "Mahadevaswamy",
    "personal_details": {
      "Father_name": "Nanjudaswamy",
      "phone_no": 7845123698,
      "age": 24,
      "gender": "Male",
      "City": "Bangalore"
    }
  }
]
```

---
##  Demonstrate How To Use Skip Operator In MongoDB

### Query:
```javascript
db.details.find({}, { name: 1, "personal_details": 1, _id: 0 }).skip(2)

```

### Output:
```json
[
  {
    "name": "Mahadevaswamy",
    "personal_details": {
      "Father_name": "Nanjudaswamy",
      "phone_no": 7845123698,
      "age": 24,
      "gender": "Male",
      "City": "Bangalore"
    }
  },
  {
    "name": "Priya Sawant",
    "personal_details": {
      "Father_name": "Ashok Sawant",
      "phone_no": 9997845123,
      "age": 25,
      "gender": "Female",
      "City": "Mumbai"
    }
  },
  {
    "name": "Ramya Gowda",
    "personal_details": {
      "Father_name": "Arjun Gowda",
      "phone_no": 6312547896,
      "age": 22,
      "gender": "Female",
      "City": "Bangalore"
    }
  },
  {
    "name": "Laksmi"
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "Father_name": "Deepak Mishra",
      "phone_no": 8895321456,
      "age": 23,
      "gender": "Male",
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "Father_name": "Deepak Mishra",
      "phone_no": 8895321456,
      "age": 23,
      "gender": "Male",
      "City": "Lucknow"
    }
  }
]
```

---
##  Demonstrate How to Use In Operator And Sort By Dob Asc

### Query:
```javascript
db.details.find(
  { "personal_details.City": { $in: ["Lucknow", "Mumbai", "Hyderabad"] } }, 
  { name: 1,"personal_details.City":1, "dob": 1, _id: 0 }
).sort({ "dob": 1 })

```

### Output:
```json
[
  {
    "name": "Zoya Akram",
    "dob": {
      "$date": "2002-11-14T00:00:00Z"
    },
    "personal_details": {
      "City": "Hyderabad"
    }
  },
  {
    "name": "Priya Sawant",
    "dob": {
      "$date": "2006-07-30T00:00:00Z"
    },
    "personal_details": {
      "City": "Mumbai"
    }
  },
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    },
    "personal_details": {
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    },
    "personal_details": {
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "dob": {
      "$date": "2008-12-04T00:00:00Z"
    },
    "personal_details": {
      "City": "Lucknow"
    }
  }
]
```
---
##  Demonstrate How to Use In Operator And Sort By Age Desc

### Query:
```javascript
db.details.find(
  { "personal_details.City": { $in: ["Lucknow", "Mumbai", "Hyderabad"] } }, 
  { name: 1,"personal_details.City":1, "personal_details.age": 1, _id: 0 }
).sort({ "personal_details.age": -1 })

```

### Output:
```json
[
  {
    "name": "Priya Sawant",
    "personal_details": {
      "age": 25,
      "City": "Mumbai"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "age": 23,
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "age": 23,
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "personal_details": {
      "age": 23,
      "City": "Lucknow"
    }
  },
  {
    "name": "Zoya Akram",
    "personal_details": {
      "age": 20,
      "City": "Hyderabad"
    }
  }
]
```
---
##  Demonstrate How to Use In Operator And Sort By Sort Batch_Year Desc 

### Query:
```javascript
db.details.find(
  { "personal_details.City": { $in: ["Lucknow", "Mumbai", "Hyderabad"] } }, 
  { name: 1,"personal_details.City":1, "batch_year": 1, _id: 0 }
).sort({ "batch_year": -1 })

```
### Output:
```json
[
  {
    "name": "Zoya Akram",
    "batch_year": 2020,
    "personal_details": {
      "City": "Hyderabad"
    }
  },
  {
    "name": "Anand Mishra",
    "batch_year": 2018,
    "personal_details": {
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "batch_year": 2018,
    "personal_details": {
      "City": "Lucknow"
    }
  },
  {
    "name": "Anand Mishra",
    "batch_year": 2018,
    "personal_details": {
      "City": "Lucknow"
    }
  },
  {
    "name": "Priya Sawant",
    "batch_year": 2017,
    "personal_details": {
      "City": "Mumbai"
    }
  }
]
```
---


