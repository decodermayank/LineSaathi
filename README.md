# LineSaathi
Real-time queue intelligence system that reduces waiting times through IoT sensors, live analytics, and data-driven predictions. Monitor crowds, estimate wait times, and optimize occupancy across venues with an intuitive dashboard.
# LineSaathi: Smart Queue Intelligence System

A real-time queue monitoring and management system that leverages IoT sensors and intelligent analytics to optimize crowd flow and reduce waiting times in high-traffic environments.

---

## 📋 Overview

LineSaathi is a comprehensive solution designed for intelligent queue management across diverse venues such as college cafeterias, service counters, public events, and commercial establishments. The system combines hardware sensor integration with a web-based dashboard to provide real-time occupancy tracking, predictive analytics, and administrative controls.

**Key Problem:** Long waiting queues lead to poor user experience, operational inefficiencies, and resource wastage.

**Our Solution:** Real-time crowd monitoring with predictive insights and administrative controls to optimize queue flow.

---

## ✨ Core Features

### 🎯 Live Dashboard
- **Real-Time Occupancy Tracking:** Monitor current crowd levels with live updates from hardware sensors
- **Dynamic Status Indicators:** Visual representation of crowd levels (Low / Medium / High)
- **Capacity Visualization:** Dynamic progress bars showing current vs. maximum capacity
- **Live Flow Metrics:** Real-time entry, exit, and net flow rate measurements
- **Animated Trend Analysis:** Interactive Chart.js graphs displaying crowd trends over time

### 📊 Predictive Intelligence
- **Wait Time Estimation:** AI-driven estimation of queue waiting times
- **15-Minute Crowd Forecast:** Predictive model for upcoming crowd density
- **Rush Hour Detection:** Automatic identification of peak usage periods
- **Optimal Visit Time Recommendation:** Smart suggestions for best times to visit

### ⚙️ Administrative Console
- **Capacity Management:** Configurable maximum occupancy limits
- **System Reset Controls:**
  - Clear current occupancy count
  - Reset entry/exit counters
  - Clear historical graph data
- **Secure Authentication:** Password-protected admin access with session management

### 🎨 User Experience
- **Dark/Light Theme Toggle:** Seamless switching between dark and light modes
- **Glassmorphism Design:** Modern UI aesthetics in light mode
- **Premium Black-Gold Theme:** Sophisticated dark mode styling
- **Responsive Layout:** Fully optimized for desktop, tablet, and mobile devices

---

## 🏗️ Technology Stack

### Frontend
- **HTML5** – Semantic markup and structure
- **CSS3** – Advanced styling with custom properties and Tailwind utilities
- **JavaScript (ES6+)** – Interactive features and real-time updates

### Backend
- **Flask** – Lightweight Python web framework
- **Python 3.x** – Server-side logic and data processing

### Data Visualization
- **Chart.js** – Interactive and animated charting library

### Hardware Integration
- **Arduino UNO** – Microcontroller for sensor processing
- **IR Sensors (2x)** – Infrared motion detection for entry/exit counting
- **Breadboard & Jumper Wires** – Connection infrastructure

---

## 📁 Project Structure

```
LineSaathi/
├── app.py                          # Flask application server
├── Arduino_Code.txt                # Microcontroller code for sensor integration
│
├── templates/                      # HTML templates
│   ├── index.html                  # Main dashboard
│   ├── admin_panel.html            # Administrative controls
│   └── admin_login.html            # Secure login interface
│
└── static/                         # Static assets
    ├── css/
    │   ├── styleFP.css             # Main dashboard styling
    │   ├── admin_panelSTYLE.css     # Admin panel styling
    │   └── login.css               # Login page styling
    │
    └── js/
        └── scriptFP.js             # Client-side functionality
```

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.7 or higher
- pip (Python package manager)
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Arduino IDE (for hardware setup, optional)

### Step 1: Clone the Repository
```bash
git clone https://github.com/abhishekkumar-code30/LineSaathi.git
cd LineSaathi
```

### Step 2: Install Dependencies
```bash
pip install flask
```

### Step 3: Configure the Application
Edit `app.py` and set your desired admin password (default provided in code).

### Step 4: Run the Flask Server
```bash
python app.py
```

### Step 5: Access the Application
Open your web browser and navigate to:
```
http://127.0.0.1:5000
```

---

## 🔐 Admin Access

### Accessing Admin Panel
1. Navigate to `http://127.0.0.1:5000/admin`
2. Enter the configured admin password
3. Access the administrative dashboard

### Admin Capabilities
- View all system metrics
- Adjust maximum capacity limits
- Reset counters and historical data
- Export occupancy logs for analysis

---

## 🔌 Hardware Integration

### Sensor Architecture

The system uses a dual-sensor approach for accurate occupancy counting:

| Component | Purpose |
|-----------|---------|
| **Entry Sensor (Sensor 1)** | Detects persons entering the monitored area |
| **Exit Sensor (Sensor 2)** | Detects persons leaving the monitored area |
| **Arduino UNO** | Processes sensor signals and communicates with server |

### Operation Flow

```
Person Approaches Sensor 1
  ↓
Arduino Detects Entry → Increments Entry Count (+1)
  ↓
Flask Server Updates Entry Counter
  ↓
Dashboard Refreshes in Real-Time
  
Person Approaches Sensor 2
  ↓
Arduino Detects Exit → Increments Exit Count (+1)
  ↓
Flask Server Updates Exit Counter
  ↓
Current Occupancy = Total Entries - Total Exits
  ↓
Dashboard Displays Updated Occupancy & Metrics
```

