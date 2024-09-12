Creating a basic calculator using HTML, CSS, and JavaScript is a great project to practice and solidify your understanding of these technologies. Below is a step-by-step guide along with sample code to help you build a simple calculator.

### **1. Project Structure**

Create a folder for your project, e.g., `basic-calculator`. Inside this folder, you should have:

- `index.html` (for HTML structure)
- `styles.css` (for CSS styling)
- `script.js` (for JavaScript functionality)

### **2. HTML Structure**

Here’s the HTML structure for your calculator:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="calculator">
        <div class="display">
            <input type="text" id="display" readonly>
        </div>
        <div class="buttons">
            <button class="btn" onclick="clearDisplay()">C</button>
            <button class="btn" onclick="appendToDisplay('7')">7</button>
            <button class="btn" onclick="appendToDisplay('8')">8</button>
            <button class="btn" onclick="appendToDisplay('9')">9</button>
            <button class="btn operator" onclick="appendToDisplay('/')">/</button>
            <button class="btn" onclick="appendToDisplay('4')">4</button>
            <button class="btn" onclick="appendToDisplay('5')">5</button>
            <button class="btn" onclick="appendToDisplay('6')">6</button>
            <button class="btn operator" onclick="appendToDisplay('*')">*</button>
            <button class="btn" onclick="appendToDisplay('1')">1</button>
            <button class="btn" onclick="appendToDisplay('2')">2</button>
            <button class="btn" onclick="appendToDisplay('3')">3</button>
            <button class="btn operator" onclick="appendToDisplay('-')">-</button>
            <button class="btn" onclick="appendToDisplay('0')">0</button>
            <button class="btn" onclick="appendToDisplay('.')">.</button>
            <button class="btn equal" onclick="calculate()">=</button>
            <button class="btn operator" onclick="appendToDisplay('+')">+</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

### **3. CSS Styling**

Here’s the CSS for styling your calculator. Save this in `styles.css`:

```css
/* Basic reset */
body, html {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f0f0;
}

.calculator {
    width: 200px;
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    background-color: #fff;
}

.display {
    padding: 10px;
    background-color: #222;
    color: #fff;
    text-align: right;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}

#display {
    width: 100%;
    border: none;
    background: transparent;
    color: #fff;
    font-size: 1.5em;
    text-align: right;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
}

.btn {
    border: 1px solid #ccc;
    padding: 20px;
    font-size: 1.2em;
    background-color: #eee;
    cursor: pointer;
    transition: background-color 0.3s;
}

.btn:hover {
    background-color: #ddd;
}

.operator {
    background-color: #f0a;
    color: #fff;
}

.operator:hover {
    background-color: #e09;
}

.equal {
    grid-column: span 2;
    background-color: #0a0;
    color: #fff;
}

.equal:hover {
    background-color: #090;
}

.btn:active {
    background-color: #ccc;
}
```

### **4. JavaScript Functionality**

Here’s the JavaScript to handle button clicks and perform calculations. Save this in `script.js`:

```javascript
function appendToDisplay(value) {
    const display = document.getElementById('display');
    display.value += value;
}

function clearDisplay() {
    document.getElementById('display').value = '';
}

function calculate() {
    const display = document.getElementById('display');
    try {
        display.value = eval(display.value);
    } catch {
        display.value = 'Error';
    }
}
```

### **5. How It Works**

1. **HTML**:
   - Defines the structure of the calculator with a display area and buttons.
   - Each button has an `onclick` attribute that calls a specific JavaScript function.

2. **CSS**:
   - Styles the calculator, display, and buttons.
   - Uses CSS grid to align the buttons in a 4x4 layout.

3. **JavaScript**:
   - `appendToDisplay(value)`: Adds the clicked button’s value to the display.
   - `clearDisplay()`: Clears the display when the "C" button is clicked.
   - `calculate()`: Evaluates the expression in the display and updates it with the result. Handles errors gracefully by displaying "Error".

### **6. Testing and Deployment**

- **Test Locally**: Open `index.html` in a web browser to see the calculator in action. Test each button to ensure it works as expected.
- **Deploy Online**: You can use platforms like GitHub Pages, Netlify, or Vercel to host your calculator online.

With this setup, you’ll have a fully functional, simple calculator that can perform basic arithmetic operations. Feel free to expand and enhance it with additional features or styling as you continue to learn and grow in web development!
