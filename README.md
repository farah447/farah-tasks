# Task 1.1:

# convert audio to txt in Arabic:
HTML code:
          <html dir = rtl>
             <head>
             <title>Live update</title>
             <style media="screen">
             body{
                background-image: url("https://i.pinimg.com/564x/0b/88/18/0b8818b689a5a067aab6f39b3a6cf1fe.jpg");
                background-color: #F4F4F4;
                background-repeat: no-repeat;
                padding: 30px 50px; 
                margin: 40px 20px;
                background-position: bottom  left; 
                background-size: 480px 400px; 
            }
            div.header{
              text-align: center;
              padding: 3px 5px;
              font-size: 15px;
              font-style: italic;
              font-family: Arial;
           }
           p{
             text-align: center;
             padding: 15px 32px;
             font-size: 13px;
          }
          button{
             background-color: #C3AD61; 
             border: none;
  	         color: white;
  	         padding: 15px 32px;
  	         text-align: center;
  	         text-decoration: none;
  	         display: inline-block;
  	         font-size: 16px;
  	         margin: 4px 2px;
             border-radius: 8px;
  	         cursor: pointer;
         }
         </style>    
      </head>
      <body>
        <div class="Header">
         <h2> تحويل الكلام الى نص:  </h2>
         <p><button type="button" onclick="SpeechRecog()">ابدأ</button> &nbsp; <span id=”action”></span></p><span id="action"></span></p>
         <input type="text" id="output">
        </div>
      <script>
           function SpeechRecog() {
                  var output = document.getElementById("output");
                  var action = document.getElementById("action");
                   var SpeechRecognition = SpeechRecognition || webkitSpeechRecognition;
                   var recognition = new SpeechRecognition();
                   recognition.lang = 'ar';

                  // This runs when the speech recognition service starts
                  recognition.onstart = function() {
                    action.innerHTML = "<small>تحدث من فضلك ...</small>";
                  };
                
                  recognition.onspeechend = function() {
                    action.innerHTML = "<small>توقف عن الاستماع ، أتمنى أن تكون قد انتهيت ...</small>";
                    recognition.stop();
                  }
              
                // This runs when the speech recognition service returns result
                recognition.onresult = function(event) {
                    var transcript = event.results[0][0].transcript;
                    var confidence = event.results[0][0].confidence;
                    output.value=transcript;
                };
              
                 // start recognition
                 recognition.start();
            }
      </script>
     </body>
   </html>

# this image is for the web page: 
https://drive.google.com/file/d/1zqn2PfohCjBXkkQjcRvAp8rnfnKOrTPy/view?usp=sharing

# Task 1.2:

2: write wasdom ESP32 operating algorithm:

First, make sure the piece is working by link and the led on the piece is on and off.

Second, download Arduino IDE and connect the piece to the device and download the identification.

Third, run the program.

The piece needs WiFi and is interested in audio coding.

forth, first go to file and then go to examples and then blink.

We use this code to make sure that the piece is working correctly and programmed correctly.

the setup function runs once when you press reset or power the board
      void setup(){
      // initialize digital pin LED_BUILTIN as an output.
      //get information from INPUT or giving information to OUTPUT.
        pinMode(LED_BUILTIN, OUTPUT);
      }

the loop function runs over and over again forever
       void loop(){
          digitalWrite(LED_BUILTIN, HIGH);
          // turn the LED on (HIGH is the voltage level)
          delay(1000);
          // wait for a second
           digitalWrite(LED_BUILTIN, LOW);
          // turn the LED off by making the voltage LOW
          delay(1000);
          // wait for a second
       }

digitalWrite takes two parameters and sends information from the program to the board.

LED_BUILTIN is the LED on the board, you could use a number to tell it which digital Output to write to.

HIGH is equal to ON or 1.
LOW is equal to OFF or 0 (no electricity).
The delay takes one parameter - the number of milliseconds (one thousand of a second).

From tools, then a port, then we choose the port to make sure that the code has moved to the electronic chip.

control ESP32 from website:
The first thing is to write the HTML code for the page you want to control the piece through.
Second, open the Arduino IDE and use the command (client.println("")) to add the html code line by line.
finally, press the run button on the Arduino IDE, and the codes will be transferred to the selected device.


/*ESP32 Chip Features:

The ESP32 development board is characterized by its very powerful features compared to its price and other development boards of the same category, as it is characterized by:

Dual core processor and 32-bit architecture

Processor frequency up to 240MHz

Wi-Fi with a data transfer speed of up to 150 Mbit/s

Bluetooth 4.2

4MB flash memory

512 KB of random memory (RAM)

The number of general purpose terminals for inputs and outputs (GPIO), or in simpler terms, the number of terminals that we can use with external elements such as sensors and light-emitting diodes (LEDs) is 34, noting that there are some special boards from ESP32 where the number of GPIO is 30
Built-in Hall effect sensor (this type of sensor is used to detect the presence of magnetic fields)
Ten built-in touch sensors

Built-in temperature sensor (looks like newer versions of this board no longer come with a temperature sensor, frankly I'm not entirely sure of this information, if anyone can confirm or deny this information let them do so in the comments section below)
12-bit analog-to-digital converter (ADC)

8-bit digital to analog converter (DAC)*/