### Arduino Configuration

Upload the `Arduino_Code.txt` to your Arduino UNO microcontroller:

1. Open Arduino IDE
2. Load `Arduino_Code.txt`
3. Connect Arduino to computer via USB
4. Select board: Arduino UNO
5. Select appropriate COM port
6. Click "Upload"

The Arduino will begin transmitting sensor data to the Flask server.

---

## 📡 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Serve main dashboard |
| `/data` | GET | Fetch live dashboard metrics (JSON) |
| `/history` | GET | Retrieve historical graph data (JSON) |
| `/admin` | GET | Display admin login page |
| `/admin_panel` | GET | Serve admin control panel (authenticated) |
| `/update_capacity` | POST | Update maximum capacity limit |
| `/reset_count` | POST | Reset current occupancy counter |
| `/reset_counters` | POST | Reset all entry/exit counters |
| `/reset_history` | POST | Clear historical data |
| `/download` | GET | Export system logs (CSV) |

---

## 📊 Data Flow Architecture

```
┌─────────────────────────────────────────────────────────┐
│               Arduino + IR Sensors                       │
│         (Detects Entry/Exit Events)                      │
└──────────────────────┬──────────────────────────────────┘
                       │ (Serial Communication)
                       ↓
┌─────────────────────────────────────────────────────────┐
│          Flask Server (Backend)                          │
│  • Receives sensor data                                  │
│  • Processes occupancy calculations                      │
│  • Generates predictions                                 │
│  • Manages authentication                                │
└──────────────────────┬──────────────────────────────────┘
                       │ (HTTP/JSON)
                       ↓
┌─────────────────────────────────────────────────────────┐
│      Web Dashboard (Frontend)                            │
│  • Real-time metrics display                             │
│  • Interactive charts                                    │
│  • User-friendly interface                               │
└─────────────────────────────────────────────────────────┘
```

---

## 🔧 Configuration

### Environment Variables
Create a `.env` file in the project root (optional):

```env
FLASK_ENV=production
FLASK_DEBUG=False
ADMIN_PASSWORD=your_secure_password_here
MAX_CAPACITY=100
```

### Sensor Calibration
Adjust sensor sensitivity in `Arduino_Code.txt` based on your physical environment:
- Sensor detection range
- Detection threshold values
- Debounce intervals

---

## 📈 Usage Examples

### For End Users
1. **View Current Queue Status:** Open dashboard to see real-time occupancy
2. **Check Wait Time:** View estimated waiting time before visiting
3. **Get Recommendations:** See suggested optimal visit times

### For Administrators
1. **Monitor Trends:** Analyze historical data and peak hours
2. **Adjust Capacity:** Update maximum limits based on venue capacity
3. **Maintain System:** Reset counters as needed for recalibration

---

## 🚀 Future Enhancements

- **Machine Learning Integration:** Advanced prediction models using TensorFlow/PyTorch
- **Mobile Application:** Native iOS and Android apps with push notifications
- **Multi-Location Support:** Manage multiple queues from a single dashboard
- **Cloud Database:** Integration with Firebase/AWS for data persistence
- **Notification System:** SMS/Email alerts for queue status updates
- **Historical Analytics:** Long-term trend analysis and reporting
- **Integration APIs:** RESTful APIs for third-party applications
- **Real-time Alerts:** Automatic notifications when capacity thresholds are reached

---

## 🔒 Security Considerations

- **Password Protection:** All admin functions require authentication
- **Session Management:** Secure session handling for admin access
- **Data Validation:** Input validation on all API endpoints
- **CORS Configuration:** Configured for safe cross-origin requests (as needed)

### Security Recommendations
- Change default admin password immediately after deployment
- Use HTTPS in production environments
- Implement rate limiting on API endpoints
- Regular security audits and updates

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is open-source and available under a custom license. Please refer to the LICENSE file in the repository for complete terms and conditions.

---

## 👨‍💻 Author

**Abhishek Kumar**  
Computer Science Student | IoT & Full-Stack Developer  
[GitHub](https://github.com/abhishekkumar-code30)

---

## 💡 Support & Feedback

If you find this project helpful:

- ⭐ **Star the repository** to show your support
- 🍴 **Fork the project** for your own use case
- 🐛 **Report issues** via GitHub Issues
- 💬 **Suggest improvements** via Pull Requests
- 📧 **Contact the author** for technical questions

---

## 📞 Contact & Communication

For questions, suggestions, or collaboration opportunities:
- Open an Issue in the repository
- Check existing Issues and Discussions first

---

## 🎯 Project Objectives

- Reduce queue waiting times through real-time monitoring
- Improve user experience in high-traffic venues
- Enable data-driven decision making for facility management
- Provide a scalable, cost-effective solution for queue management
- Create an intuitive interface for both end-users and administrators

---

## 📚 References & Resources

- [Flask Documentation](https://flask.palletsprojects.com/)
- [Arduino Documentation](https://www.arduino.cc/en/Guide)
- [Chart.js Documentation](https://www.chartjs.org/)
- [Python Documentation](https://docs.python.org/3/)

---

**LineSaathi – Making Queues Smarter, Faster, and Stress-Free** ✨
