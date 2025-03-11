# Chapter 13 - Wireless and Mobile Security

---

## Domain 2.0: Threats, Vulnerabilities, and Mitigations

**2.3. Explain various types of vulnerabilities.**

- Mobile device (Side loading, Jailbreaking)

## Domain 3.0 Security Architecture

**3.3. Compare and contrast concepts and strategies to protect data.**

- General data considerations (Geolocation)

## Domain 4.0 Security Operations

**4.1. Given a scenario, apply common security techniques to computing resources.**

- Hardening targets (Mobile devices, Workstations, Switches, Routers, Cloud infrastructure, Servers, ICS/SCADA, Embedded systems, RTOS, IoT devices).
- Wireless devices (Installation considerations (Site surveys, Heat maps))
- Mobile solutions (Mobile device management (MDM), Deployment models (Bring your own device (BYOD), Corporate-owned, personally enabled (COPE), Choose your own device (CYOD)), Connection methods (Cellular, Wi-Fi, Bluetooth)) 
- Wireless security settings (Wi-Fi Protected Access 3 (WPA3), AAA/Remote Authentication Dial-in User Service (RADIUS), Cryptographic protocols, Authentication protocols)

---

# Building Secure Wireless Networks

- Wi-Fi, Bluetooth, Cellular, Zigbee, and others

## Connection Methods

### Cellular

- LTE, 4G, 5G

### Wi-Fi

- 2.4 GHz, 5 GHz
- Multiple channels 

| **Wi-Fi standard** | **Generation name**  | **Maximum speed** | **Frequencies**          |
| ------------------ | -------------------- | ----------------- | ------------------------ |
| 802.11b            |                      | 11 Mbit/s         | 2.4 GHz                  |
| 802.11a            |                      | 54 Mbit/s         | 5 GHz                    |
| 802.11g            |                      | 54 Mbit/s         | 2.4 GHz                  |
| 802.11n            | Wi-Fi 4              | 600 Mbit/s        | 2.4 GHz and 5 GHz        |
| 802.11ac           | Wi-Fi 5              | 6.9 Gbit/s        | 5 GHz                    |
| 802.11ax           | Wi-Fi 6 and Wi-Fi 6E | 9.6 Gbit/s        | 2.4 GHz, 5 GHz and 6 GHz |
| 802.11be           | Wi-Fi 7              | 40+ Gbit/s        | 2.4 GHz, 5 GHz and 6 GHz |

- Security features
	- WPA2
	- WPA3
- Encryption
- Protection for network frames
- Authentication

- Service Set Identifiers (SSID)
	- Identify network name

### Bluetooth

- 2.4 GHz
- Low-power
- Short-range
- Point-to-point
- *Pairing*
- Support encryption (weak)
	- Relies on PIN

- Security modes
	- Mode 1: No security (non-secure)
	- Mode 2: Service-level enforced security
	- Mode 3: Link-level enforced security
	- Mode 4: Standard pairing with Security Simple Pairing (SSP)

### RFID

- Radio Frequency Identification
- Relatively short-range (from some centimetre to 100m for active tag)
- Tag and a receiver
- Deploy
	- Active tags (own power, always send signals)
	- Semi-active tags (battery, activated by receiver)
	- Passive tags (powered by receiver)
- Frequency
	- Low-frequency
		- Short-range
		- Low-power
		- Entry access and identification purposes
	- High-frequency
		- Longer readable range (meter)
		- Near-Field Communication (NFC) 
		- Tags 
			- Read-only
			- Write-only
			- Rewritable
	- Ultra-High-frequency
		- Fastest 
		- Longest range
		- Inventory
		- Antitheft purpose

### GPS

- Global Positioning System
- Satellites send out GPS signals
- Received by a compatible GPS receiver
- GLONASS (Russian), Galileo (EU)
- Provide a consistent *time signal* 
- GPS signals
	- Jammed or spoofed
- Geolocation
	- Location-aware authentication
	- Geofencing
- Combined with other location-centric data
	- Wi-Fi network names
	- Bluetooth 

>[!TIP] The following technologies are not in the exam outline as topics, but remain in the glossary or have related items on the exam.

### NFC

- Near-Field Communication
- Short-range
- Apple Pay
- Low-bandwidth 
- Issue
	- Intercepting NFC traffic
	- Replay attacks
	- Spoofing attacks
- Must ensure
	- Not respond to queries except when desired

### Infrared

- IR
- Only work in line of sight
- From very low-bandwidth to gigabit speeds
- Traffic can be captured by anything with a line of sight to it

## Wireless Network Models

