##Bluetooth Authentication -- A Secure and Usable Authentication Scheme


__Device:__ a tablet and a pc

__PC stores:__ Two encryption key, K1 and K2.

__Tablet stores:__ Password set encrypted by K3, K3, and decryption key K4.

__Key Relations__ K1 can decrypt data encrypted by K3, and K4 can decrypt Data encrypted by K2.

__Procedure__:

1. Tablet and PC establish connection by Bluetooth (only one time).

2. Tablet automatically connect to PC

3. PC fetch encrypted password from Tablet

4. PC decrypt password the password using local key K1.

5. Password manager will automatically fill the password

6. After filling, no password will be stored in the pc

7. When PC needs to create or update passwords, encrypt the data using K2 and send the data to the tablet. 

8. The tablet decrypt the data and update its password set.

__Analysis:__

This scheme has good usability since users do not need to do anything, the passwords will be automatically filled (If the connection has been established before).

This scheme has good security since compromising either of the device does not help the attacker obtain the passwords. Unless both devices are compromised, the manager should be secure.
