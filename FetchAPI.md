<h2>Using Promise </h2>

```javascript
    <div id="api-container"></div>
    <script>
      const fetchData = () => {
        let apiLink = "https://jsonplaceholder.typicode.com/users";
        fetch(apiLink)
          .then((response) => response.json())
          .then((data) => {
            const userName = data.map((user) => user.name);
            console.log(userName);
            document.getElementById(
              "api-container"
            ).innerHTML = `<p>UserName: ${userName}</p>`;
          })
          .catch((error) => {
            console.error("Error fetching data ", error);
          });
      };
      window.onload = fetchData;
    </script>
```
<h2>Using Async/Await </h2>

```javascript
    <div id="api-container"></div>
    <script>
      const fetchingData = async () => {
        try {
          let apiLink = "https://jsonplaceholder.typicode.com/users";
          const response = await fetch(apiLink);
          const data = await response.json();

          const names = data.map((user) => user.name);
          console.log(names);

          document.getElementById(
            "api-container"
          ).innerHTML = `<p>UserName: ${names}</p>`;
        } catch (error) {
          console.error("Error Fetching Data : ", error);
        }
      };
      window.onload = fetchingData;
    <script>
```
