
### <a name="biometric-confirmation-unit"></a> Biometric Confirmation Unit

Various events and actions require biometric confirmation unit to be invoked in order to proceed.

- In essence this is a simple device with two physical input interfaces. One is for basic keyboard input, other is for actual biometric input.
- Aim is to assure action that requests permission was initiated by authentic user.
- Biometric input is not really expected to be implemented in the first iterations. Keyboard input alone should be enough. After all; we are trying to stop bots and imposters in the first place.
- Keyboard input is used to provide some sort of master key. This master key is stored and compared to input made by the keyboard.
- Means of storage for the password is some sort of custom hashing function. vanillaCrypt project could prove useful for this instance. Even tough decryption was never implemented in that, there is no need for it. Only input hash and stored hash will be compared. It was a mashup of established encryption algorithms such as AES, DES etc. I think it'll suffice.
- Since hard-confirmation won't be too common in the system, it might be a good idea not to implement auth caching.