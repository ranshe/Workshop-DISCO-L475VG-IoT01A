# Mbed Cloud Workshop - Connect Service

## Embedded Application

### Prerequisites
1. Install [Mbed CLI](https://os.mbed.com/docs/latest/tools/installation-and-setup.html)
1. Register for an [Mbed OS account](https://os.mbed.com/account/signup/) (if you do not already have one)
1. Register for an [Mbed Cloud account](http://cloud.mbed.com/quick-start)
1. Download the code: `mbed import https://github.com/BlackstoneEngineering/mbed-cloud-workshop-connect`

### Let's Code: Device to Dashboard
1. Create a Developer Certificate for your device
   1. Log into the [Mbed Cloud Portal](https://portal.mbedcloud.com/) with your developer account.
   1. Go to **Device Identity** -> **Certificates**.
   1. Click **Actions** -> **Create a developer certificate**.
   1. Enter a certificate file name. This file name is for your convenience. For example: `Jenny_Plunkett`
   1. Click **Create Certificate**.
   1. A credentials C file called `mbed_cloud_dev_credentials.c` is created. It contains the credentials you need to connect your device to Mbed Cloud.
   1. Download the file and copy/paste it into your `mbed-cloud-workshop-connect` project folder
1. Change the wifi SSID and password credentials at the top of `main.cpp`
   - SSID: `mbed`
   - Password: `mbedisawesome`
1. Plug the board into your computer
1. Compile, flash, and view the board's serial output
   - `mbed compile --target auto --toolchain GCC_ARM --flash --sterm`
1. View your Mbed Cloud Portal dashboard: https://portal.mbedcloud.com/dashboard/usage

### Let's Code: Make Device Blink
- Read number of button presses – GET from "3200/0/5501", "button_count"​
- Make LED’s Blink – POST to "3201/0/5850", "blink_action” ​
- Change LED Blink Pattern – PUT to "3201/0/5853", "blink_pattern” 

### Let's Code: Challenge
- Change variables in Developer Certificate
   - Serial, name, device type ... etc.
- Add variables with multiple functions GET/PUT/POST

## Web App

### Let's Code: Web App
1. Install [Node.js](https://nodejs.org/en/) and [npm](https://www.npmjs.com/)
1. Clone the Mbed Cloud SDK JavaScript Quickstart to your computer
   - `git clone https://github.com/ARMmbed/mbed-cloud-sdk-javascript-quickstart`
1. `cd mbed-cloud-sdk-javascript-quickstart`
1. Install the required npm packages: `npm install`
1. Create your API key
   1. Open the Mbed Cloud Portal: https://portal.mbedcloud.com/
   1. In the Cloud portal, navigate to **Access management** > **API keys**
   1. Click **Create new API key**.
   1. Define the API key name. For example: `Jenny`
   1. Select the key's group. Note that the key will have the same privileges as the group you select, meaning an administrator key will have full privileges.
   1. Click **Create API key**. A key is generated.
   1. Copy the generated API key.
1. Open `app.js`
   - Replace the `<access key>` placeholder in the `accessKey` variable on line 8 with the API key you just copied
1. Run the app: `node app.js`
1. Open `http://localhost:8080` in your browser
1. You should now see a list of connected Mbed Cloud JavaScript Quickstart devices
   <img width="946" src="/img2.png">
1. If you open the Mbed Cloud portal (https://portal.mbedcloud.com/) you should also see your device listed under "Device directory" > "Devices"
   <img width="835" src="/img1.png">

### Let's Code: GET/PUT/POST to Device
1. Subscribe to your board's simulated button presses by clicking on the checkbox next to "Subscribe" and then click the "Get presses (GET)" button
1. Type `500:500:500:500` into the text box below "LED blink pattern"
   - This pattern indicates that the LED on the board will turn on for 500 ms, turn off for 500 ms, turn on for 500 ms, and then turn off for 500 ms (and then stay off)
1. Click the "Update (PUT)" button
1. Now click the orange "Blink (POST)" button and verify that your board's LED blinked twice
