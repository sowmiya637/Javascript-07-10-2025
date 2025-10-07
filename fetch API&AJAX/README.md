# User Management Demo (Fetch & AJAX)

## Overview
This demonstrates how to use **Fetch API** and **XMLHttpRequest (XHR)** to interact with APIs without reloading the web page.  
You can **fetch a list of users** and **add a new user** using JSON data.

---

## Features

1. **Fetch Users (GET Request)**
   - **Fetch API** → Modern way to make HTTP requests using `async/await` and Promises.
   - **XMLHttpRequest** → Old way (classic AJAX) to fetch data from server.
   - Display list of users with **Name** and **Email** on the page.

2. **Add New User (POST Request)**
   - Add a new user with **Name** and **Email** using Fetch API.
   - Sends JSON data to the server with proper headers (`Content-Type: application/json`).
   - Shows an alert with the new user ID and details.
   - Refreshes the user list automatically after adding.


###  Fetch Users

- **Fetch API Example**
```javascript
async function fetchUsers() {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");
  const data = await response.json();
  displayUsers(data, "Fetch API");
}
XMLHttpRequest Example

function fetchUsersXHR() {
  const xhr = new XMLHttpRequest();
  xhr.open("GET", "https://jsonplaceholder.typicode.com/users", true);
  xhr.onload = function() {
    if(xhr.status === 200) {
      const data = JSON.parse(xhr.responseText);
      displayUsers(data, "XMLHttpRequest");
    }
  };
  xhr.send();
}

 Display Users

Function displayUsers(users, method) loops through the user array and creates a <div> for each user:

users.forEach(user => {
  const div = document.createElement("div");
  div.className = "user";
  div.innerHTML = `<b>${user.name}</b> - ${user.email}`;
  usersDiv.appendChild(div);
});

 Add User (POST Request)
async function addUser() {
  const name = document.getElementById("name").value;
  const email = document.getElementById("email").value;

  const response = await fetch("https://jsonplaceholder.typicode.com/users", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ name, email })
  });

  const data = await response.json();
  alert(`User added! ID: ${data.id}\nName: ${data.name}\nEmail: ${data.email}`);
  fetchUsers(); // refresh list
}
