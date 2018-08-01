# Mbed Cloud Workshop - Connect service

## 

## Adding a web app

### Running the JavaScript web app
1. Install [Node.js](https://nodejs.org/en/) and [npm](https://www.npmjs.com/)
1. Clone the Mbed Cloud SDK JavaScript Quickstart to your computer
   - `git clone https://github.com/ARMmbed/mbed-cloud-sdk-javascript-quickstart`
1. `cd mbed-cloud-sdk-javascript-quickstart`
1. Install the required npm packages: `npm install`
1. Copy the provided Mbed Cloud API key
1. Open `app.js`
   - Replace the `<access key>` placeholder in the `accessKey` variable on line 8 with the Mbed Cloud API key you just copied
1. Run the app: `node app.js`
1. Open `http://localhost:8080` in your browser
1. You should now see a list of connected Mbed Cloud JavaScript Quickstart devices
   <img width="946" src="/img1.png">
1. If you open the Mbed Cloud portal (https://portal.mbedcloud.com/) you should also see your device listed under "Device directory" > "Devices"
   <img width="835" src="/img2.png">

### GET/PUT/POST to your device
1. Subscribe to your board's simulated button presses by clicking on the checkbox next to "Subscribe" and then click the "Get presses (GET)" button
1. Type `500:500:500:500` into the text box below "LED blink pattern"
   - This pattern indicates that the LED on the board will turn on for 500 ms, turn off for 500 ms, turn on for 500 ms, and then turn off for 500 ms (and then stay off)
1. Click the "Update (PUT)" button
1. Now click the orange "Blink (POST)" button and verify that your board's LED blinked twice
