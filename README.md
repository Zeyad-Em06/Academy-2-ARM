simulation video:
https://github.com/user-attachments/assets/0e5296f8-516e-4a5f-97cf-5d805e264107

Technical explanation & debouncing:
The button is connected to a power source. When pressed, it simply closes the circuits, passes the current into pin 14 in port c of the MCU which is configured as a gpio_input pin (takes readings). the code checks if it reads a value on pin 14. if it does, then then pin 13 is toggled (1 to 0 or 0 to 1).
However, there is mechanical bouncing of the button irl so to fix that, a simple way is to add a short delay function after the first high reading from the button, simply to wait for the button signal to be stable and not constantly jumping from 1 to 0 and vice versa. after the short delay the reading is checked again then the process of togggling the led explained above is done.