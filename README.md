# 🚀 LineSaathi - Smart Queue Intelligence System

> **Skip the wait, beat the rush!** Real-time queue monitoring that makes waiting smarter and faster.

A smart IoT-based queue management system that shows you exactly how crowded a place is, how long you'll wait, and the best time to visit. Perfect for college mess, cafeterias, service counters, and events!

## 🎯 The Problem We Solve

Tired of standing in long queues? Not sure if it's worth going right now? **LineSaathi solves this!**

- 📊 See LIVE how many people are in the queue
- ⏳ Get realistic wait time estimates
- 🎯 Know the best time to visit
- 👨‍💼 Admins can manage capacity easily

---

## ✨ What Can You Do?

### 👤 For Users
- **Live Dashboard** 📱
  - See current crowd level (Low/Medium/High)
  - Visual capacity bar - how full is the queue?
  - Real-time entry/exit tracking
  
- **Smart Insights** 🧠
  - Estimated waiting time
  - 15-minute crowd prediction ("Will it get busier?")
  - Automatic rush hour detection
  - Best time to visit suggestions

### 👨‍💼 For Admins
- **Control Panel** 🎛️
  - Set maximum capacity
  - Reset counters anytime
  - Clear historical data
  - Secure login system

### 🎨 User Interface
- **Light & Dark Mode** 🌙☀️
- **Beautiful Design** - Modern glassmorphism + premium black-gold theme
- **Works Everywhere** - Desktop, tablet, mobile (fully responsive)

---

## 🛠️ How It's Built

**Frontend (What You See):**
- HTML5, CSS3, JavaScript
- Chart.js for graphs

**Backend (The Brain):**
- Python + Flask (lightweight web server)

**Hardware (The Sensors):**
- Arduino UNO microcontroller
- 2 IR Sensors (detect entry/exit)
- Breadboard + Jumper wires

---

## 📁 File Structure

```
LineSaathi/
├── app.py                      ← Main application (run this!)
├── Arduino_Code.txt            ← Code for Arduino sensor board
│
├── templates/                  ← HTML pages
│   ├── index.html              (Main dashboard)
│   ├── admin_panel.html        (Admin controls)
│   └── admin_login.html        (Admin login)
│
└── static/                     ← Styling & scripts
    ├── css/
    │   ├── styleFP.css
    │   ├── admin_panelSTYLE.css
    │   └── login.css
    └── js/
        └── scriptFP.js
```

---

## 🚀 Quick Start (5 minutes)

### What You Need
- Python 3.7 or higher
- Any modern browser
- (Optional) Arduino IDE if setting up hardware

### Step 1️⃣ - Get the Code
```bash
git clone https://github.com/decodermayank/LineSaathi.git
cd LineSaathi
```

### Step 2️⃣ - Install & Run
```bash
pip install flask
python app.py
```

### Step 3️⃣ - Open in Browser
```
http://127.0.0.1:5000
```

✅ **Done!** You'll see the live dashboard.

---

## 🔐 Admin Access

1. Go to: `http://127.0.0.1:5000/admin`
2. Enter password (set in `app.py`)
3. Control capacity, reset counters, manage the system

---

## 🔌 Hardware Setup (Optional)

Want to connect actual sensors? Here's how:

**What You'll Connect:**
- **Entry Sensor** → Counts people coming in
- **Exit Sensor** → Counts people going out  
- **Arduino** → Talks to your server

**How It Works:**
```
Person enters → Sensor 1 triggers → Arduino counts → Server updates → Dashboard shows!
```

**To Upload Code:**
1. Open Arduino IDE
2. Load `Arduino_Code.txt`
3. Connect Arduino via USB
4. Click Upload

That's it! Sensors will start feeding data.

---

## 📡 Main Features Explained

**Dashboard** - See live data
- Current occupancy & capacity
- Entry/exit counts
- Crowd level (Low/Medium/High)
- Wait time estimate
- Crowd prediction

**Predictions** - Smart insights
- "It will be busier in 15 mins" 
- "Rush hour is 1-3 PM"
- "Come back at 4 PM for shorter wait"

**Admin Panel** - Control everything
- Update max capacity
- Reset counters
- Clear historical data
- Secure login

---

## ⚙️ Configuration

Just edit `app.py` and change:
- `ADMIN_PASSWORD` - Your admin login password
- `MAX_CAPACITY` - Maximum people allowed
- Other settings as needed

No complex setup needed!

---

## 🚀 What's Next? (Future Ideas)

- 🤖 Better AI predictions using machine learning
- 📱 Mobile app (iOS & Android)
- 🌍 Manage multiple locations from one dashboard
- ☁️ Cloud storage for long-term data
- 🔔 Notifications when queue gets too long
- 📊 Detailed analytics & reports
- 🔌 APIs for other apps to use
- ⚡ More powerful alerts & notifications

---

## 🔒 Security

✅ Password-protected admin panel  
✅ Secure session management  
✅ Input validation on all forms  

**Tips for Production:**
- Change default password immediately
- Use HTTPS in production
- Add rate limiting
- Regular security checks

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
