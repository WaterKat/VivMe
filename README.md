# VivMe
VivMe is a web based image live animator. VivMe can take inputs from different sources, and use these parameters to animate user created images. This can be used to create animated avatars based on motion capture data, among other uses.

# Overview
VivMe is meant to be an accessible open source alternative to programs that animate avatars though voice and face capture.

## Functionality
VivMe is program that will render sprites, and take input parameters, apply modifications, and use that parameter to affect the rendering of these sprites. These modifications to sprites can include, position, scaling, rotation, as well as post processing effects like masking, warping, and colorshifting.

## Rendering
VivMe will use the p5.js package primarily for rendering. This will allow VivMe to run on a web browser, electron based applications, and built in browser extensions in applications like OBS. Further information about rendering features can be found here: [Rendering Documentation](./documentation/rendering.md)

## Audio
VivMe when running in the browser will play audio through web api. This will not be the primary use case for VivMe, but the option to play audio in animations will prove useful if the user wishes to create a more interactive animation. Further information about rendering features can be found here: [Audio Documentation](./documentation/audio.md)
