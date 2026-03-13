

You must create two new files in the system. The first is a Python server that generates random colors.

from flask import Flask, jsonify
import random

app = Flask(__name__)

@app.route("/")
def home():
    return "Color Server Running. Use /color"

@app.route("/color")
def get_color():
    r = random.randint(0,255)
    g = random.randint(0,255)
    b = random.randint(0,255)

    return jsonify({
        "r": r,
        "g": g,
        "b": b
    })

if __name__ == "__main__":
    app.run(host="127.0.0.1", port=5000)

The second file is a .env file that stores environment variables such as the OpenAI API key.

OPENAI_API_KEY=your_api_key_here

The rest of the system runs inside Unreal Engine.

