### **Axiom-IPCamera**  
#### *How to add an IP camera to a Raymarine Axiom plotter*

Raymarine offers a range of cameras for their Axiom Pro plotters, but they can cost upwards of **£500**.  
There are ways to connect third-party IP cameras, but existing guides are outdated, and some cameras are discontinued. This guide provides an updated method that worked for me and others that followed the guide.

---

## 📌 **Hardware Requirements**  

### **Plotter:**  
- **Raymarine Axiom Pro 9 and other similar models**  

### **Camera:**  
- *Recommended:* [Gadinan 8MP/5MP/4MP H.265 IP Camera](https://www.aliexpress.com) (Aliexpress)  
  - Supports 4K & H.265, but needs to run on **H.264 at 720p**  
  - Recommended lens: **2.8mm focus** was ideal for my engine room
  - Must support ONVIF with authentication disabled
  - Use the 12v version and not the POE version  

### **Power Over Ethernet (POE) Considerations:**  
- POE cameras require **48V**, which is not readily available on boats  
- Instead, a **12V camera** is used with a [**passive POE injector**](./POE_Injector_Pair.jpeg)

- **Power Source:** 12V near the helm  

### **Network Connection:**  
- Raymarine sells a **Raynet to RJ45 cable** (£50-£80)  
- Alternative: Cut a **Raynet to Raynet cable** (May be in the Axiom box) and crimp an **RJ45 connector**. This will give you 2 cables.
  Follow the wiring in the diagram here [**RJ45**](./RJ45.png).

- This method supports two cameras on Axiom Pro models with 2 spare Raynet inputs without needing a network hub.

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
   
Easy way to test camera at home using VLC.
In VLC: File >> Open Network. Paste in the URL below, but modify based on your actual IP address.
rtsp://192.168.0.210:554/user=admin&password=123456&channel=1&stream=0.sdp?

---

## 🌐 **Camera IP Address Configuration**  

### **Static IP (Recommended for Stability)**
Although Axiom has **DHCP**, and will provide a dynamic IP to the camera, using a **static IP** prevents delays with the image appearing and improves the reliabilty.

#### **Manual IP Settings:**
| Setting          | Value          |
|-----------------|---------------|
| DHCP           | **Disabled** |
| IP Address     | `198.18.2.91` |
| Subnet Mask    | `255.255.248.0` |
| Default Gateway | `198.18.2.46` |
| DNS Server     | `198.18.2.46` |

> *Thanks to forum member "**5TC**" on the [Sealine forum](https://sealineforum.forumotion.com) for discovering and documenting this*
>
> Note: Use of DHCP is possible, however this causes a slight delay when selecting the camera, and when displaying the initial video stream sometimes the stream will disappear after a second.
> Using the recommended IP settings also allows access to the camera web menu via the Axiom settings and network page.

---

## 🛠 **Camera Firmware**
My Gadinan camera has firmware version v1.08.  
In May 2025 they were shipping V1.14.91 which also works.  
Later firmware may cause issues.


---

## 💰 **Parts and Cost Breakdown**  

| Item | Description | Price |
|------|------------|-------|
| **Camera** | Gadinan 8MP/5MP/4MP H.265 IP Camera (12V version, NOT POE) | **£25.00** |
| **RJ45 Female-to-Female** | Needed for connecting Power injector RJ45 to Ethernet cable at helm end of cable | **£3.00** |
| **Passive POE Adapter set** | Helm end - Injector: RJ45 Male + Power In to RJ45 Female Splitter. Camera end - RJ45 Female to RJ45 Male + Power Out. For 12v injection to feed camera| **£5.00** |
| **Raynet to RJ45 Cable** | Alternative: Cut & crimp Raynet cable (May be supplied with Axiom) | **£50.00** |
| **DC Power Cable** | 2.1mm x 5.5mm Male-to-Male (1M) | **£2.00** |
| **Cat5/Cat6 Ethernet** | Choose one long enough to route from helm through boat to camera | **£10.00** |

> *The camera is from Aliexpress. eBay and Amazon good sources for the other items*  





## **Updates from the Pontoon** 

Some users have kindly provided feedback via the Sealine Forum and the YBW forum.
I will try to collate all information here.

Be aware that Raymarine and the camera manufacturers can change their firmware at any time which can then cause the camera to stop working.

**DipperToo** from YBW forum reports success with SV3C camera 806POE-5MP-HX. This is a POE camera which he powers using a Teltonika automotive switch (Teltonika TSW101). Full description: SV3C 5MP PoE CCTV Security Camera Outdoor, Cameras House Security with 20M IR Night Vision, Security IP Camera Outdoor with Human/Vehicle Detection, Build-in MIC, SD card & Cloud, Waterproof, No WIFI.

**Kendal** from YBW reports success with a Dahua nv-ib2b40-zs on Axiom 7.

**AngusMcDoon** from YBW wrote an article in 2022 that pre-dates this page. His page also explains how to use a 12v Ethernet Switch (**Brainbox SW-005**) to connect multiple devices over the network [Link to YBW](https://forums.ybw.com/threads/raymarine-axiom-camera-connection-yapp.588531/)

Another resource which is from 2019 is here [Link](https://panbo.com/broad-ip-camera-support-a-raymarine-advantage/) The author has 7 cameras connected into the Axiom Plotter and has also setup on the network a surveillance server based on Blue Iris.
