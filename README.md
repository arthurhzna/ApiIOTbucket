# IoT Bucket API 🌟

A Flask-based REST API that manages IoT sensor data and stores it in Google Cloud Storage. This API handles sensor values and relay status data from IoT devices, with multiple operation modes and conditions.

## 🚀 Features

- Real-time IoT data reception and storage
- Google Cloud Storage integration
- Mode and condition management
- Sensor value and relay status monitoring

## 🛠️ Technologies Used

- Python
- Flask
- Google Cloud Storage
- JSON for data exchange

## 📋 API Endpoints

### Mode Management
- `GET /check_mode` - Check current operation mode
- `GET /set_mode/<int:new_mode>` - Set new operation mode

### Condition Management
- `GET /check_kondisi` - Check current condition status (ON/OFF)
- `GET /set_kondisi/<int:new_kondisi>` - Set new condition status

### Data Operations
- `POST /receive_data` - Receive and store sensor data
- `GET /check_data` - Retrieve latest sensor data

## 📦 Data Structure

The API handles data in the following format:
```json
{
    "sensorValue": float,
    "relayStatus": string
}
```

## 🔧 Setup and Installation

1. Install required dependencies:
```bash
pip install flask google-cloud-storage
```

2. Configure Google Cloud Storage:
   - Set up a Google Cloud project
   - Create a bucket named "iot-bucket-arthur"
   - Configure authentication credentials

3. Run the application:
```bash
python apibucket.py
```

## 💡 Usage Example

### Sending Sensor Data
```bash
curl -X POST http://localhost:5000/receive_data \
-H "Content-Type: application/json" \
-d '{"sensorValue": 25.5, "relayStatus": "ON"}'
```

## 📝 Data Storage

- Data is stored in Google Cloud Storage bucket
- Storage format: `<sensor_value> <relay_status> <timestamp>`
- File name: `data.txt`

## ⚙️ Environment

- The application runs in debug mode by default
- Default port: 5000
- Supports both development and production environments

## 🔒 Security Notes

- Ensure proper Google Cloud credentials configuration
- Implement authentication for production use
- Secure sensitive endpoints

## 👥 Contributing

Feel free to submit issues and enhancement requests!

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details

---
Made with ❤️ for IoT Development
