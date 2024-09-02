   <div id="api-container"></div>
    ```javascript
     //Using Promise
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
      //Using Async/Await
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
    ```
