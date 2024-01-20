# gokeyless
Keyless door lock

## Lock

For both of the approaches below, the public key of the backend must be stored to authenticate connections or validate QR codes.

### Wifi design
The lock could be an inexpensive microcontroller board with an integrated wifi chip.
[Rasperry Pi Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/) is available from $4.

This board must connect to the lock hardware in the door, and the hotel's wifi network.

The application running on this board listens for TCP/IP connections from the backend described below.

### QR code & camera design
The Rasperry Pi Zero module & case can be fitted with an integrated camera. This could read a QR code from the phone.
The QR code would be a ephemerally-signed token that unlocks the door for the duration of the client's stay.

## Web app
The web app allows users to book & pay for the room.
It also allows keyless entry.
When the user is logged in, during their stay, they can remotely unlock the door.

## Backend
We need a database for locks, users, bookings, payments & everything in between.
We also need a service running to serve the clients of the web app, and to control the locks via the TCP/IP socket.
