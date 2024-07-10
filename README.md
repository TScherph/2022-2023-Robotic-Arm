# Robotic-Arm-2022
Individual High School Senior Design Project 2022 creating a 3d printed robotic hand and arm


https://github.com/TScherph/Robotic-Arm-2022/assets/147080935/0c7fabfe-fba3-4cce-bbdb-8780fc61444e


How does the arm work:

CAD: 


https://cdn.discordapp.com/attachments/1156343721588166676/1260612260087205968/IMG_2448.png?ex=668ff427&is=668ea2a7&hm=0f13ab30221cbbaa7dc15f9fa14fc70a868e2202226737c3c38873be06b0ab1e&



The cad consists of 4 main areas.

The fingers:

 5 individual finger each constructed by 3 parts, there are two “mid” parts which serve as the first two joints and there is a finger tip, an parts have 2 0.1in holes spaced at 0.3in apart and are centered 0.2in vertically raised from the bottom of the finger that I thread elastic bands through, there is also a 1.5in X 1.5in square at the top that is 0.1in from the top that I thread the fishing wire through.
Each finger is connected to the hand via elastic bands that form a U which has its apex at the fingertip, this causes the finger to be pulled taught into the palm allowing it when unactuated to stand at an open hand position
The Palm has holes that go from the point of connection for the finger out the back side of the palm allowing me to tie off each elastic band, There is a groove to allow for placement of felt to allow for greater grip
The forearm, palm, and fingers are all currently printed out of SLS, the elbow and bicep are printed from PLA for prototyping purposes
The Forearm:
The forearm is two separate 3d printed parts, it stores 5 servos (4 shown in cad) and these servos are each connected to one of the fingers VIA fishing line, the fishing line when pulled taught allows the fingers to be pulled into a closer fist position giving the hand its motion
This forearm is connected to the elbow via a 0.5in hex shaft.

The Elbow:

The elbow serves two purposes. It houses the wires from the forearm, and it houses the servo that controls forearm rotation.
The elbow is connected to the bicep via a ultra planetary gearbox 90degree module allowing the elbow to actually bend

The Bicep: 

The bicep is the largest and heaviest part, it houses a neo 550 motor and 3 5:1 ultra planetary gearbox modules allowing the neo to rotate and control the elbows bend

Electrical:

The electrical is relatively simple, I use an arduino UNO with a 12v Anker battery pack ziptied to it to power the entire arm. The arduino currently uses 6 of its output pins for servos and has a 5v and gnd output. The ground and 5v breakoff into 7 different wires as they feed all required power currently
My goal is to create a polycarbon casing for the batterypack and arduino in the future

Programming

Arm Control:

The control of the arm itself is done through Arduino IDE, The motors rotate from a 0 degree position to a 180 degree position at increments of 30 degrees every 10th of a second, resistances cause the rotation to take longer but not noticeably
The input is a serial input that reads a char for a number or letter, each finger is controlled by a number 1-5 from thumb to pinky respectively

Wireless communication:

The arm is connected to a computer wirelessly via two Exbee Pro s1 modules, one inserted into a devices USB port as the transmitter and the other wired to the arduino as the receiver
The two modules talk to eachother over radio signals and can be directly communicated with using the XCTU Software

Easier use interface:

Using the Python IDE for windows I created a GUI that has 8 buttons, the buttons control fingers 1-5, a button to invert all fingers locations allowing mass control, a button to trigger a rock paper scissors random output and a quit command
The GUI communicates through the computer directly to the usb port, ignoring XCTU and talks to the exbee in Chars allowing me to directly control the fingers

![Screenshot 2023-05-21 191856](https://github.com/TScherph/Robotic-Arm-2022/assets/147080935/82894409-77ce-4a53-8291-f2b012851c85)
