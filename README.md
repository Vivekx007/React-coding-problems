# React-coding-problem
## Q1. Create a functional component that displays data from https://reqres.in/api/users?

```js
import React, { useState, useEffect } from "react";
import axios from "axios";
const DataApi = () => {
  const [usersData, setUsersData] = useState([]);

  useEffect(() => {
    axios.get("https://reqres.in/api/users").then((response) => {
      setUsersData(response.data.data);
    });
  }, []);

  return (
    <div className="dataApi">
      <ul>
        {usersData.map((userData) => (
          <li key={userData.id}>
            <img
              src={userData.avatar}
              alt="userImage"
              // height="350px"
              // width="350px"
            />
            <br />
            FirstName : {userData.first_name}
            <br />
            LastName : {userData.last_name}
            <br />
            Email : {userData.email}
            <br />
            <br />
          </li>
        ))}
      </ul>
    </div>
  );
};

export default DataApi;
```

## Q2. Write a program to display searched keyword in React?

```React
import React, { useState } from "react";
const SearchedKey = () => {
  const [search, setSearch] = useState("");
  const [text, setText] = useState();
  const handleClick = (e) => {
    e.preventDefault();
    setText(search);
  };
  return (
    <>
      <div>
        <form onSubmit={handleClick}>
          <input
            type="text"
            value={search}
            placeholder="Write some text..."
            onChange={(e) => setSearch(e.target.value)}
          />
          <button type="submit">Show Text</button>
        </form>
      </div>
      <div>
        <h3>Searched Key : {text}</h3>
      </div>
    </>
  );
};
```
