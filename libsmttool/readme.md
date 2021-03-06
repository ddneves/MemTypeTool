# Memtype Library List

Basic usefull libraries to communicate with MemType device, files in this list:

 * noekeon.py: Implementation of noekeon cipher algorithm based on the oficial specification located at [Noekeon-spec.pdf](http://gro.noekeon.org/Noekeon-spec.pdf). NOEKEON is an iterated block cipher with a block and key length of 128 bits.

```
Public methods implemented in noekeon.py file:

1. NoekeonEncrypt(WorkingKey, State)
2. NoekeonDecrypt(WorkingKey, State)

The Number of Rounds is defined by NUMBER_OF_ROUNDS and fixed to 16.
WorkingKey -- format is 4 elements of 32 bit length each.
State      -- is the information to be encrypted / decrypted in 4 elements of 32 bit.

```
 * memtype.py: memtype command library implementation

```
Public methods implemented in memtype.py file:

1. memtype Class (communicates with device)
   1.1 connect (open USB connection with device)
   1.2 disconnect (close USB connection with device)
   1.3 info (read info from device and return deviceInfo object)
   1.4 write (write credentials to memtype credential reserved memory area, credential data must be encrypted first with the correct PIN)
   1.5 read (read credentials from memtype, must be decrypted after reading with the correct PIN)
   1.6 writePinHash (writes pin Hash into memtype, pinToHash function to be used to generate the Hash)
   1.7 readPinHash (reads pin Hash from memtype)
   1.8 writeKeyboardLayout (writes keyboard layout into memtype device)
   1.9 isLocked (check status of the device, returns True if memtype PIN has not been entered)
   1.10 validatePin (when Memtype is unlocked, return True if pin is equal to memtype hash, return false otherwise)


2. decryptCredentialList(cl, key) (decrypts credential list according to device implementation)
3. encryptCredentialList(cl, key) (encrypts credential list according to device implementation)
```

## Dependencies:
```
python 2.7
libusb-1.0-0
pyusb library
```
Linux:
```
$ sudo pip install pyusb
```
Mac:
```
$ sudo port install py-pyusb
```
Dependencies:
python 2.7
pyusb library

Mac:
```
sudo port install py-pyusb-devel
```
