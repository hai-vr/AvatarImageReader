Download: https://github.com/Miner28/AvatarImageReader/releases/

Demo world: https://vrchat.com/home/launch?worldId=wrld_b906fef2-9c90-463a-bb7b-23d187ccdffe&instanceId=0

# AvatarImageReader
Allows you to encode text into image and then read it in VRChat. Uses Avatar Images to store and load images.
Works on both PC and Quest

Made by: @GlitchyDev, @Miner28 and @BocuD

Special help: @lox9973 for Quest support

Special Thanks: @Merlin for making UdonSharp making any of this possible

## Requirements
- VRCSDK 3 2021.06.03 or later (earlier versions are untested but may work)
- Udon Sharp v0.19.12 or later (earlier versions are untested but may work) https://github.com/MerlinVR/UdonSharp

## Documentation
### Encoding images
The python script `gen.py` can be edited to encode any string by changing the last line (this currently contains the example string). It will generate an image file `img.png` which can then be uploaded as an avatar pedestal image to VRChat, for example with VRCX, or the following python script: https://gitlab.com/-/snippets/2183182. 

### Decoding images at runtime
The prefab Decoder contains everything required to decode data from a pedestal. The example pedestal that should be linked by default contains a simple test string `ABCDEFGHIJKLMNOPQRSTUVWXYZ`. The image source for this can be found inside `Python Encoder`. Replace the avatar id to load text from your own avatar source. The ReadRenderTexture udonbehaviour on RenderCamera can be setup to call a callback event on another udonbehaviour when reading completes. The public string `currentOutputString` will then contain the decoded string data.

### Max Image Size by Platform
PC: 1200x900 -> 3.24MB or 1,620,000 UTF16 characters

Quest: 128x96 -> 36.8KB or 18,432 UTF16 characters

Example use cases may include a dynamically updating event calendar that can be updated without updating the world, or a list of patrons in your world. 

A Quest Avatar Pedestal can be used for PC by uploading an image of Quest Size, making a cross platform enabled reader.
Please note that if an image of any size other then exactly 128x96 is uploaded, the image will be compressed and unreadable on quest.
