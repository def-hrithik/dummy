web computing dec 24 
q2 A 
### 📧 Email Validation Script (JavaScript)

This script validates an email input field and displays an appropriate message for valid or invalid formats.

```html
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

























Q3 A
### ⚛️ Example: Using **State** and **Props** in React

This example demonstrates how **State** (for component’s internal data) and **Props** (for passing data between components) interact.

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





## Node.js Simple File Server Example

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

}
</script>




### 🧩 React Functional Component using **useState** and **useEffect**

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
          <li key={i}>
            {item} <button onClick={() => removeItem(i)}>X</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default ItemList;






# Node.js Streams — Efficient Read & Write Example

Simple, copy-paste-ready examples showing how to use Node.js **streams** to read, transform, and write data efficiently (no large buffers).

---

## 1) Copy a large file using streams (efficient pipeline)

```js
// copy-file.js
const fs = require('fs');
const { pipeline } = require('stream');
const source = 'large-input.txt';
const dest   = 'large-output.txt';

pipeline(
  fs.createReadStream(source),
  fs.createWriteStream(dest),
  (err) => {
    if (err) console.error('Pipeline failed:', err);
    else console.log('File copied successfully.');
  }
);

