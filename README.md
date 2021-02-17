1. Frontend:
  a. Creating a component in React
    Within App or render, write a regular html tag.
  b. Initializing state
    this.state = {} inside teh constructor.
  c. Passing state as props
    You can write props inside a new html tag as any parameter: <div onClick={this.onClick}> will give the new tag a props.onClick property.
  d. How to handle user click events
    You can give the tag a onClick property that directs to a click function.
  e. Perform AJAX requests to the server
    With jQuery: $.get(url, callback) for get and post. Other methods: 
    $.ajax({
      type: type,
      url: url,
      success: what to do on success,
      etc: etc
    });
2. Server:
  a. How to use module.export / require
    Call module.exports = {} with functions to export at the bottom of the script, then at the top of the script where you'd like to use it call const nameToGiveImportedItem(s) = require("addressOfExportedItem(s)";
  b. How to create restful routes
    app.get("url", callback) or app.post, app.delete etc.
  c. Use callbacks in database helper functions
    Error first like:
    function (err, result) {
      if (err) {
        cb(err, null) log or throw error
      } else {
        cb(null, result) run callback on result
      }
    }
3. Database:
  a. How to setup configuration to connect ExpressJS server to MySQL DB
    In sql file:
    DROP DATABASE IF EXISTS database;
    CREATE DATABASE database;
    USE database;
    CREATE TABLE IF NOT EXISTS table (
      id integer AUTO_INCREMENT UNIQUE PRIMARY KEY,
      column varchar(255),
      column varchar(255),
      column varchar(255)
    );
    In example, id auto increments and columns have varchar to symbolize they are a string but other options are available.
  b. How to use MySQLjs to make SQL queries to your MySQL DB
    connection.query(`DELETE FROM table WHERE id = someid`, callback function
    In this example we delete an entry
  c. What should go in to the callback function of the query
    Error first like:
    function (err, result) {
      if (err) {
        cb(err, null) log or throw error
      } else {
        cb(null, result) run callback on result
      }
    }