# Development Log

## Project Setup

- `data.js` - project data
- `index.css` - global styles

## `List.js`

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

## `App.js`

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