- Major connection models
	- Point-to-point
	- Point-to-multipoint
	- Mesh
	- Broadcast

>[!TIP] Exam outline considers three major connection models: cellular, Wi-Fi, and Bluetooth. Make sure that you're aware of the major features, advantages, and disadvantages of each, and think about what they mean for the security of your organization.

## Attacks Agains Wireless Networks and Devices

### Evil Twins and Rogue Access Points

- **Evil Twin** malicious illegitimate access point
	- Appear to be legitimate
		- Copy legitimate SSID
	- Attacker capture all of the victim's network traffic
		- May presenting false version of websites
		- Quick way to capture credentials

- **Rogue access points**
	- AP added to network
	- Offer a point of entry to attackers

- Defence
	- Modern enterprise **Wireless controller systems**
		- Detect new AP in areas where they are deployed
	- **Wireless intrusion detection** systems
		- Scan for unknown AP

### Bluetooth Attacks

- **Bluejacking**
	- **Sends unsolicited messages** to Bluetooth-enabled devices
- **Bluesnarfing**
	- **Unauthorized access** to a Bluetooth device
	- Gathering information

- **Bluetooth Impersonation Attacks (BIA)**
	- Take advantage of weakness in the Bluetooth specification
	- Exploit
		- Lack of mutual authentication
		- Authentication procedure downgrade options
		- Ability to switch roles

- Secure
	- Turn off
	- Change default pairing code
	- Patches

### RF and Protocol Attacks

- Who want to conduct evil twin attacks
- Or want systems to disconnect from a wireless network
- Disassociation attacks and jamming

- **Disassociation**
	- Device disconnects from an AP
	- Wireless attack work better if the target system can be forced to disassociate from initial AP
		- Cause the system to attempt to reconnect
	- Providing an attacker
		- Set up a more powerful evil twin
		- Capture information as the system tries to reconnect

- Best wat to disassociate
	- Send a **deauthentication frame**
		- Specific wireless protocol
		- Can be sent to AP by spoofing the victim's wireless MAC address 
	- WPA2
		- Often not encrypted
		- Can deauth
	- WP3
		- Requires protected management frame
		- Can't deauth

- **Jamming**
	- **Block all the traffic** in the range or frequency 
	- **Wireless interference** 

## Wi-Fi Jammers vs. Deauthers 

- Deauther
	- Send deauthentication frames
- Jammer
	- Sends out powerful traffic to drown out traffic

### Sideloading and Jailbreaks

- **Sideloading** 
	- Transferring files to a mobile devices typically via USB, MicroSD, or Bluetooth
		- **Install applications outside of the official application store**
	- Not necessary malicious and has legitimate uses

- **Jailbreaking**
	- Takes advantage of vulnerabilities or other weakness
		- Privilege escalation attack and root the system
	- Once a device is jailbroken
		- Installing additional applications
		- Changing settings or options that are not normally available to users

>[!TIP] You'll want to focus on sideloading and jailbreaks. The exam outline focuses on protection methods, but knowing the attacks you may face is important part of understanding wireless security and wireless security settings, which we cover next.

## Designing a Network

- **Site surveys** 
	- Walking through a site
	- Tools test wireless signal
		- **Heatmap**
			- Help determine what channel each AP should use
		- Wireless network management software
			- Monitor interference and overlap problems
		- Wi-Fi analyzer software
			- Heatmap
			- Speedtest
			- Identify best channel

- 2.4 GHz band
	- Each channel is 20 MHz wide
	- 5 MHz space between
	- 11 channels
	- 70 MHz total space
		- Result in overlap
			- In most case use channels 1, 6, 11 

>[!TIP] You'll need to be aware and able to explain the purpose of both heatmaps and site surveys for the exam.

## Controller and Access Point Security

- Wireless Local Area Network (WLAN) controllers 
	- Manage AP and wireless network 
	- Software-defined wireless network
	- Blended Wi-Fi and 5G wireless roaming
	- Deploy
		- Hardware device, cloud, VM or software

## Wi-Fi Security Standards 

- Wi-Fi Protected Access 2 (WPA2)
	- **WPA2-Personal (WPA2-PSK)**
		- Pre-Shared Key
		- Without an auth server 
	- **WPA2-Enterprise**
		- RADIUS authentication server
			- 802.1X implementation
		- Users can have uniques credentials
			- Individually identified

- WPA2
	- Counter Mode Cipher Block Chaining Message Authentication Code Protocol (CCMP)
		- **AES encryption** to provide confidentiality
		- Authentication
		- Access control capabilities 

