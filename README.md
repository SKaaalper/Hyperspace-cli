# HyperSpace Node Installation Guide

## Installation for Apps
1. **Create an Account:** [HyperSpace Node](https://node.hyper.space/)
2. **Download the App**
3. **Connect the Node:** Click the red "Connected" button (it will turn green automatically).
4. **Copy Your Private Key:** Click the key icon.
5. **Paste Your Private Key** into the provided rectangular box.

**Notes:**
- This can be done on mobile.
- The node disconnects frequently; check it regularly.



## Installation for Linux:

### 1️⃣ Install AIOS Node
```sh
curl https://download.hyper.space/api/install | bash
source /root/.bashrc
```
This downloads and installs the AIOS Node package and updates your shell environment.

### 2️⃣ Save Your Private Key
```sh
nano my.pem
```
- Follow the official guide to obtain your private key.
- Save and exit nano by pressing `Ctrl + X`, then `Y` to confirm.

![image](https://github.com/user-attachments/assets/218e2abb-917a-4d6c-a72c-832e0a18cfff)
  
```sh
chmod 600 my.pem
```
This restricts access to your private key for security.

### 3️⃣ Create a Screen Session
```sh
screen -S hyperspace
```
- This creates a screen session named `hyperspace` to keep the process running in the background.

### 4️⃣ Start the Node
```sh
aios-cli start
```
- Starts the HyperSpace node.
- To detach from the screen session, press `Ctrl + A`, then `D`.

### 5️⃣ Download a Required Model
```sh
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```
- Downloads the necessary AI model for the node.

### 6️⃣ Import Your Private Key
```sh
aios-cli hive import-keys ./my.pem
```
- Imports your saved private key into the system.

### 7️⃣ Log in to Your Node
```sh
aios-cli hive login
aios-cli hive connect
```
- Authenticates and connects your node.

### 8️⃣ Select a Storage Tier
Choose the appropriate tier based on your server's storage:
- **Tier 1** - `30GB`
- **Tier 2** - `20GB`
- **Tier 3** - `8GB`
- **Tier 4** - `4GB`
- **Tier 5** - `2GB`

- Format: 
```sh
aios-cli hive select-tier 5
```

### 9️⃣ Check Points and Node Status
```sh
aios-cli hive points
```
- Displays the accumulated points.

- Also, you can check your points on the website.
  
![image](https://github.com/user-attachments/assets/4bcd39d1-087e-46de-b185-b9b37f54a2d7)


### 🔟 View Your Public and Private Keys
```sh
aios-cli hive whoami
```
- Shows your node's public and private key details.


### Official Documentation
- [HyperSpace AIOS CLI Guide](https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file)
