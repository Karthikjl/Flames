# Try this -> [Click here](https://karthikjl.github.io/Flames/)

#Html 
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FLAMES</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <h1>FLAMES</h1>
    <div id="main">
        <form id="flamesForm">
            <label for="yourName">Your Name:</label>
            <input type="text" id="yourName" name="yourName" required>
            <br><br>
            <label for="partnerName">Partner's Name:</label>
            <input type="text" id="partnerName" name="partnerName" required>
            <br><br>
            <button type="submit">Calculate Flames</button>
        </form>
        <div id="result"></div>
    </div>
    <script>
        document.getElementById("flamesForm").addEventListener("submit", function(event) {
            event.preventDefault();
            var yourName = document.getElementById("yourName").value.toLowerCase();
            var partnerName = document.getElementById("partnerName").value.toLowerCase();
            var flames = "flames";

            // Remove common characters
            for (var i = 0; i < yourName.length; i++) {
                for (var j = 0; j < partnerName.length; j++) {
                    if (yourName[i] === partnerName[j]) {
                        yourName = yourName.replace(yourName[i], '');
                        partnerName = partnerName.replace(partnerName[j], '');
                        i--;
                        break;
                    }
                }
            }

            // Calculate remaining characters
            var remainingChars = yourName + partnerName;

            // Calculate flames
            while (flames.length > 1) {
                var index = remainingChars.length % flames.length;
                if (index === 0) {
                    flames = flames.substring(0, flames.length - 1);
                } else {
                    flames = flames.substring(index) + flames.substring(0, index - 1);
                }
            }

            // Determine the relationship
            var result;
            switch (flames) {
                case 'f':
                    result = "Friendship🫂";
                    break;
                case 'l':
                    result = "Love💖";
                    break;
                case 'a':
                    result = "Affection😍";
                    break;
                case 'm':
                    result = "Marriage🤵👰";
                    break;
                case 'e':
                    result = "Enemy😈";
                    break;
                case 's':
                    result = "Sibling🧑👧";
                    break;
                default:
                    result = "Error";
            }

            // Display the result
            document.getElementById("result").innerHTML = "</br></br>The relationship between " +
                document.getElementById("yourName").value.toLowerCase() + " and " +
                document.getElementById("partnerName").value.toLowerCase() + " is " + result;
        });
    </script>
</body>

</html>
```

#Css 
```
@import url('https://fonts.googleapis.com/css?family=Poppins');
body {
    font-family: 'Poppins';
    background-color: #f5f5f5;
    text-align: center;
}

.container {
    width: 50%;
    margin: 0 auto;
    padding: 20px;
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

p {
    margin-top: auto;
    margin-bottom: 20px;
    color: #666;
}

input[type="text"] {
    width: 250px;
    padding: 10px;
    margin-bottom: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    padding: 10px 20px;
    background-color: #4CAF50;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    align-items: center;
    font: 'Poppins';
}

button:hover {
    background-color: #45a049;
}

```
