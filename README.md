# PlantEra
A Smart Growing System for Plant Cuttings and Seedlings

# Project Overview
  PlantEra is an automated plant propagation system designed to help maintain suitable environmental conditions for plant cuttings and seedlings. It uses sensors and automated mechanisms to monitor and regulate humidity, temperature, soil moisture, and lighting.
The system integrates hardware components with a web-based platform, allowing users to monitor plant conditions, view live camera footage, manage settings, and access daily reports. PlantEra aims to reduce manual maintenance and improve the survival rate of plant cuttings and seedlings through automation.

# Features
1. Automated Humidity Control – Uses a mister and automatic ventilation to maintain humidity levels between 85% and 95%.
2. Temperature Monitoring – Monitors temperature and controls fans and ventilation to maintain suitable conditions.
3. Automatic Watering – Uses soil moisture sensors to determine when watering is needed.
4. Smart Lighting – Monitors light conditions and activates grow lights when additional lighting is needed.
5. Real-Time Monitoring – Displays humidity, temperature, soil moisture, and light readings through the website.
6. Live Camera Viewing – Allows users to remotely view the plants inside the propagation box.
7. Daily Reports – Records power consumption, water usage, system activities, and errors.
8. Device Management – Allows users to manage their devices and adjust environmental settings.
9. Offline Operation – Continues monitoring and controlling the growing environment even without an internet connection.

# System Architecture

# Hardware Requirements
- Orange Pi Zero 3 controller
- Temperature, humidity, soil, and light sensors
- Mister, dosing dumps, fans, and vent gate
- Grow light and 1080p USB camera
- Local device portal for offline control

# Software Requirements
1. Frontend
- Next.js with App Router
- React with custom hooks
- Tailwind CSS with CSS variables for Light & Dark mode
- HTML5 Canvas API for particle burst animations
- SVG Components for historical climate graphs and custom cursors
- Lucide React for hardware interface icons

2. Backend & Auth
- Next.js Server Actions & API Routes for local telemetry ingestion and hardware toggles
- Better Auth for local user sessions, registration, and access control

3. Database
- Drizzle ORM for schema definitions and type-safe database queries
- PostgreSQL (Local / Containerized) for persistent telemetry, hardware profiles, and local order requests

5. Embedded Hardware & IoT
- Armbian Linux OS running directly on Orange Pi Zero 3
- Python 3.x / Node.js runtime for local sensor loops and relay actuation
- gpiod & I2C/SPI drivers for sensor polling and relay control (mister, fan, grow light)
- fswebcam / OpenCV utility for periodic 1080p local snapshot capture
- FastAPI / Express for offline hardware API endpoints

5. Local Hosting & Deployment
- Node.js Runtime & PM2 for process management and continuous local Next.js server execution
- Docker & Docker Compose for self-contained deployment of the web app and database on local hardware
- Local Area Network (LAN) / mDNS for local IP and hostname access 
- pnpm / npm for local dependency and package management

# How it Works
  PlantEra relies on an embedded hardware-to-software architecture designed to maintain an optimal propagation environment for delicate plant cuttings and seedlings:

1. Environmental Sensing: Integrated sensors continually measure four core environmental variables inside the propagation box: relative air humidity, ambient temperature, soil moisture percentage, and ambient light intensity.
2. Automated Regulation: The Orange Pi Zero 3 controller compares live sensor readings against target threshold profiles. When humidity drops or temperatures rise, the system triggers hardware actuators:

- Ultrasonic Mister: Disperses fine mist into the air to prevent leaf desiccation before roots develop.
- Airflow Fan & Vent Gate: Circulates air and vents excess heat to avoid stagnant humidity or thermal buildup.
- Grow Light & Dosing Pump: Regulates light cycles and soil hydration on automated schedules.

3. Visual Progress Tracking: An internal 1080p USB camera captures periodic snapshots of the propagation space, allowing users to observe root emergence (e.g., Root Watch tracking) without opening the sealed enclosure.

