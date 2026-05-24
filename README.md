# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Name:Santhosh V
# Register no: 212224230251
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools
# Framing Prompts for AI-Assisted Project Coding

## Objective
Learners will learn how to design effective prompts for AI tools to assist them in coding tasks related to mini and final year projects. The exercise focuses on creating prompts that clearly guide AI systems to generate code, compare outputs, and provide meaningful insights.

---

# Exercise Description
Instead of directly writing the code, students must practice creating prompts that guide AI tools to:

- Generate Python code for interacting with multiple APIs.
- Compare outputs from different APIs and highlight differences.
- Suggest meaningful insights or next steps based on the results.

---

# Deliverable
Each student should submit:

1. The prompts they designed for each stage.
2. The AI-generated responses (code + explanation).
3. A short reflection note on how effective their prompts were and how they could refine them.

---

# Stage 1 — Prompt for Generating Python Code Using Multiple APIs

## Prompt
> I am building a student project using Python.  
> Write a Python program that fetches weather data from two different APIs (OpenWeatherMap API and WeatherAPI).  
> The program should:
> - Accept a city name as input.
> - Send requests to both APIs.
> - Extract temperature, humidity, and weather condition.
> - Display the results in a clean tabular format.
> - Use proper exception handling for invalid city names or API failures.
> - Add comments explaining each major step in the code.
> - Use the requests library.
> Also explain how the code works step-by-step for a beginner.

---

# Expected AI Response (Example)

```python
import requests

city = input("Enter city name: ")

api_key1 = "YOUR_OPENWEATHER_API_KEY"
api_key2 = "YOUR_WEATHERAPI_KEY"

url1 = f"https://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key1}&units=metric"
url2 = f"http://api.weatherapi.com/v1/current.json?key={api_key2}&q={city}"

try:
    response1 = requests.get(url1).json()
    response2 = requests.get(url2).json()

    print("\n--- Weather Comparison ---")

    print("\nOpenWeatherMap")
    print("Temperature:", response1['main']['temp'])
    print("Humidity:", response1['main']['humidity'])
    print("Condition:", response1['weather'][0]['description'])

    print("\nWeatherAPI")
    print("Temperature:", response2['current']['temp_c'])
    print("Humidity:", response2['current']['humidity'])
    print("Condition:", response2['current']['condition']['text'])

except Exception as e:
    print("Error:", e)
```

## Explanation
- The program accepts a city name from the user.
- It connects to two APIs using HTTP requests.
- JSON responses are converted into Python dictionaries.
- Required weather information is extracted and displayed.
- Exception handling prevents crashes when errors occur.

---

# Stage 2 — Prompt for Comparing API Outputs

## Prompt
> Compare the outputs received from OpenWeatherMap API and WeatherAPI in Python.  
> Write code that:
> - Identifies differences in temperature and humidity values.
> - Calculates the difference percentage.
> - Displays which API gives higher values.
> - Generates a summary report.
> - Use functions to make the program modular.
> Also explain why API outputs may vary slightly.

---

# Expected AI Response (Example)

```python
def compare_values(value1, value2, parameter):
    difference = abs(value1 - value2)

    if value1 > value2:
        higher = "OpenWeatherMap"
    else:
        higher = "WeatherAPI"

    print(f"\n{parameter} Difference: {difference}")
    print(f"Higher Value Provided By: {higher}")

temp1 = 30
temp2 = 29

humidity1 = 75
humidity2 = 70

compare_values(temp1, temp2, "Temperature")
compare_values(humidity1, humidity2, "Humidity")
```

## Explanation
- Functions improve code readability and reusability.
- The logic compares both values and identifies the higher one.
- APIs may vary because:
  - Data may come from different weather stations.
  - APIs update at different times.
  - Different prediction models are used.

---

# Stage 3 — Prompt for Generating Insights

## Prompt
> Based on the compared API results, suggest meaningful insights for the user.  
> The Python program should:
> - Detect unusual temperature differences.
> - Recommend which API appears more consistent.
> - Suggest actions if weather conditions are extreme.
> - Print user-friendly insights in natural language.
> - Keep the explanation simple for beginners.

---

# Expected AI Response (Example)

```python
temperature_difference = 5

if temperature_difference > 3:
    print("Large variation detected between APIs.")
    print("You may cross-check with another trusted weather source.")
else:
    print("Both APIs provide similar weather readings.")

weather_condition = "Storm"

if weather_condition.lower() == "storm":
    print("Extreme weather alert: Avoid unnecessary travel.")
```

## Explanation
- The program converts raw data into actionable insights.
- Users receive understandable recommendations instead of only numbers.
- AI can help automate decision-making in projects.

---

# Reflection Note

## Reflection
The prompts were effective because they clearly specified:
- The programming language.
- Required APIs.
- Output format.
- Additional requirements like exception handling and explanations.

The detailed instructions helped the AI generate more accurate and structured responses.

## Possible Improvements
- Specify exact output formatting requirements.
- Mention preferred libraries or frameworks.
- Include sample inputs and expected outputs.
- Request optimized or production-level code for advanced projects.

---

# Conclusion
This exercise demonstrates how well-structured prompts can guide AI tools to:
- Generate useful Python programs.
- Compare outputs intelligently.
- Produce actionable insights for real-world applications.

Effective prompt framing improves the quality, accuracy, and usability of AI-generated coding solutions.


# Result: The corresponding Prompt is executed successfully.
