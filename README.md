### **Axiom-IPCamera**  
#### *How to add an IP camera to a Raymarine Axiom plotter*

Raymarine offers a range of cameras for their Axiom Pro plotters, but they can cost upwards of **£500**.  
There are ways to connect third-party IP cameras, but existing guides are outdated, and some cameras are discontinued. This guide provides an updated method.

---

## 📌 **Hardware Requirements**  

### **Plotter:**  
- **Raymarine Axiom Pro 9**  

### **Camera:**  
- *Recommended:* [Gadinan 8MP/5MP/4MP H.265 IP Camera](https://www.aliexpress.com) (Aliexpress)  
  - Supports **4K** & **H.265**, but needs to run on **H.264 at 720p**  
  - Recommended lens: **2.8mm focus**  

### **Power Over Ethernet (POE) Considerations:**  
- POE cameras require **48V**, which is not readily available on boats  
- Instead, a **12V camera** is used with a **passive POE injector**  
- **Power Source:** 12V near the helm  

### **Network Connection:**  
- Raymarine sells a **Raynet to RJ45 cable** (£50-£80)  
- Alternative: Cut a **Raynet to Raynet cable** (included with Axiom) and crimp an **RJ45 connector**  
- This method supports **two cameras** without needing a network hub  

---

## 🛠 **Camera Setup & Configuration**  

1. **Configure the Camera on a PC First**  
   - Default login credentials (check the box or manual):  
     ```
     Username: admin
     Password: 123456 / password / admin
     ```
   - **Disable On-Screen Date/Time** (as the camera lacks internet access)  
   - **Enable ONVIF**  
   - **Disable ONVIF Authentication** (necessary for Axiom compatibility)  

2. **Video Stream Settings**  
   - **Encoding:** H.264  
   - **Resolution:** 1280x720  
   - **Quality:** Medium  
   - **RTSP Authentication:** Disabled  
   - **RTSP Port:** 554  

---

## 🌐 **IP Address Configuration**  

### **Static IP (Recommended for Stability)**
Although Axiom has **DHCP**, using a **static IP** prevents delays and camera disconnections.

#### **Manual IP Settings:**
| Setting          | Value          |
|-----------------|---------------|
| DHCP           | **Disabled** |
| IP Address     | `198.18.2.91` |
| Subnet Mask    | `255.255.248.0` |
| Default Gateway | `198.18.2.46` |
| DNS Server     | `198.18.2.46` |

> *Thanks to forum member "5TC" on the Sealine forum for discovering this!*  

---

## 💰 **Cost Breakdown**  

| Item | Description | Price |
|------|------------|-------|
| **Camera** | Gadinan 8MP/5MP/4MP H.265 IP Camera (12V version, NOT POE) | **£25** |
| **RJ45 Female-to-Female** | Needed for connection | **£3** |
| **Passive POE Adapter** | For 12V power transmission | **£1.67** |
| **Raynet to RJ45 Cable** | Alternative: Cut & crimp Raynet cable | **~£50** |
| **DC Power Cable** | 2.1mm x 5.5mm Male-to-Male (1M) | **~£2** |

---

## ✅ **Conclusion**  

By following this guide, you can successfully integrate an affordable **IP camera** with a **Raymarine Axiom plotter**—saving **hundreds of pounds** compared to official Raymarine cameras!  

---

Would you like any additional images, diagrams, or further refinements? 🚀

