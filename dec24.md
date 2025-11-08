# Web Computing Dec 24 - Code Reference Guide

Complete collection of examples covering JavaScript validation, React components, and Node.js server implementations.

---

## 📧 Frontend Code

### Email Validation Script (JavaScript)

This script validates an email input field and displays an appropriate message for valid or invalid formats.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Email Validation</title>
</head>
<body>
  <input type="email" id="email" placeholder="Enter your email">
  <button onclick="validateEmail()">Validate</button>
  <p id="msg"></p>

  <script>
    function validateEmail() {
      const emailInput = document.getElementById("email");
      const message = document.getElementById("msg");
      const email = emailInput.value.trim();

      // Regular expression for basic email validation
      const emailPattern = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;

      if (email === "") {
        message.textContent = "Email field cannot be empty.";
        message.style.color = "red";
        emailInput.focus();
        return false;
      } 
      else if (!emailPattern.test(email)) {
        message.textContent = "Please enter a valid email address (e.g., user@example.com).";
        message.style.color = "red";
        emailInput.focus();
        return false;
      } 
      else {
        message.textContent = "Email format is valid!";
        message.style.color = "green";
        return true;
      }
    }
  </script>
</body>
</html>
```

---

## ⚛️ React Components

### Example 1: State and Props Interaction

This example demonstrates how **State** (for component's internal data) and **Props** (for passing data between components) interact.

```jsx
import React, { useState } from "react";

// Child component receives data via props
function ChildComponent({ message }) {
  return <h3>Message from Parent: {message}</h3>;
}

// Parent component manages state and passes it as a prop
function ParentComponent() {
  const [text, setText] = useState("Hello from Parent!");

  return (
    <div>
      <h2>React State and Props Example</h2>
      <ChildComponent message={text} />
      <button onClick={() => setText("Message Updated!")}>Update Message</button>
    </div>
  );
}

export default ParentComponent;
```

---

### Example 2: Item List with useState and useEffect Hooks

This example demonstrates how to create a simple item list in React where users can **add** and **remove** items using **Hooks** (`useState` and `useEffect`).

```jsx
import React, { useState, useEffect } from "react";

function ItemList() {
  const [items, setItems] = useState([]);
  const [input, setInput] = useState("");

  // This effect runs every time the 'items' state changes
  useEffect(() => {
    console.log("Items updated:", items);
  }, [items]);

  const addItem = () => {
    if (input.trim()) {
      setItems([...items, input.trim()]);
    }
    setInput(""); // Clear input after adding
  };

  const removeItem = (indexToRemove) => {
    // Filter out the item at the specified index
    setItems(items.filter((_, idx) => idx !== indexToRemove));
  };

  return (
    <div>
      <h3>Item List</h3>
      <input
        value={input}
        onChange={(e) => setInput(e.target.value)}
        placeholder="Add item"
      />
      <button onClick={addItem}>Add</button>
      <ul>
        {items.map((item, i) => (
          <li key={i}> {item} <button onClick={() => removeItem(i)}>X</button></li>
        ))}
      </ul>
    </div>
  );
}

export default ItemList;
```

---

## 🚀 Backend Code (Node.js)

### Example 1: Simple File Server

This code creates a basic HTTP server using Node.js. When a request is received, it reads the content of a file named `data.txt` and sends its contents as the response.

```javascript
// Import required modules
const http = require("http");
const fs = require("fs");
const PORT = 3000;

// Create server
const server = http.createServer((req, res) => {
  fs.readFile("data.txt", "utf8", (err, data) => {
    if (err) {
      res.writeHead(500, { "Content-Type": "text/plain" });
      res.end("Error reading file");
    } else {
      res.writeHead(200, { "Content-Type": "text/plain" });
      res.end(data);
    }
  });
});

// Start server
server.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}`);
});
```

**Requirements:**
- Create a `data.txt` file in the same directory with sample content
- Run with: `node file-server.js`

---

### Example 2: Streams - Efficient File Copy

Simple, copy-paste-ready example showing how to use Node.js **streams** to read and write data efficiently (no large buffers needed).

```javascript
// Copy a large file using streams (efficient pipeline)
const fs = require('fs');
const { pipeline } = require('stream');

const source = 'large-input.txt';
const dest   = 'large-output.txt';

pipeline(
  fs.createReadStream(source),
  fs.createWriteStream(dest),
  (err) => {
    if (err) {
      console.error('Pipeline failed:', err);
    } else {
      console.log('File copied successfully.');
    }
  }
);
```

**Benefits of using streams:**
- Memory efficient - processes data in chunks
- Handles large files without loading entire file into memory
- Built-in error handling with pipeline
- Better performance for I/O operations

**Usage:**
```bash
# Create a sample large file
echo "Sample content for testing streams" > large-input.txt

# Run the script
node copy-file.js
```

---

## 📋 Summary of Examples

| Example | Technology | Purpose |
|---------|-----------|---------|
| Email Validation | JavaScript (Vanilla) | Form validation with regex |
| State & Props | React | Component communication |
| Item List | React (Hooks) | State management with useEffect |
| File Server | Node.js | HTTP server with file reading |
| Stream Copy | Node.js | Efficient file operations |

---

## 🎯 Question Reference

- **Q2 A**: Email Validation Script
- **Q3 A**: React State and Props Example
- **Additional**: Node.js Server Examples and Streams

---

## 📝 Notes

- All code snippets are production-ready and can be copied directly
- React examples use modern functional components with Hooks
- Node.js examples follow best practices for error handling
- Email regex pattern covers most common email formats

---

**Last Updated:** 2025-11-08 08:07:04  
**Course:** Web Computing