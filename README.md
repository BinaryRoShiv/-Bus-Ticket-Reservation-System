# -Bus-Ticket-Reservation-System
This is my first project
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bus Ticket Reservation</title>
    <style>
        body {
            font-family: sans-serif;
            margin: 20px;
            background-color: #f4f4f4;
        }
        .container {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            margin: 0 auto;
        }
        h1, h2 {
            color: #333;
            text-align: center;
        }
        #welcome-message {
            margin-bottom: 20px;
            font-size: 1.2em;
            text-align: center;
            color: #555;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #333;
        }
        input[type="text"],
        input[type="date"],
        select {
            width: calc(100% - 22px);
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }
        button {
            background-color: #007bff;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1em;
        }
        button:hover {
            background-color: #0056b3;
        }
        #reservation-form {
            display: none; /* Initially hide the reservation form */
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Bus Ticket Reservation</h1>

        <div id="name-input-section">
            <h2>Enter Your Name</h2>
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>
            <button onclick="greetUser()">Continue</button>
        </div>

        <div id="welcome-section" style="display: none;">
            <p id="welcome-message"></p>
        </div>

        <div id="reservation-form" style="display: none;">
            <h2>Book Your Ticket</h2>
            <label for="from">From:</label>
            <input type="text" id="from" name="from" required>

            <label for="to">To:</label>
            <input type="text" id="to" name="to" required>

            <label for="date">Date of Journey:</label>
            <input type="date" id="date" name="date" required>

            <label for="passengers">Number of Passengers:</label>
            <select id="passengers" name="passengers">
                <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
                <option value="4">4</option>
            </select>

            <button onclick="submitReservation()">Search Buses</button>
        </div>
    </div>

    <script>
        function greetUser() {
            const nameInput = document.getElementById('name');
            const name = nameInput.value.trim();

            if (name) {
                document.getElementById('name-input-section').style.display = 'none';
                document.getElementById('welcome-message').textContent = `Welcome, ${name}!`;
                document.getElementById('welcome-section').style.display = 'block';
                document.getElementById('reservation-form').style.display = 'block';
            } else {
                alert('Please enter your name.');
            }
        }

        function submitReservation() {
            const from = document.getElementById('from').value;
            const to = document.getElementById('to').value;
            const date = document.getElementById('date').value;
            const passengers = document.getElementById('passengers').value;

            // In a real application, you would send this data to a server
            alert(`Searching for buses from ${from} to ${to} on ${date} for ${passengers} passenger(s)... (This is a simulation)`);
            // You would typically use JavaScript to make an AJAX request here.
        }
    </script>
</body>
</html>
