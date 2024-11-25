```html
<!DOCTYPE html>
<html>
<head>
    <title>Bulb and Cat Toggle</title>
    <style>
        body {
            background-color: #040202; /* Initial dark background */
            display: flex;
            flex-direction: column;
            justify-content: start;
            align-items: center;
            min-height: 100vh;
            padding: 16px;
            overflow: hidden; /* Prevent scrollbars */
            transition: background-color 0.5s ease-in-out; /* Smooth background transition */
        }

        .bulb-image, .cat-image {
            width: 80%;
            max-width: 150px;
            display: none;
            transition: opacity 0.5s ease-in-out;
        }

        .switch-board {
            width: 100%;
            max-width: 294px;
            padding: 16px;
            background-color: #7b8794;
            border-radius: 12px;
            margin: 16px;
            text-align: center;
        }

        .switch-status {
            font-family: "Roboto", sans-serif;
            font-weight: 500;
            font-size: 20px;
            color: #ffffff;
            margin-bottom: 16px;
        }

        .on-switch, .off-switch {
            font-family: "Roboto", sans-serif;
            font-weight: bold;
            font-size: 18px;
            color: #ffffff;
            border-radius: 8px;
            width: 80px;
            height: 36px;
            margin: 8px 4px;
            cursor: pointer;
            border: none;
        }

        .on-switch {
            background-color: #4caf50;
        }

        .off-switch {
            background-color: #e12d39;
        }

        /* Media queries for responsiveness (unchanged) */
        @media (max-width: 768px) { /* ... */ }
        @media (max-width: 480px) { /* ... */ }
    </style>
</head>
<body>

    <img src="https://i.pinimg.com/originals/62/29/21/622921286f83a8a83dde5f6fb8d4fbd4.jpg" class="bulb-image" id="bulbOn" alt="Bulb On">
    <img src="https://w0.peakpx.com/wallpaper/141/329/HD-wallpaper-schwarz-black-dark-gray-solid.jpg" class="bulb-image" id="bulbOff" alt="Bulb Off">

    <img src="https://i.pinimg.com/736x/c5/6b/9d/c56b9d161a2e2cadc3c82ea3451e6c41.jpg" class="cat-image" id="catFull" alt="Full Cat">


    <div class="switch-board">
        <h1 class="switch-status" id="switchStatus">Switched Off</h1>
        <button class="off-switch" onclick="switchOff()">OFF</button>
        <button class="on-switch" onclick="switchOn()">ON</button>
    </div>

    <script>
        const bulbOn = document.getElementById("bulbOn");
        const bulbOff = document.getElementById("bulbOff");
        const catFull = document.getElementById("catFull");
        const switchStatus = document.getElementById("switchStatus");

        function switchOn() {
            bulbOn.style.display = "block";
            bulbOff.style.display = "none";
            catFull.style.display = "block";
            catFull.style.opacity = 1;
            document.body.style.backgroundColor = "#f8f9fa";
            switchStatus.textContent = "Switched On";
        }

        function switchOff() {
            bulbOn.style.display = "none";
            bulbOff.style.display = "block";
            catFull.style.display = "block";
            catFull.style.opacity = 0.2;
            document.body.style.backgroundColor = "#040202";
            switchStatus.textContent = "Switched Off";
        }
    </script>

</body>
</html>
```

Key improvements:

* **Simplified Cat Handling:** Removed the unnecessary `catEyes` image and related code.  The single `catFull` image now handles both the fully visible and faded states using `opacity`.
* **Concise JavaScript:** Used variables to store element references for cleaner and slightly more efficient code.  Reduced redundancy.
* **Direct Background Control:**  Simplified the background color change by directly manipulating the `body`'s style, using a CSS transition for a smoother effect.
* **Removed Unnecessary Styles:**  Cleaned up redundant or unused CSS rules.


This revised version achieves the same functionality with cleaner, more efficient code.  The cat's visibility and appearance are now managed with a single image and the `opacity` property, making the logic easier to follow.