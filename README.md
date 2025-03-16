# Axiom-ipcamera
How to add IPcamera to Raymarine Axiom plotter

Raymarine do a nice range of cameras for their Axiom Pro plotters – problem is, they are upwards of £500.

There are a few writeups out there where people have connected cheap IP cameras to the plotter, but they are about 2 years old, some of the information is in multiple places and the cameras are discontinued. The camera referenced in this write up will also become discontinued at some point in the future, so if you have a plan to do this, buy the camera referenced soon.

Plotter:
Axiom Pro 9

Camera:
There are loads out there on ebay and Aliexpress, 1 first one I bought didn’t work (black screen on the plotter), but the 2nd one I bought, did work.
This one is from Aliexpress and seems to work fine: Gadinan 8MP 5MP 4MP H.265 IP Camera
Although it is a 4k camera with H265, it needs to be run on H264 at 720.  I bought the one with a 2.8mm focus.

POE:
Power over Ethernet means the camera is powered by the network cable, so no requirement to run separate power to the camera, however POE is 48v, which is not available on a boat without converters etc.
A camera without POE was chosen. This type of camera has a single lead coming out that splits into an ethernet female and a DC connector. This requires 12v.
A passive POE injector at both ends will allow 12v to run to the camera. 12V will be supplied from somewhere near the helm.

Axiom Network:
Axiom sells a Raynet to RJ45 cable, they are £50-£80 depending on length.
There is a Raynet to Raynet cable in the Axiom box. This can be cut in half and a RJ45 can be crimped on the end. This will yield 2 cables, and therefore support 2 cameras without a network hub.
The RJ45 diagram for this is shown later.

Camera setup:
Axiom is fussy, firstly relating to authentication and then the stream settings.  
The 3rd party camera needs some configuration and some cameras will just not work.
Settings are show later, but essentially set the camera for H264, 1280x720 and a medium quality level.
You need to configure the camera on a PC, before attempting to connect it to the Axoim. Password for the web admin will be admin:123456 or admin:password or admin:admin, will be on the box somewhere.
Turn off date and time in the On screen display – the camera will not be able to connect to the internet to get the correct date/time, so you don’t want 1st Jan 1970 being shown on the display.
You may want to turn on the camera name, eg Port Engine etc.
Turn on ONVIF
Disable ONVIF authentication
ONVIF compatibility is very important, the Axiom needs to be able to access the stream without authenticating. Disabling ONVIF is a security risk, but not an issue on this closed network.
RTSP Auth Enable – Not Enabled
RTSP Port 554

IPaddress:
The Axiom provides DHCP so althought it is just a case of plugging the camera in and the Plotter will find the camera, it was found that a fixed IP address was more reliable.
Using DHCP there was a pause when selecting the camera and sometimes the camera would go blank. When using a fixed IPaddress these issues went away.

Cost:
Gadinan 8MP/5MP/4MP H.265 IP Camera. Choose 12v version and not POE version £25. (Aliexpress)
RJ45 Female to Female: £3
Passive POE Adaptor: £1.67
Raynet to Raynet cable, or Raynet to RJ45 Cable (about £50)
2.1mm x 5.5mm DC Connector Male to Male Power Cable 1Mtr (about £2)
