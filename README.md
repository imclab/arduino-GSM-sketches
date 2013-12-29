###Arduino GSM Sketches

These are a collection of sketches to be used with the Arduino GSM Shield.  They focus primarily on using the shield through serial communication instead of using the GSM library.  

####Notes for the tracking sketch

Something important to note is that I modified the GSM library in order to get this sketch to work.  The GSM3CircularBuffer.h file has a default buffer size of 128.  In order to get AT+QENG? information from the GSM module, I had to increase the size of the buffer to 256.  The __BUFFERMASK__ was also changed to 0xFF.

If using the SoftwareSerial Library, modify the SoftwareSerial.h file and to increase the buffer from 64 to 256.

This can be done by:

- Go to the Arduino application (Applications > Arduino) and right click. Select show package contents
- Find the file Resources > Java > libraries > SoftwareSerial > SoftwareSerial.h
- Change the line: __#define _SS_MAX_RX_BUFF 64__   to __#define _SS_MAX_RX_BUFF 256__
- Save file
