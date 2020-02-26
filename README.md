# Grampa Simpson

![](./img/Abe_Simpson.png)

🚀 A simple development server which mocks data for you.

## Examples

Let the next file be `mock-server.js`:

```js
import { Mock, server } from "grampa";

server.get('/users', () => {
  return new Array(5).fill(0).map({
    "first_name": Mock.name(),
    "second_name": Mock.name(),
    "birth": Mock.date(),
    "avatar": Mock.img({ w: 200, h: 200 })
  });
});
server.start();
```

Run it with Node.js:

```
$ node mock-server.js
  Server is running on http://127.0.0.1/
```

Make a request to get a list of users:

```
$ http http://127.0.0.1/users

[
  {
    "first_name": "Bret",
    "second_name": "Viktor",
    "date": "19/09/1965",
    "avatar": "http://127.0.0.1/img/200x200.jpg"
  },
  {
    "first_name": "Albert",
    "second_name": "Einstein",
    "date": "01/01/2011",
    "avatar": "http://127.0.0.1/img/200x200.jpg"
  },
  {
    "first_name": "David",
    "second_name": "Hilbert",
    "date": "12/07/1981",
    "avatar": "http://127.0.0.1/img/200x200.jpg"
  },
  {
    "first_name": "Alan",
    "second_name": "Turing",
    "date": "11/02/1989",
    "avatar": "http://127.0.0.1/img/200x200.jpg"
  },
  {
    "first_name": "Bjarne",
    "second_name": "Stroustrup",
    "date": "08/04/1973",
    "avatar": "http://127.0.0.1/img/200x200.jpg"
  }
]
```

💪 Profit!
