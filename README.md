# DIY-Arduno-based-Stroboscope

![image](https://user-images.githubusercontent.com/19898602/145040969-2d15bcf9-3bef-4045-8acd-17edc7089ab6.png)

Hello friends in this post we will see how to make Stroboscope using arduino.
Stroboscope an instrument for studying periodic motion or determining speeds of rotation by shining a bright light at intervals so that a moving or rotating object appears stationary.

A stroboscope, also known as a strobe, is an instrument used to make a cyclically moving object appear to be slow-moving, or stationary. It consists of either a rotating disk with slots or holes or a lamp such as a flashtube which produces brief repetitive flashes of light. Usually, 

the rate of the stroboscope is adjustable to different frequencies. When a rotating or vibrating object is observed with the stroboscope at its vibration frequency (or a submultiple of it), it appears stationary. Thus stroboscopes are also used to measure frequency.


![Strobe_2](https://user-images.githubusercontent.com/19898602/145041154-8db9d77a-5061-48f4-afe3-a47376fcd684.gif)


# COMPONENT REQUIRED 

![image](https://user-images.githubusercontent.com/19898602/145041591-7ab87c80-f4d2-455c-afd9-eb5466c76272.png)


> Arduino Nano :-  https://amzn.to/2NyDX4u

> 0.96" OLED Display :- https://amzn.to/2NDva11

> 10W LED :- https://amzn.to/2NCZdFW

> 10K POT :- https://amzn.to/2x81M8W

> Toggle S/W :- https://amzn.to/2NafZ05

> 2222A Transistor :- https://amzn.to/2QojE8b

> Custom PCB


# CIRCUIT DRAWING

![image](https://user-images.githubusercontent.com/19898602/145041996-145caf7c-a0f4-4c8e-83ac-9025ee22673a.png)


Stroboscopes produce carefully timed pulses of light in order to make a rotating object appear still. While this may seem like something of an exotic concept, YouTuber Mr. Innovative decided to build his own using an Arduino Nano.

His project uses a PN2222A transistor to drive a 10W LED, which acts as the device’s light source. The spinning RPM is set via a potentiometer, and a small OLED provides user feedback.

Let’s do some mathematical calculation

We had designed this circuit for LXML-PWC1-0100 LUXEON LED.

Voltage required to illuminate LED i.e. Vin

V_{in} = V_t + (V_f \times nLED)
Here we are using three LED in series, hence number of LED nLED = 3

V_t = 2
V_f = 3.99V (voltage required to powering the single LED)

Now, wee can calculate the Vin voltage

V_{in} = 2 + (3.99 \times 3) = 13.97 \approx 14V
So, we required approximately 14V per column.

After calculating required voltage for powering the LED, let’s calculate supply voltage by LM317

# CUSTOM PCB



![image](https://user-images.githubusercontent.com/19898602/145042790-b83b088f-418e-4b80-a4d1-db8233d55d57.png)
![image](https://user-images.githubusercontent.com/19898602/145042732-142f6179-cced-4419-ab40-a6e7b124ccf6.png)

I have design circuit and PCB in [easyEDA](https://easyeda.com/) and ordered PCB from [JLCPCB](https://jlcpcb.com/IAT )

This is the link of [PCB editabl file](https://oshwlab.com/sharmaz747/multipurpose-pcb)

If you seriously need quality PCB quickly in your hand then you must have to try [JLCPCB](https://jlcpcb.com/IAT ) PCB manufacturing service.
They have Special offer of $2 for 1-4 Layer PCBs, free SMT assembly monthly.
If you get yourself registered today at [JLCPCB](https://jlcpcb.com/IAT ) you get welcome coupon from [JLCPCB](https://jlcpcb.com/IAT ).

![image](https://user-images.githubusercontent.com/19898602/145043499-ef9f87fd-7355-41e1-b811-59b64a4cef46.png)
![image](https://user-images.githubusercontent.com/19898602/145043605-a9708bfb-ba64-4234-b2ec-5d8b5461a43d.png)
![image](https://user-images.githubusercontent.com/19898602/145043637-ae2f2185-af05-4e3c-ba3a-83f2710453e0.png)
![image](https://user-images.githubusercontent.com/19898602/145044301-88f74079-4bf7-4cce-9180-350d46890838.png)

# PROCEDURE

![image](https://user-images.githubusercontent.com/19898602/145044419-b0626b6f-2c89-4e4b-9dff-80e843f7356c.png)

first of all we collect all the required components like Arduino Nano, 0.96" OLED Display, 10W LED, 10K POT, Toggle S/W, Toggle S/W, 2222A Transistor, Custom PCB
 

 
![image](https://user-images.githubusercontent.com/19898602/145044699-a0c9349d-d1d6-45a3-a32d-303be3b768f7.png)

Then I shholder the Display pins to the PCB
basically pin cofiguration are as below

I2C display             Arduino
    SCL                   A5
    SDA                   A4
    5V                    5V
    GND                   GND
    
    
   
 ![image](https://user-images.githubusercontent.com/19898602/145045082-ee4cfe92-0653-4d8b-bfe4-bdeaa48721ee.png)
![image](https://user-images.githubusercontent.com/19898602/145045143-516386d6-43af-41e5-a601-db550155900c.png)
![image](https://user-images.githubusercontent.com/19898602/145045215-f085d65e-a6f3-4642-9e46-ca31cb0f9df2.png)

Then I bring sun board sheet and mark the dimensions on the sheet with the help of scale and pen
and the I cut those parts with the help of cutter to make the shape of object like gun which we can hold in our hand


![image](https://user-images.githubusercontent.com/19898602/145045537-320f997b-fa37-4ffe-88d8-c7b36c5639b6.png)

Then I 3D printed a reflector part and used 10W led diode to make the stroboscope 

![image](https://user-images.githubusercontent.com/19898602/145045949-8e8cdc96-a2ed-4bc1-87ef-6d9c1aaf3899.png)
![image](https://user-images.githubusercontent.com/19898602/145045992-e482d351-df62-44b6-a060-3682a3faf95f.png)


Then I install the potentiometer, toggle switch and 0.96'' oled display on the other side of strobo scope and 
fit the panel with the body using super glue. 

# CODE

```

#include <Wire.h>
#include "SSD1306Ascii.h"
#include "SSD1306AsciiWire.h"
#define I2C_ADDRESS 0x3C
#define RST_PIN -1
SSD1306AsciiWire oled;


const int led = 12;
int customDelay,customDelayMapped; // Defines variables
 

   
void setup() {
  Wire.begin();
  Wire.setClock(400000L);
  Serial.begin(9600);
#if RST_PIN >= 0
  oled.begin(&Adafruit128x64, I2C_ADDRESS, RST_PIN);
#else // RST_PIN >= 0
  oled.begin(&Adafruit128x64, I2C_ADDRESS);
#endif // RST_PIN >= 0

  oled.setFont(Adafruit5x7);
  oled.clear();
  pinMode(led,OUTPUT);
  
  oled.set2X();
  oled.setCursor(0, 0);
  oled.println("");
  oled.set1X();
  oled.setCursor(0, 13);
  oled.println("");
  oled.set2X();
  oled.setCursor(0, 20);
  oled.println("  WELCOME  ");
  oled.set1X();
  oled.println("");
oled.set2X();
  oled.setCursor(40, 25);
  delay(1400);
  
}


  
void loop() {
 
  
   staticmenu();
  
 customDelayMapped = speedUp(); // Gets custom delay values from the custom speedUp function
  // Makes pules with custom delay, depending on the Potentiometer, from which the speed of the motor depends
  digitalWrite(led, HIGH);
  delayMicroseconds(200);
  digitalWrite(led, LOW);
  delay(customDelayMapped);
Serial.println(customDelayMapped);
  
}
  
  
  int speedUp() {
  int customDelay = analogRead(A0); // Reads the potentiometer
  int newCustom = map(customDelay, 0, 1023, 1,50); // Convrests the read values of the potentiometer from 0 to 1023 into desireded delay values (300 to 4000)
  return newCustom;  
    
}
  
  00
  
  .
1141,,j    ,
//.,       m[p
0.....
00000
.444444444444444    



  
  

void staticmenu() {
  oled.set2X();
  oled.setCursor(0, 0);
  oled.println("STROBOSCOPE");
  oled.set1X();
  oled.setCursor(0, 13);
  oled.println("---------------------");
  oled.set2X();
  oled.setCursor(0, 20);
  oled.println("    RPM   ");
  oled.set1X();
  oled.println("");
oled.set2X();
  oled.setCursor(40, 25);
   
 
   oled.print( customDelayMapped*99, DEC);
  
// if (customDelayMapped % 100 == 0){
//    oled.clear();
// }
  
  
  //oled.display();

}


```


In this way sctroboscope construction is done now it is time for testing 

![10000000_371783094596508_6335027578223470645_n](https://user-images.githubusercontent.com/19898602/145046692-c8939218-628c-4bd2-be4e-06329e28fdb8.gif)


