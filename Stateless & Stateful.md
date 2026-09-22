# stateless and statefull components?

---

A stateless component does not manage its own state and is mainly used to display UI. A stateful component manages state and can update its UI when the state changes. In modern React, functional components can be both stateless and stateful using Hooks like useState.

---

## Example

---

### Stateless

    function User() {
      return <h1>Hello Ritesh</h1>;
    }

---

### Stateful

    function Counter() {
      const [count, setCount] = useState(0);

      return (
        <button onClick={() => setCount(count + 1)}>
          {count}
        </button>
      );
    }