# Website Features
| Feature | Category | Description |
|---|---|---|
| **Hero & Dynamic Typing Header** | Presentation | Interactive hero section featuring a dynamic typing title effect, quick hardware statistics, and floating telemetry chips showing live humidity (91%) and root growth progress (Day 9 Root Watch). |
| **Live Environment Monitor** | Dashboard | Real-time climate overview panel rendering live readings for Humidity, Temperature, Soil, and Light status with optimal indicator tags. |
| **Interactive Climate Graph** | Data Visualization | SVG-based trend chart visualizing 20-hour historical relative humidity data. |
| **Manual Device Override Controls** | System Control | Interactive toggle switches allowing users to remotely turn the Mister, Fan (with rotation animation), and Grow Light on or off, accompanied by real-time status toast notifications. |
| **No-Payment Order Request System** | E-Commerce / Leads | Pre-order request form (`/order`) capturing client details, quantity, delivery address, setup options, and custom notes without requiring upfront credit card or gateway payment. |
| **Interactive FAQ Accordion** | Documentation | Expandable accordion answering common customer queries regarding offline capability, enclosure capacity, setup procedures, and payment workflows. |
| **Direct Contact & Inquiry Form** | Support | Inquiry submission form sorted by topic (System Setup, Delivery, Growing Advice, Other) alongside direct contact channels (Email, Viber/Phone, Batangas location). |
| **Interactive Visual Particle Effects** | UI/UX | Custom SVG leaf cursor state (forest green default, bright lime on hover), HTML5 Canvas circular shockwave particle bursts on pointer-down events, and scroll-triggered falling leaves animation. |
| **Growth Visualizer Loading Screen** | UI/UX | Animated plant growth progression screen tracking load stages from seed sprouting to full bloom. |
| **Light & Dark Theme Toggle** | Design | Theme switching between warm greenhouse paper/terracotta light mode and dark moss greenhouse mode. |

# Scope and Limitations
1. Scope
- Target Application: Specially engineered for small-scale vegetative propagation (cuttings, seedlings, and fragile tropical plant species).
- Capacity: Standardized enclosure size designed to comfortably house 6 to 10 plant cuttings per unit to ensure adequate airflow and clear camera visibility.
- Hardware Integration: Configured to interface with an Orange Pi Zero 3 controller, 1080p USB camera, ultrasonic mister, dosing pump, ventilation fan, adjustable vent gate, grow lights, and multi-sensor array (temperature, humidity, soil moisture, light).
- Authentication & Database Architecture: Includes schema specifications (built with Drizzle ORM and PostgreSQL) supporting user account creation, session management, email verification, and client authentication (via Better Auth).
- Local Autonomy: Complete functional autonomy ensuring that misting schedules, ventilation pulses, and sensor triggers continue operating even during network outages.

2. Project Limitations
- No Online Payment Gateway: The website does not handle direct financial transactions or credit card processing; all orders are submitted as pre-order requests requiring direct team confirmation prior to fulfillment.
- Single-Unit Scale: Optimized for individual propagation boxes rather than high-volume commercial farm or industrial greenhouse scale.
- Hardware Dependency: Real-time telemetry monitoring and manual device toggles require physical connection to an active PlantEra hardware unit; frontend displays use simulated telemetry when un-paired.
- Camera Functionality: Camera view relies on still snapshot capture intervals rather than low-latency high-FPS video streaming.
  
# Screenshots


# Project Team
## Project Team

| Name | Role |
|---|---|
| Jeremiah Sulit | Project Manager, Frontend Developer |
| Andrei Brian Mohammad Said | Backend Developer, Hardware/IoT Developer |
| Justine Babasa | Documentation Specialist, Quality Assurance Tester |
| Ranze Dimaala | Frontend Developer, UI/UX Designer |
| Aaron Aguda | Documentation Specialist |
| Trishtan De Roxas | Documentation Specialist, System Analyst |

