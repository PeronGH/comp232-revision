# Steganography

## What to Protect
- Steganography aims to protect the existence of the message, not just its content
- Metadata of the message (sender, recipient, time sent, length) may also need protection

## Steganography and Information Hiding
- Steganography: methods of secure communication that conceal the existence of the message
- Non-digital examples: invisible ink, microdots

## Digital Steganography
- Involves hiding information within digital files (cover objects) such as text, images, audio, or video

## Digital Watermarking
- Aims to embed information that cannot be removed or altered without making the cover object unusable
- Adds the requirement of robustness compared to steganography
- Can be used for copyright protection

## Texts as Cover Objects
- Example: using the second letter of each word in a seemingly innocuous text to convey a hidden message

## Images as Cover Objects
- LSB (Least Significant Bit) substitution method:
  - Least significant bits used to store pixel characteristics are modified to store a message
  - Resulting image looks identical to the original to the human eye
  - Easy to implement but not very robust
- Advantages of LSB: easy to implement, high capacity
- Disadvantages of LSB: not robust, message is easy to detect (introduces distortion to statistical properties of the image)

## Stochastic Modulation Method
- Simple variant: randomly chosen pixels are altered by changing their intensities by +1 or -1 before applying LSB
- Improved method (J. Fridrich, M. Goljan):
  - Add "noise" (pseudo-random values) modulated by message bits to the cover image
  - Pseudo-noise can be generated deterministically given a secret initial value (key)
- Advantages: high capacity, low embedding and extraction complexity, high security (embedding noise can approximate noise of a given device)

## Transform Space Algorithms
- Jsteg algorithm (D. Upham) uses specifics of JPEG image format
  - Replaces least-significant bits of discrete cosine transform (DCT) coefficients with message data
- Provides better protection against visual attacks compared to spatial domain methods

## Audio and Video Files as Cover Objects
- LSB can be used but introduces significant noise to audio data
- Message can be encoded in audio signal phase
- Spread spectrum method: encoded data spread across the maximum range of frequencies (difficult to detect)
- Video objects (files, streams) can also be used for hiding information

## Network Packets as Cover Objects
- Steganography within TCP/IP: insert data within TCP and IP protocol headers
- Naive embedding can be detected by anomaly detection in TCP/IP fields
- Detection can be prevented by considering properties of specific TCP/IP implementations
- HTML steganography

## Redundancy
- Steganography is applicable to any data objects containing redundancy
- Redundancy is used to hide the presence of the embedded message
- Data compression may remove redundancy
- Data compression and message embedding can be combined (e.g., MP3stego by F. Petitcolas)

Steganography provides a means to conceal the existence of a message within various digital cover objects. By exploiting the redundancy present in these objects, steganographic methods can embed hidden information while minimizing detectability. However, the robustness and security of steganographic techniques vary, and care must be taken to balance the trade-offs between capacity, robustness, and undetectability when designing steganographic systems.