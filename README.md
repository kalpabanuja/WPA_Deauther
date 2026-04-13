# 📡 WPA Deauther

> **Simple Wireless Pentest Assistant built using the RTL8720DN BW16 kit.**

---

## 🎯 Features

### 🔴 Red Teaming
* **Wireless Network Detector / Radar:** Scans BLE, 2.4GHz, and 5GHz Wi-Fi with deep-dive details of individual networks.
* **Wi-Fi FoxHunting:** Physically track and locate the source of target networks.
* **Deauthing Attacks:** Selectively target a single user, a single network, or perform a mass deauth on all surrounding networks.
* **Beacon Spamming:** Flood the area with fake access points to confuse targets.
* **Beacon Spoofing:** Clone existing access points.
* **4-Way Handshake Capture:** Intercept and capture WPA/WPA2 handshakes for offline cracking.

### 🔵 Blue Teaming
* **Wi-Fi Analyzer:** Monitor the surrounding RF environment and channel congestion.
* **Attack Detection:** Identifies active Spoofing, Deauthentication, and Evil Twin attacks in your vicinity.

### ⚙️ Advanced Capabilities
* **Fully Customizable Attacks:** Adjust Reason Codes, Burst Counts, Attack Delays, and more to fine-tune your pentest.
* **Display Management:** Built-in brightness adjustment.
* **Detection Logging:** Keeps a history of detected attacks (logs are cleared automatically upon reboot).
* **Customizable Access Point:** Set your own AP Name and Password for secure access to the device when downloading .pcap files.

---

## 🛠️ Hardware & Wiring

### Required Components
* **RTL8720DN BW16 Kit**
* **1.8-Inch TFT Display** (128x160 resolution; any display supporting the `Adafruit_ST7735` library will work)
* **3x Push/Tactile Buttons**

### Wiring Diagrams

#### BW16 Board ➡️ TFT Display
| BW16 Pin | TFT Pin | Description |
| :--- | :--- | :--- |
| **VCC** | V3.3 | Power |
| **GND** | GND | Ground |
| **P15** | CS | Chip Select |
| **P26** | RESET | Reset |
| **P25** | AO / DC | Data/Command |
| **P12** | SDA | Serial Data |
| **P14** | SCK | Serial Clock |
| **A30** | LED | Backlight Control |

> ⚠️ **Troubleshooting Tip (Breadboard Setup)**: If you experience random dots appearing on the screen, screen crashing, or flickering, isolate the **A30 -> LED** wire. Moving it away from other active wires usually resolves interference issues.

#### BW16 Board ➡️ Buttons
| BW16 Pin | Button Action | Destination |
| :--- | :--- | :--- |
| **PB3** | OK / Select | Button 1 ➡️ GND |
| **PB2** | UP | Button 2 ➡️ GND |
| **PB1** | DOWN | Button 3 ➡️ GND |

---

## ❓ Frequently Asked Questions (FAQ)

**What do the Reason Codes do?**
> I have attached a text file in the repository explaining the specific reason codes available on the WPA Deauther and how they affect the target.

**What does a "Two-Way" attack do?**
> Instead of only attacking the access point (router), a two-way attack targets *both* ends of the connection (the user and the router). This makes the deauthentication significantly more effective and harder to ignore.

**How can I retrieve a captured 4-Way Handshake?**
> 1. After running the `Config+Deauth` function, the device will host an Access Point (AP) and display an IP address on the screen.
> 2. To maintain stealth during a pentest, this network is set as a **Hidden Network** so everyone around you cannot see it.
> 3. On your laptop or phone, go to your Wi-Fi settings and select "Add a Network" (or look under "Hidden Networks").
> 4. Enter the custom AP name and password you configured, then press OK.
> 5. Once connected, navigate to the provided IP address in your web browser to download the `.pcap` file.

**I connected to the AP and went to the IP address/URL address, but its not downloading the `.pcap` file. Why?**
> Simply turn off your mobile data and refresh the webpage. Your phone might be trying to route the local IP traffic through your cellular network instead of the Deauther.

**How do I exit a function while it is running?**
> For some functions, simply press the **OK** button once. For others, you may need to press and hold the **OK** button to force an exit.

**Will you be adding more functions in the future?**
> Yes! Future updates will include advanced features such as network scanning (similar to Nmap) and active Evil Twin attacks of cause BLE Jamming(I personally got zero interests in BLE jamming that's why I haven't implemented it into my project).

**Why do 5GHz deauth attacks sometimes fail?**
> The deauther works perfectly on standard networks, but 5GHz networks utilizing the newer **WPA3** standard have built-in protections against traditional management frame attacks. While there isn't a universally stable method to deauth WPA3 yet, I am currently researching bypass methods and will implement them into the code soon.

---

## 📬 Contact & Support
Got questions, suggestions, or need help troubleshooting? You can reach out to me through our Telegram group:
[Join the Telegram Group](https://t.me/+z9nlOraUsKUxNTU9)
