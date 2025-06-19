# MongoDB-Task-1
use company
db.createCollection("employees")

1. How do you insert a single document into a MongoDB collection?
db.employees.insertOne({empno: 101, ename:"Ravi", job:"clerk", sal: 450, comm:null, deptno:10, mgr: 7698, address:{city:"mumbai"}})

2. How do you insert multiple documents at once?
db.employees.insertMany([
 { empno: 102, ename: "Anjali", job: "analyst", sal: 1200, comm: null, deptno: 20, mgr: 7839, address: {city: "mumbai"}},
    { empno: 103, ename: "Suresh", job: "manager", sal: 2000, comm: 300, deptno: 30, mgr: 7839,
address: { city: "delhi" } },
    { empno: 104, ename: "Priya", job: "developer", sal: 800, comm: 150, deptno: 10, mgr: 7788, address: {
city: "bangalore"} },
    { empno: 105, ename: "Aman", job: "salesman", sal: 600, comm: 100, dentno: 20, mgr: 7788, address:
{city: "bangalore" } }
])
db.employees.insertMany([
    { empno: 106, ename: "Neha", job: "analyst", sal: 700, comm: 200, deptno: 20, mgr: 7902, address: {
city: "chennai"}},
    { empno: 107, ename: "Rakesh", job: "king", sal: 3000, comm: null, deptno: 40, mgr: null, address: {
city: "pune"} },
    { empno: 108, ename: "Divya", job: "clerk", sal: 500, comm: 100, deptno: 30, mgr: 7698, address: { city:
"mumbai"}},
    { empno: 109, ename: "Vikas", job: "developer", sal: 300, comm: null, deptno: 50, mgr: 7788 },
    { empno: 110, ename: "Kiran", job: "salesman", sal: 950, comm: 250, deptno: 60, mgr: 7839, address: {
city: "bangalore"} }
])

3. How do you find all documents in a collection?
db.employees.find()

4. How do you find documents where a field equals a specific value?
db.employees.find({mgr: 7839}) or
db.employees.find({mgr: {$eq: 7839}})

5. How do you find documents where a numeric field is greater than a value?
db.employees.find({comm: {$gt: 200}})

6. How do you find documents where a numeric field is less than a value?
db.employees.find({sal: {$lt: 2000}})

7. How do you find documents with multiple conditions (AND)?
db.employees.find({sal: {$gte: 2000}, job: {$nin: ["salesman", "developer"]}}) or
db.employees.find({ $and: [ {"address.city":"mumbai"}, {job:{$in: ["clerk", "analyst"]}} ]})
