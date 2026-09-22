# Controlled and Uncontrolled Components

---

A controlled component is a form input whose value is controlled by React state. An uncontrolled component is a form input whose value is managed by the DOM, and we access it using a ref. Controlled components are commonly used when we need validation or real-time control over form data.

## Controlled Component

    import { useState } from "react";

    function Login() {

      const [email, setEmail] = useState("");

      return (

        <input
          value={email}
          onChange={(e) => setEmail(e.target.value)}
        />

      );

    }

## Uncontrolled Component

    import { useRef } from "react";

    function Login() {

      const emailRef = useRef();

      const handleSubmit = () => {

        console.log(emailRef.current.value);

      };

      return (

        <>
          <input ref={emailRef} />

          <button onClick={handleSubmit}>
            Submit
          </button>
        </>

      );

    }