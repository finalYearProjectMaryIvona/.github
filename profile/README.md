# Final Year Project: Mobile Traffic Detection and Analysis System

This organisation hosts the repositories for the Final Year Project completed by Mary McDonnell and Ivona Cvija.  
The project focuses on enabling real-time traffic monitoring using mobile devices, lightweight machine learning models, and full-stack cloud integration.
Want to see the system work? Watch this [screen cast](https://youtu.be/BiGP9D95-no)

---

## Project Overview

The goal of this project was to create a working proof-of-concept system where a mobile phone could be used to:
- Detect and classify vehicles in real-time using TensorFlow Lite models.
- Track vehicle movements using a lightweight centroid-based tracker.
- Record traffic session metadata including GPS coordinates.
- Store traffic data and bus images in a cloud-hosted MongoDB database.
- Provide an interactive web dashboard for visualising traffic patterns via maps and graphs.

This system consists of three main components:
- **Mobile Application** — Native Android App (Kotlin + TFLite)
- **Backend Server** — Node.js Server + MongoDB Atlas Database
- **Web Application** — React.js frontend with ReCharts and Google Maps integration

---

## Repositories

| Repository | Description | Link |
|:---|:---|:---|
| **Mobile Application** | Android app for real-time vehicle detection, tracking, and data logging. | [Mobile App Repo](https://github.com/finalYearProjectMaryIvona/kotlin_tflite) |
| **Backend Server** | Node.js server managing data collection, authentication, and cloud storage. | [Server Repo](https://github.com/finalYearProjectMaryIvona/backend_server) |
| **Web Application** | React web app for traffic session visualisation using maps and charts. | [Web App Repo](https://github.com/finalYearProjectMaryIvona/front_end_web_app) |
| **Legacy Repositories** | Early experiments using React Native, Tensorflow.js, and ONNX models before moving to native development. | Found with the the other repositories |

>  **Note:** Older experimental repositories are retained for documentation and learning purposes but are not part of the final system.

---

## Installation Instructions For Repos

Each repository contains its own detailed setup guide in the README.  
The steps are:

### Mobile Application
### Clone the repository
```bash
git clone https://github.com/finalYearProjectMaryIvona/kotlin_tflite.git
cd kotlin_tflite
```
### Open in Android Studio
- Open the project folder in Android Studio.
- Let Gradle sync and download all required dependencies.

## Important assets
Model and labels are already in assets folder (app/src/main/assets/)

Update BASE_IP with device's ipv4 address in Constants.kt
```bash
// Replace PUTYOURIPV4HERE with your server's IPv4 address
const val BASE_IP = "http://YOUR_SERVER_IP:5000"
```
Have mobile device connected to computer (through wifi or cable). Once Android Studio sees you mobile device, click on Run button to build and deploy the app on mobile device.

## Backend Server
This mobile app needs a backend server for user management, session storage and visualization

Make sure the [Backend Server](https://github.com/finalYearProjectMaryIvona/backend_server) is running and is accessible from the mobile device (on the same wifi or hotspot).


### Backend Server
Clone the repository:
```bash
git clone https://github.com/finalYearProjectMaryIvona/backend_server.git
```

Go into project:
```bash
cd kotlin_onnx_backend
```

Install dependencies:
```bash
npm install
npm install jsonwebtoken
```

Make sure there is a `.env` file in the project root and add if it's not already there:
```
PORT=5000
MONGO_URI=mongodb+srv://<your_user>:<your_password>@cluster0.mongodb.net/<your_db_name>?retryWrites=true&w=majority
JWT_SECRET=your_jwt_secret
```
Change:
<your_user> to your MongoDB username

<your_password> to your MongoDB password

<your_db_name> to your database name

To run the server:
```bash
node server.js
```

Server should be running at: [http://localhost:5000](http://localhost:5000).


### Web Application
Clone the repository with:<br />
```bash
git clone https://github.com/finalYearProjectMaryIvona/front_end_web_app.git
```

In the project directory, run:<br />
```bash
npm install react-router-dom axios html2pdf.js recharts @react-google-maps/api bootstrap
```

Make sure there is a `.env` file in the project root with the google api key
`REACT_APP_GOOGLE_MAPS_API_KEY=your_google_maps_key`


To run the app, you can run this command:

```bash
npm start
```

The server must also be running for the web application to work

