# Bill & Tip Calculator

A lightweight, browser-based web application designed to instantly calculate a standard **15% tip** based on a user's total bill amount. This project showcases foundational frontend skills, including HTML5 form handling, basic input validation, and dynamic DOM manipulation using vanilla JavaScript.

As seen in the source code within `image.png`, the entire application structure and logic are efficiently self-contained within a single file.

🔗 **Live Demo Hosted on GitHub Pages:** https://esther-kentomahun.github.io/bill_calculator_app/

---

## 🚀 Features

* **Instant Calculation:** Processes the tip amount on form submission without reloading the browser page.
* **Input Validation:** Built-in validation ensures that users provide a valid, realistic numeric amount before processing.
* **Error Handling:** Dynamically displays a targeted error prompt for invalid entries and clears it automatically once a valid amount is supplied.
* **Minimalist UI:** A clean, typography-first user interface focused completely on utility and distraction-free interaction.

---

## 🛠️ Tech Stack

* **HTML5:** Used for structuring the layout container, form inputs, submission button, and semantic text placeholders.
* **JavaScript (ES6):** Powering the logic—including capturing form submit events, preventing default browser behavior, parsing input strings into numbers with `parseFloat()`, implementing conditional logic, and dynamically updating element text content.

---

## 📸 Project Preview

Below is a look at the application interface and calculation behavior running on a local development environment (as shown in `image_2.png`):

![Tip Calculator Live Preview](image_2.png)

---

## 💻 Code Architecture

The dynamic functionality is handled entirely by an event listener attached to the input form. It evaluates the input and updates the DOM elements dynamically based on whether the condition is met:

```javascript
form.addEventListener("submit", (e) => {
    e.preventDefault();
    const billValue = parseFloat(billAmount.value);

    if (isNaN(billValue) || billValue <= 0) {
        errorMSG.textContent = "Please enter a valid bill amount.";
        resultText.textContent = ""; 
    } else {
        errorMSG.textContent = ""; 
        const tipAmount = billValue * 0.15;
        resultText.textContent = `Tip Amount: $${tipAmount.toFixed(2)}`;
    }
});
