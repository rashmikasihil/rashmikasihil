- 👋 Hi, I’m @rashmikasihil
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
rashmikasihil/rashmikasihil is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
var sqlite3 = require('sqlite3').verbose()
var md5 = require('md5')

const DBSOURCE = "db.sqlite"


let db = new sqlite3.Database(DBSOURCE, (err) => {
    if (err) {
        // Cannot open database
        console.error(err.message)
        throw err
    } else {
        console.log('Connected to the SQlite database.')
        db.run(`CREATE TABLE customer (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            name text, 
            address text,
            email text,
            dateOfBirth text,
            gender text,
            age INTEGER,
            cardHolderName text,
            cardNumber INTEGER,
            expirytDate text,
            cvv INTEGER,
            timeStamp text,
            )`, (err) => {
            if (err) {
                // Table already created
            } else {
                // Table just created, creating some rows
                var insert = 'INSERT INTO products (name text, address text,email text,dateOfBirth text,gender text,age INTEGER,cardHolderName text,cardNumber INTEGER,expirytDate INTEGER,cvv INTEGER,timeStamp INTEGER) VALUES (?,?,?,?,?,?,?,?,?,?)'
                db.run(insert, ["A.D.Lakith", "No 324/A Ra De Mel Road, Colombo", "lakith@gmail.com", "1991.02.25", "female", 28, "A.D.L.Dharmasiri", , 102445217895,"12/2022",246,"2022-12-31 23:59:59"])
            }
        })

module.exports = db