- Wi-Fi Protected Access 3 (WPA3)
	- **WPA3-Personal**
		- **Additional protection for password-based authentication**
			- Using **Simultaneous Authentication of Equals (SAE)**
				- Replace the pre-shared keys
				- Requires interaction between both the client and the network to validate both sides
					- Slows down brute-force
		- **Perfect forward secrecy**
			- Ensures that the traffic sent between the client and network is secure
				- Even if the client's password has been compromised 
			- **Changes the encryption keys on an ongoing basis**
				- So that a single exposed key won't expose entire communication
	- **WPA3-Enterprise**
		- Stronger encryption than WPA2
			- Optional 192-bit security mode
		- **Authenticated encryption** 
		- Additional controls for deriving
		- **Authenticating keys**
		- **Encrypting** network frames
		- RADIUS

## Wireless Authentication

- Open networks
	- Not require authentication
	- *Captive portal* to gather some information from users
	- Not provide encryption
	- Leaving user data at risk
		- Unless the traffic is sent via secure protocols like HTTPS

- Preshared keys (PSK)
	- Passphrase or key 
		- Shared with anybody who wants to use the network
			- Traffic encrypted
			- But not allow users to be uniquely identified 

- Enterprise authentication
	- RADIUS server
	- Extensible Authentication Protocol (EAP)
		- For authentication 

### Wireless Authentication Protocols 

- 802.1X 
	- IEEE standard for access control
	- Wired and wireless devices
	- Used to integrate with RADIUS servers
		- Allowing enterprise users to authenticate and gain access to the network
	- Groups or network zones
	- Taking actions based on attributes

- Wi-Fi enterprise networks
	- Rely on 802.1X
		- And various versions of **Extensible Authentication Protocol (EAP)**
			- Used as part of the **authentication process**
				- When devices are authenticating to a **RADIUS server**

- Common EAP variants
	- **Protected EAP (PEAP)**
		- Authenticates servers using a **certificate**
		- Wraps EAP using **TLS tunnel**
		- Unique encryption keys
			- For each devices
		- Temporal Key Integrity Protocol (TKIP)
			- Replace keys on a regular basis
	- **EAP-Flexible Authentication via Secure Tunneling (EAP-FAST)**
		- Cisco-developed protocol
		- Improve vulnerabilities in the LEAP
		- Faster reauthentication 
			- **Shared secret (symmetric) key**
		- Can use preshared keys or keys stablished using public key authentication
	- **EAP-Transport Layer Security (EAP-TLS)**
		- **Certificate-based** authentication
		- Mutual authentication
		- Certificates on both client and network devices
			- To generate keys 
		- Used less frequently
			- Certificate management challenges
	- **EAP-Tunneled Transport Layer Security (EAP-TTLS)**
		- **Not require that client devices have a certificate** to create secure sessions
			- Unlike EAP-TLS
			- Remove overhead and management effort
		- **Can require additional software** to be installed on some devices
		- Support for some less secure authentication mechanism 

- Remote Authentication Dial-in User Service (RADIUS)
	- When organizations want to work together
		- **Servers can be federated**
	- Federating RADIUS servers

>[!TIP] Exam outline focuses on WPA3, RADIUS, cryptographic protocols, and authentication protocols without going into specifics about cryptographic protocols and authentication protocols. As you prepare for the exam, you should consider the new security features of WP3 as well as its newer security features over WPA2. You'll also want to have a general understanding of RADIUS and authentication protocols like PEAP and EAP.

# Managing Secure Mobile Devices

## Mobile Device Deployment Methods

- **BYOD**
	- Bring Your Own Device
		- *User device*
		- Limited management capabilities

- **CYOD**
	- Choose Your Own Device
		- User choose from organization device list
		- Security easier 

- **COPE**
	- Corporate-Owned, Personally Enabled
		- Corporate chosen and managed

- **COBO**
	- Corporate-Owned, Business Only

- Virtual Desktop Infrastructure (VDI) 
	- Allow relatively low-security devices to access a secured, managed environment

- Containerization tools
	- Help split devices between work and personal-use environments 

## Hardening Mobile Devices

- Mobile device
	- Not well designed for central management and organizational level security 
- Hardening benchmarks
	- Center for Internet Security (CIS)
- Hardening techniques
	- Updating and patching the OS
	- Enabling remote wipe
	- Passcodes
	- Automatic screen lock
	- Wiping after excessive passcode failures
	- Turn off connectivity when not in use

## Mobile Device Management

