# figo

from flask import Flask, render_template_string

app = Flask(__name__)

HTML_PAGE = """
<!DOCTYPE html>
<html>
<head>
    <title>Hey ❤️</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .card {
            background: white;
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
            max-width: 400px;
        }
        h1 {
            color: #ff4d6d;
        }
        button {
            padding: 12px 25px;
            border: none;
            border-radius: 25px;
            background: #ff4d6d;
            color: white;
            font-size: 16px;
            cursor: pointer;
        }
        button:hover {
            background: #e63950;
        }
    </style>
    <script>
        function confess() {
            document.getElementById("msg").innerHTML =
            "I really like you ❤️<br><br>You make my days brighter.";
        }
    </script>
</head>
<body>

<div class="card">
    <h1>Hey 😊</h1>
    <p id="msg">I have something important to tell you...</p>
    <button onclick="confess()">Click Me</button>
</div>

</body>
</html>
"""

@app.route("/")
def home():
    return render_template_string(HTML_PAGE)

if __name__ == "__main__":
    app.run(debug=True)
