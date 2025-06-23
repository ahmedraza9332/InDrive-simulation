# InDrive Simulation 🚗

A comprehensive C++ console application that simulates the InDrive ride-hailing platform, featuring real-time price negotiation between customers and drivers across different vehicle types.

## 📋 Table of Contents
- [Features](#features)
- [System Requirements](#system-requirements)
- [Installation & Setup](#installation--setup)
- [How to Use](#how-to-use)
- [Project Structure](#project-structure)
- [Technical Implementation](#technical-implementation)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### Core Functionality
- **User Authentication**: Login and signup system with persistent data storage
- **Multi-Vehicle Support**: Choose between Bike, Car, and Rickshaw rides
- **Dynamic Pricing**: Real-time fare calculation based on distance and vehicle type
- **Price Negotiation**: Interactive bidding system between customers and drivers
- **Ride History**: Track and view past 5 rides (automatic queue management)
- **Location-Based Matching**: Drivers matched based on pickup location

### Advanced Features
- **Floyd-Warshall Algorithm**: Optimized shortest path calculation for 12+ locations
- **Dynamic Driver Pool**: Randomly generated drivers (20-80 per vehicle type)
- **Rating System**: Driver ratings from 3.0 to 5.0 stars
- **Input Validation**: Comprehensive error handling and user input validation
- **File Persistence**: User data and ride history saved to local files

## 🖥️ System Requirements

- **Operating System**: Windows (uses Windows-specific libraries)
- **Compiler**: C++11 or later (GCC, MinGW, Visual Studio)
- **RAM**: Minimum 2GB
- **Storage**: 50MB free space for data files

## 🚀 Installation & Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/ahmed9332/indrive-simulation.git
   cd indrive-simulation
   ```

2. **Compile the Project**
   ```bash
   # Using GCC/MinGW
   g++ -std=c++11 indrive_simulation.cpp -o indrive_simulation.exe
   
   # Using Visual Studio (Developer Command Prompt)
   cl indrive_simulation.cpp
   ```

3. **Run the Application**
   ```bash
   ./indrive_simulation.exe
   ```

## 📖 How to Use

### Getting Started
1. **Launch** the application
2. **Choose** between Login (existing user) or Signup (new user)
3. **Enter** your credentials (name, phone number, age for signup)

### Booking a Ride
1. **Select** "Book a ride" from the main menu
2. **Choose** pickup location from 12 available locations
3. **Select** drop-off destination
4. **Review** estimated fares for all vehicle types:
   - **Bike**: Base fare PKR 50 + PKR 15/km
   - **Rickshaw**: Base fare PKR 70 + PKR 35/km  
   - **Car**: Base fare PKR 100 + PKR 50/km
5. **Choose** your preferred vehicle type
6. **Enter** your desired fare amount
7. **Negotiate** with available drivers or add PKR 5 to your offer
8. **Select** a driver and enjoy your ride!

### Available Locations
- FAST University
- Gulshan-e-Iqbal
- Defence Housing Authority
- Saddar
- Nazimabad
- Bahria Town
- Scheme 33
- PECHS
- Malir
- Korangi
- Gadap
- Lyari

## 🏗️ Project Structure

```
indrive-simulation/
│
├── indrive_simulation.cpp    # Main source code
├── data/                     # Auto-generated user data directory
│   └── [username][phone].txt # Individual user files
├── README.md
└── .gitignore
```

### Key Classes

- **Customer**: Handles user data, booking logic, and ride history
- **Driver** (Abstract): Base class for all driver types
  - **Bike**: Bike drivers (PKR 20-40 negotiation range)
  - **Car**: Car drivers (PKR 80-150 negotiation range)  
  - **Rickshaw**: Rickshaw drivers (PKR 40-80 negotiation range)
- **Ride**: Stores individual ride information

## ⚙️ Technical Implementation

### Algorithms Used
- **Floyd-Warshall Algorithm**: Calculates shortest distances between all location pairs
- **Dynamic Programming**: Optimizes route planning and fare calculation
- **Object-Oriented Design**: Polymorphism for different driver types
- **STL Containers**: Vectors, lists, and unordered_maps for efficient data management

### Data Structures
- **Hash Maps**: Fast location-to-distance lookups
- **Vectors**: Dynamic driver storage
- **Linked Lists**: FIFO queue for ride history (max 5 rides)
- **File I/O**: Persistent user data storage

### Design Patterns
- **Inheritance**: Driver class hierarchy
- **Polymorphism**: Virtual negotiation methods
- **Encapsulation**: Private data members with public interfaces
- **Friend Functions**: Operator overloading for ride display

## 🎯 Key Features Breakdown

### Negotiation System
- Customers set their desired price
- Drivers counter-offer based on vehicle type and base rates
- Interactive bidding with PKR 5 increment option
- Automatic acceptance if customer offer exceeds driver threshold

### Fare Calculation
```cpp
// Example fare calculation
Base Fare + (Distance × Rate per KM)
Bike: PKR 50 + (distance × PKR 15)
Car: PKR 100 + (distance × PKR 50)  
Rickshaw: PKR 70 + (distance × PKR 35)
```

### Data Persistence
- User profiles saved to individual text files
- Ride history maintained across sessions
- Automatic data directory creation

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Areas for Improvement
- Cross-platform compatibility (remove Windows-specific code)
- GUI implementation using Qt or similar framework
- Database integration (MySQL/PostgreSQL)
- Real-time GPS integration
- Payment gateway simulation
- Driver earnings tracking
- Advanced routing algorithms

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Your Name** - *Initial work* - [YourGitHub](https://github.com/yourusername)

## 🙏 Acknowledgments

- Inspired by the real InDrive application
- Built as a academic project demonstrating OOP concepts
- Special thanks to the C++ community for documentation and support

---

**Note**: This is a simulation project for educational purposes. It demonstrates various programming concepts including object-oriented programming, data structures, algorithms, and file handling in C++.
