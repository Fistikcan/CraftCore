\# 🛠️ CraftCore Technical Documentation (v2.1.0)



\## ⚠️ \*\*Important Usage Notes\*\*



To ensure the system works correctly and to avoid potential bugs, please follow these guidelines:



\* \*\*Primary Launcher:\*\* Always start the application using \*\*`CraftCore\_Hosting\_Hub.exe`\*\*.

\* \*\*Avoid Direct Execution:\*\* Do not attempt to run \*\*`runner.exe`\*\* or \*\*`settings.exe`\*\* independently from their respective folders. These components are designed to work in synchronization with the main Hub.

\* \*\*Error Prevention:\*\* Launching sub-components manually may lead to path conflicts, missing library errors, or unexpected crashes. The Hub manages all necessary environment variables and dependencies for you.



---



\## 🏗️ \*\*Technical Architecture \& System Design\*\*



\### 1. \*\*Elevated Execution (UAC \& Admin Rights)\*\*

\*\*Why does CraftCore require Administrator privileges?\*\*

\* \*\*Socket Binding:\*\* Opening the default Minecraft port (\*\*25565\*\*) and managing IPv6 transition technologies requires high-level OS permissions to prevent "Permission Denied" errors.

\* \*\*Automated Port Mapping (UPnP):\*\* The built-in discovery protocols must communicate directly with your gateway/router. Windows Firewall blocks these packets unless the process is elevated.

\* \*\*JVM Optimization:\*\* Administrator rights allow the Hub to set the \*\*Java Virtual Machine (JVM)\*\* to "High Priority" at the kernel level, significantly reducing TPS (Ticks Per Second) drops during high-load gameplay.



\### 2. \*\*Decoupled Library Structure (`lib\_hub` \& `lib\_runner`)\*\*

We utilize an \*\*Encapsulated Dependency Architecture\*\*. Instead of cluttering the root directory with hundreds of `.dll` and `.pyd` files:

\* \*\*Isolation:\*\* All binary dependencies are moved to \*\*`lib\_hub`\*\*. This prevents DLL Hijacking and ensures runtime stability.

\* \*\*Path Persistence:\*\* The system ensures that even though libraries are moved, the binary can locate them without modifying the Global System PATH.



\### 3. \*\*IPv6 \& CGN Bypass Logic\*\*

CraftCore 2.1 is optimized for modern network stacks:

\* \*\*Global Address Recognition:\*\* Automatically detects and binds to your global IPv6 address, bypassing the limitations of ISP-side \*\*CGNAT\*\* (Carrier-Grade NAT).

\* \*\*Loopback Handling:\*\* Manages the "Localhost vs External IP" conflict, ensuring the host can join via local socket while external users connect via the IPv6 tunnel.



---



\## 📺 \*\*Project Showcase \& Tutorial\*\*



Check out CraftCore in action! This video covers the automated installation process and how to use the Hosting Hub effectively.



\[!\[CraftCore Showcase](https://img.youtube.com/vi/VIDEO\_ID\_HERE/0.jpg)](https://www.youtube.com/watch?v=VIDEO\_ID\_HERE)



\*Click the image above to watch the technical tutorial on YouTube.\*



---



\## 📄 \*\*License \& Legal\*\*

\* \*\*Developer:\*\* Fıstıkcan | GitHub Community

\* \*\*Version:\*\* 2.1.0-Stable

\* \*\*Copyright:\*\* © 2026 Fıstıkcan. All rights reserved.

\* \*\*Notice:\*\* This software is provided "as is", without warranty of any kind. Unauthorized redistribution of binary components is prohibited.

