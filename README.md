<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LoL Team Finder</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #121212;
            color: #ffffff;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #1e1e2f;
            padding: 1rem;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 2rem;
        }

        main {
            padding: 2rem;
        }

        .section {
            margin-bottom: 2rem;
        }

        .section h2 {
            color: #00aaff;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        form input, form select, form button {
            display: block;
            margin: 0.5rem 0;
            padding: 0.5rem;
            width: 100%;
            max-width: 400px;
        }

        .profiles {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .profile {
            background-color: #1e1e2f;
            border: 1px solid #333;
            padding: 1rem;
            border-radius: 5px;
            width: 250px;
        }

        .profile h3 {
            margin: 0 0 0.5rem 0;
            font-size: 1.2rem;
        }
    </style>
</head>
<body>
    <header>
        <h1>League of Legends Team Finder</h1>
    </header>

    <main>
        <!-- Form Section -->
        <div class="section" id="profile-form">
            <h2>Create Your Profile</h2>
            <form id="createProfile">
                <input type="text" id="summonerName" placeholder="Summoner Name" required>
                <select id="rank" required>
                    <option value="">Select Rank</option>
                    <option value="Iron">Iron</option>
                    <option value="Bronze">Bronze</option>
                    <option value="Silver">Silver</option>
                    <option value="Gold">Gold</option>
                    <option value="Platinum">Platinum</option>
                    <option value="Diamond">Diamond</option>
                    <option value="Master">Master</option>
                    <option value="Grandmaster">Grandmaster</option>
                    <option value="Challenger">Challenger</option>
                </select>
                <select id="role" required>
                    <option value="">Select Role</option>
                    <option value="Top">Top</option>
                    <option value="Jungle">Jungle</option>
                    <option value="Mid">Mid</option>
                    <option value="ADC">ADC</option>
                    <option value="Support">Support</option>
                </select>
                <button type="submit">Add Profile</button>
            </form>
        </div>

        <!-- Profiles Section -->
        <div class="section" id="profiles">
            <h2>Available Players</h2>
            <div class="profiles" id="profilesList">
                <!-- Profiles will appear here -->
            </div>
        </div>
    </main>

    <script>
        const form = document.getElementById('createProfile');
        const profilesList = document.getElementById('profilesList');

        form.addEventListener('submit', (e) => {
            e.preventDefault();

            // Get form data
            const summonerName = document.getElementById('summonerName').value;
            const rank = document.getElementById('rank').value;
            const role = document.getElementById('role').value;

            // Create a profile card
            const profileCard = document.createElement('div');
            profileCard.className = 'profile';
            profileCard.innerHTML = `
                <h3>${summonerName}</h3>
                <p><strong>Rank:</strong> ${rank}</p>
                <p><strong>Role:</strong> ${role}</p>
            `;

            // Add to the profiles list
            profilesList.appendChild(profileCard);

            // Clear form
            form.reset();
        });
    </script>
</body>
</html>
