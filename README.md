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





