from flask import Flask, request, jsonify
from flask_cors import CORS

app = Flask(__name__)
CORS(app)

def simple_ai_analysis(symptoms):
    symptoms = symptoms.lower()

    if "fever" in symptoms and "cough" in symptoms:
        return "Possible Flu or COVID-19. Please consult a doctor."
    elif "headache" in symptoms:
        return "Could be stress or migraine."
    elif "chest pain" in symptoms:
        return "Seek immediate medical attention."
    else:
        return "Not enough data. Please consult a healthcare professional."

@app.route("/analyze", methods=["POST"])
def analyze():
    data = request.json
    symptoms = data.get("symptoms", "")

    result = simple_ai_analysis(symptoms)

    return jsonify({"result": result})

if __name__ == "__main__":
    app.run(debug=True)