- Manage mobile devices
	- **Mobile Device Management (MDM)**
		- Android, iOS, tablets and similar systems
	- Unified Endpoint Management (UEM)
		- Mobile devices, desktops and laptops and many other
	- Mobile Application Management (MAM)

- **Application management** features
	- Deploy specific applications
	- Limit which application can be installed
	- Remote
		- Add, remove, change applications and settings for them
		- Monitoring usage
- **Content management**
	- Ensures secure access and control of organizational files
	- Lock away business data in a controlled space
	- Useful in BYOD and shared-use devices
	- Requires use of the MDM's application 
- **Remote-wipe**
	- Used when device is lost or stolen
	- Work only if the device can receive the command
		- Not if in airplane mode or in RF-blocking bag
		- So encryption, strong passcodes, and the underlying security is important
- **Geolocation and geofencing**
	- Use the location to make decisions about its operation
	- Help locate lost device
- **Screen locks, password, and PINs**
	- Prevent unauthorized access
- **Biometrics**
	- Fingerprint
	- Facial recognition
- **Context-aware authentication**
	- Include location, hours, and other behavioral elements
		- To determine if user should be able to log in
- **Containerization**
	- Separation of work and personal-use
	- Secure container to run app and store data
	- Reduce cross-contamination and exposure
	- Wrap application or complete
- **Storage segmentation**
	- Personal and business data separate 
	- Separate encrypted volumes
- **Full-Device Encryption (FDE)**
	- Stolen or lost device don't result in a data breach
	- May combined with remote-wipe and strong authentication
- **Push notifications**
	- May need to alert a user or ask them to perform an action
	- Want to communicate with someone who found a lost device
	- Tell a thief that the device is being tracked

- UEM and MDM tools
	- Per-application VPN
	- Onboarding tools to help with BYOD
	- Threat detection and response 
	- Control user behaviors
	- Enable closed or managed third-party application store
	- Limit what users can download 
	- Monitor firmware updates and versions
	- Detect good firmware and software
	- Allow or block list to the applications 
	- Control which service and device capabilities can be used
		- Where they can be used
	- Limiting or prohibiting use of cameras, microphone, SMS and MMS
	- Limiting the use of external media and USB on-the-go
	- Control GPS tagging for photos and other documents
	- Control wireless connectivity 
		- Which Wi-Fi can be used 
		- Disabling tethering and hotspot
		- NFC and Bluetooth controls 

>[!TIP] Make sure you can outline the differences, benefits, and challenges of BYOD, COPE, and CYOD device models. Review hardening practices, including using standards like the CIS benchmarks for iOS and Android, and be prepared to leverage your understanding of mobile device management tools and techniques to secure organizational devices.

# Exam Essentials 

- **Modern enterprises rely on many types of wireless connectivity**
	- Cellular networks
		- Control in the hands of cellular providers
	- Wi-Fi
	- Bluetooth

- **Secure wireless network designs take existing networks and physical spaces into account.**
	- Site surveys
	- Physical tours of a facility
	- Tools that can identify existing wireless networks and AP
		- As well as signal strengths and other details that help map the location
	- Channel spacing
	- Access Point placement
	- Composition of the building 

- **Cryptographic and authentication protocols provide wireless security**
	- WPA2
		- Pre-Shared Key
		- Enterprise: RADIUS servers
		- Encrypt data in transit 
	- WPA3
		- Encrypt data in transit
	- Extensible Authentication Protocol (EAP)
		- PEAP
			- TLS, Certificate, Unique encryption key, TKIP for key renewal
		- EAP-FAST
			- Fast reauthentication, symmetric key, pre-shared or dynamic
		- EAP-TLS
			- Client/server certificates, mutual authentication, complex management 
		- EAP-TTLS
			-  Extend EAP-TLS, server certificate only, may require additional software, support less secure authentication methods

- **Understand mobile device vulnerabilities.**
	- Sideloading
		- Programs from external device or system
		- Bypass application store
	- Jailbreaking
		- Provide root access
		- Greater control
		- Security concerns 

- **Securing underlying wireless infrastructure requires strong network device administration and security practices.**
	- Wireless controllers and Access Points must be protected
		- Regularly patched and updated and must be configured securely
	- Protect administrative interfaces
	- Configured to log and report on the network
		- Status, security issues or potential problems
	- Heatmap and site surveys help understand the environment 

- **Managing mobile devices relies on both deployment methods and administrative tools.**
	- BYOW
	- CYOD
	- COPE
	- COBO
	- Mobile Device Management (MDM)
	- Unified Endpoint Management (UEM)
	- Help configure, secure, manage and control
	- Deploying application
	- Wiping

#cybersecurity 