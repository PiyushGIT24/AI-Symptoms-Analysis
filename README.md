# AI-Symptoms-Analysis
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>AI Symptom Checker</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.5/font/bootstrap-icons.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Quicksand', sans-serif;
            background: linear-gradient(to right, #dbeafe, #e0f2fe);
            padding-bottom: 60px;
        }
        .container {
            max-width: 650px;
            margin-top: 60px;
        }
        .card {
            padding: 35px;
            border-radius: 15px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            background-color: #ffffff;
            animation: fadeIn 1s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .title {
            text-align: center;
            margin-bottom: 25px;
            color: #0a58ca;
        }
        .form-check {
            margin-bottom: 12px;
        }
        .form-check-label {
            margin-left: 8px;
        }
        .btn-primary {
            background-color: #0d6efd;
            border: none;
            transition: background 0.3s;
        }
        .btn-primary:hover {
            background-color: #0a58ca;
        }
        footer {
            text-align: center;
            padding: 20px 0;
            background-color: #e0f2fe;
            color: #555;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="card">
            <h2 class="title">🩺 AI Symptom Checker</h2>
            <form method="POST" action="/predict">
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="fever" value="1" id="fever">
                    <label class="form-check-label" for="fever"><i class="bi bi-thermometer-half"></i> Fever</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="cough" value="1" id="cough">
                    <label class="form-check-label" for="cough"><i class="bi bi-wind"></i> Cough</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="fatigue" value="1" id="fatigue">
                    <label class="form-check-label" for="fatigue"><i class="bi bi-battery-half"></i> Fatigue</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="headache" value="1" id="headache">
                    <label class="form-check-label" for="headache"><i class="bi bi-emoji-dizzy"></i> Headache</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="sore_throat" value="1" id="sore_throat">
                    <label class="form-check-label" for="sore_throat"><i class="bi bi-chat-left-dots"></i> Sore Throat</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="runny_nose" value="1" id="runny_nose">
                    <label class="form-check-label" for="runny_nose"><i class="bi bi-droplet"></i> Runny Nose</label>
                </div>
                <div class="form-check">
                    <input class="form-check-input" type="checkbox" name="nausea" value="1" id="nausea">
                    <label class="form-check-label" for="nausea"><i class="bi bi-emoji-frown"></i> Nausea</label>
                </div>
                <div class="form-check mb-4">
                    <input class="form-check-input" type="checkbox" name="diarrhea" value="1" id="diarrhea">
                    <label class="form-check-label" for="diarrhea"><i class="bi bi-water"></i> Diarrhea</label>
                </div>

                <button type="submit" class="btn btn-primary w-100">🔍 Predict Disease</button>
            </form>

            {% if result %}
            <div class="alert alert-success text-center mt-4">
                <strong>Predicted Disease:</strong> {{ result }}
            </div>
            {% endif %}
        </div>
    </div>

    <footer>
        @ 2025 AI Health Assistant by Geeta Kakrani 
    </footer>
</body>
</html>
