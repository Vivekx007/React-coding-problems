# React-coding-problem
## Create a functional component that displays data from https://reqres.in/api/users?

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
