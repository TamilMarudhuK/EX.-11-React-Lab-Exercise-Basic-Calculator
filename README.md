# EX.-11-React-Lab-Exercise-Basic-Calculator
## Name: TAMIL MARUDHU K
## Roll no: 2305001033
## Department: CSE

## AIM

To develop a basic calculator using React that performs addition, subtraction, multiplication, and division using the useState hook, event handling, and conditional statements.

## PROGRAM

### i) App.jsx
```jsx
import { useState } from "react";
import "./App.css";

function App() {
  const [num1, setNum1] = useState("");
  const [num2, setNum2] = useState("");
  const [operator, setOperator] = useState("+");
  const [result, setResult] = useState("");

  const calculate = () => {
    if (num1.trim() === "" || num2.trim() === "") {
      setResult("Please enter both numbers");
      return;
    }

    const a = Number(num1);
    const b = Number(num2);

    let answer;

    if (operator === "+") {
      answer = a + b;
    } else if (operator === "-") {
      answer = a - b;
    } else if (operator === "*") {
      answer = a * b;
    } else if (operator === "/") {
      answer = b !== 0 ? a / b : "Cannot divide by zero";
    }

    setResult(answer);
  };

  const clearCalculator = () => {
    setNum1("");
    setNum2("");
    setOperator("+");
    setResult("");
  };

  return (
    <div className="calculator">
      <h1>Basic Calculator</h1>

      <label>First Number</label>
      <input
        type="number"
        step="any"
        value={num1}
        onChange={(e) => setNum1(e.target.value)}
        placeholder="Enter first number"
      />

      <label>Operator</label>
      <select
        value={operator}
        onChange={(e) => setOperator(e.target.value)}
      >
        <option value="+">Addition (+)</option>
        <option value="-">Subtraction (-)</option>
        <option value="*">Multiplication (*)</option>
        <option value="/">Division (/)</option>
      </select>

      <label>Second Number</label>
      <input
        type="number"
        step="any"
        value={num2}
        onChange={(e) => setNum2(e.target.value)}
        placeholder="Enter second number"
      />

      <button onClick={calculate}>Calculate</button>

      <button className="clear" onClick={clearCalculator}>
        Clear
      </button>

      <h2>Result: {result}</h2>
    </div>
  );
}

export default App;
```

### ii) App.css
```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #eef2f7;
}

.calculator {
  max-width: 350px;
  margin: 50px auto;
  padding: 25px;
  background-color: white;
  border-radius: 12px;
  box-shadow: 0 4px 15px #0000001a;
}

h1 {
  text-align: center;
  color: #1976d2;
  font-size: 26px;
}

label {
  display: block;
  margin-top: 15px;
  margin-bottom: 6px;
  font-weight: bold;
  color: #333;
}

input, select {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 6px;
  box-sizing: border-box;
  font-size: 16px;
}

button {
  width: 100%;
  padding: 12px;
  margin-top: 18px;
  background-color: #1976d2;
  color: white;
  border: none;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
}

button:hover {
  background-color: #125ca1;
}

button.clear {
  margin-top: 10px;
  background-color: #e53935;
}

button.clear:hover {
  background-color: #b71c1c;
}

h2 {
  margin-top: 25px;
  padding: 12px;
  background-color: #eef5ff;
  border-radius: 6px;
  color: #333;
  overflow-wrap: anywhere;
  font-size: 18px;
}
```

## OUTPUT
<img width="1095" height="713" alt="image" src="https://github.com/user-attachments/assets/0ddd7a3d-43c2-4e28-8c9f-4993a90c8c4b" />
<img width="1108" height="777" alt="image" src="https://github.com/user-attachments/assets/df0d7bde-c5b5-4a8a-9e63-7e986e95da07" />

## RESULT

Thus, a basic calculator application was successfully implemented using React. It performs addition, subtraction, multiplication, and division, handles division by zero, and provides a Clear button to reset the calculator.
