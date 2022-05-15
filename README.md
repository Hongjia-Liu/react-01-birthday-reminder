# Birthday Reminder

A practice React project bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

## Development Log

### Project Setup

- `data.js` - project data
- `index.css` - global styles

### `List.js`

```jsx
const List = ({ people }) => {
  return (
    <>
      {people.map((person) => {
        return (
          <article key={person.id} className="person">
            <img src={person.image} alt={person.name} />
            <div>
              <h4>{person.name}</h4>
              <p>{person.age} years</p>
            </div>
          </article>
        );
      })}
    </>
  );
};
export default List;
```

### `App.js`

```jsx
import { useState } from "react";
import data from "./data";
import List from "./List";

function App() {
  const [people, setPeople] = useState(data);

  return (
    <main>
      <section className="container">
        <h3>{people.length} birthdays today</h3>
        <List people={people} />
        <button
          onClick={() => {
            setPeople([]);
          }}
        >
          Clear All
        </button>
      </section>
    </main>
  );
}

export default App;
```
