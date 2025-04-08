# Collaborative Intelligence Component

## Overview
The **Collaborative Intelligence Component** is a web-based application designed to demonstrate an AI-assisted decision-making system at the **Edge**. It integrates human and machine intelligence to curate model results collaboratively and provides seamless recalibration of the AI model with a single click. The tool can be used to generate new training data when training data is scarce. The advantage is that this new data is generated automatically (an LLM generates it) based on positive and negative cases manually curated by domain experts.

This industrial demonstrator showcases data visualization, real-time interaction, and MQTT-based communication for industrial pilots. It is currently ready to work with ChatGPT 4o.

![Screenshot](image.png)

## Features
- **Real-Time Data Processing**: Integrates with MQTT to receive and process live data.
- **Dynamic Table Interface**: Displays AI predictions alongside human adjustments.
- **AI Explanation Generation**: Uses GenAI to provide reasoning for AI predictions.
- **Automated Model Recalibration**: Enables model adjustments based on curated results.
- **CSV File Handling**: Supports data import and export for analysis.
- **Interactive Charts**: Visualizes AI predictions against actual values.
- **Status Monitoring**: Provides insights into AI accuracy through live charts.

## System Architecture
The system consists of:
- **Frontend**: A web interface built with HTML, CSS, and JavaScript.
- **Backend Integration**: Communicates with an MQTT broker to send and receive messages.
- **GenAI API**: Connects to Chatbase for AI-generated explanations.
- **Data Visualization**: Uses Plotly.js for dynamic chart rendering.

## Usage Guide
1. **Open the Interface**  
   Open `index.html` in a modern web browser.
   
2. **Load Configuration**  
   - Click **"Load Config"** and upload a `.json` configuration file.
   - The system validates and auto-connects to the MQTT broker.

3. **Connect to Broker**  
   - Click **"Connect to Broker"** to establish communication with the MQTT server.
   - Real-time data will be displayed in the table.

4. **Analyze Data**  
   - View AI predictions vs. actual target values.
   - Modify target values if necessary.
   - AI explanations are automatically generated.

5. **Recalibrate Model**  
   - Click **"Recalibrate Model"** to adjust the AI model based on user input.

6. **Export Data**  
   - Click **"Export Non-OK Rows"** to save problematic cases in JSON format.

## Configuration File (Example)
To connect to an MQTT broker, create a `config.json` file:

```json
{
    "brokerURL": "wss://broker.hivemq.com:8000/mqtt",
    "inputTopic": "ai/input",
    "outputTopic": "ai/output",
    "inputs": [
        {"name": "Feature1"},
        {"name": "Feature2"},
        {"name": "Feature3"}
    ]
}
```

## Customization
- **Styling**: Modify the CSS in the `<style>` section of the HTML file.
- **Feature Expansion**: Extend JavaScript functions to support new AI models.
- **Integration**: Connect to different MQTT brokers or APIs.

## System Requirements
- A modern web browser (Chrome, Firefox, Edge, or Safari).
- An MQTT broker (e.g., HiveMQ, Mosquitto).
- A CSV file for data import.

## Acknowledgment
This work is performed within the **AI REDGIO 5.0** project:  
*"Regions and (E)DIHs alliance for AI-at-the-Edge adoption by European Industry 5.0 Manufacturing SMEs"* under **EU Grant Agreement No. 101092069**.
