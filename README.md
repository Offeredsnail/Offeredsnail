<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Voting Website</title>
    <style>
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
        }
        .option {
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Do you support palestine</h2>
        <div class="options">
            <div class="option">
                <input type="radio" name="vote" value="option1">
                <label>yes</label>
            </div>
            <div class="option">
                <input type="radio" name="vote" value="option2">
                <label>no</label>
            </div>
            <div class="option">
                <input type="radio" name="vote" value="option3">
                <label>idk</label>
            </div>
            <div class="option">
                <input type="radio" name="vote" value="option4">
                <label>idc</label>
            </div>
        </div>
        <button onclick="submitVote()">Submit Vote</button>
        <div id="results" style="margin-top: 20px;"></div>
    </div>

    <script>
        let votes = {
            option1: 0,
            option2: 0,
            option3: 0,
            option4: 0
        };

        function submitVote() {
            const selectedOption = document.querySelector('input[name="vote"]:checked');
            if (selectedOption) {
                const optionValue = selectedOption.value;
                votes[optionValue] += 10; // Increase by 10%
                displayResults();
            } else {
                alert('Please select an option to vote.');
            }
        }

        function displayResults() {
            const totalVotes = Object.values(votes).reduce((acc, curr) => acc + curr, 0);
            let resultsHTML = '<h2>Results</h2>';
            for (const [option, voteCount] of Object.entries(votes)) {
                const percentage = (voteCount / totalVotes) * 100 || 0;
                resultsHTML += `<p>${option}: ${voteCount} votes (${percentage.toFixed(2)}%)</p>`;
            }
            document.getElementById('results').innerHTML = resultsHTML;
        }
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Background Image HTML</title>
    <style>
        body {
            background-image: url("https://www.solidaire.org/sites/default/files/images/2019/04/12/gaza-38294051280.jpg");
            background-size: cover; /* Cover the entire background */
            background-position: center; /* Center the background image */
            height: 100vh; /* Set the height to 100% of the viewport height */
            margin: 0; /* Remove default margins */
            padding: 0; /* Remove default padding */
        }
    </style>
</head>
<body>
    <!-- Your content goes here -->
</body>
</html>
