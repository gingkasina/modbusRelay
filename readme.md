# Mosbus Relay
![](https://raw.githubusercontent.com/gingkasina/modbusRelay/master/image/1_MKG_nHa2YmhmqMWOcCB8_w.jpeg)
## คุณสมบัติ
- ใช้กับแหล่งจ่ายไฟ 12VDC
- สื่อสารด้วย RS485 Half Duplex กําหนด Slave Device ID ได้อิสระจากคําสั่ง
- 8 Output Relay 2 Contact (NO / COMMON / NC)
    - AC Contact Rating 10A / 220VAC
    - DC Contact Rating 10A / 30VDC
- 8 Input Opto-Isolate 12V แบบ Sink Input
- การเชื่อมต่อสื่อสารผ่านสัญญาณแบบ RS485 Half Duplex ด้วย Modbus RTU Protocol
    -สามารถกําหนดค่า Slave Address ได้อิสระจาก คําสั่ง
    - Baudrate 9600bps, Data 8Bit, None Parity, 1 Stop Bit
- มีคําสั่งรองรับการทํางานแบบ
    - Write Single Coil(0x05) สําหรับสั่ง ON/OFF
    - Read Discrete Inputs(0x02) สําหรับสั่งอ่านสถานะ Input
- ขนาด ความกว้าง 6.7ซม. x ความยาว mn.o ซม. 

## การใช้งาน
ในการทดลองนี้ใช้ npm package modbus-serial ซึ่งจะใช้ method writeCoil ดังรูป
    
![](https://raw.githubusercontent.com/gingkasina/modbusRelay/master/image/1.PNG)



โดยที่ 
- address ในการทดลองนี้ มีค่าตั้งแต่ 0-3 โดยที่ 0 คือ channel 1 ตามลำดับ

- state มีค่าเป็น True / False โดยที่ true คือการสั่งให้รีเลย์ทำงาน (ขา C ต่อกับขา NO )
และ False คือ การสั่งให้รีเลย์ไม่ทำงาน (ขา C ต่อกับ ขา NC)

