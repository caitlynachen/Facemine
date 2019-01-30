# Facemine

An app that takes photos and encrypts and saves them locally, for future facial recognition purposes. 

## Getting Started

1. Download or clone the source code.
2. Open the FM.xcworkspace file.
3. Build on a mobile device (will not work on simulator because no camera).

## Future Considerations

Right off the bat, I started using ImagePickerController to handle taking the images, and got the camera to take a single image. But after looking up some documentation, it was probably a better idea to switch to AVPhoto to handle image capturing (as the project called for taking multiple photos). I got the photo taking functionality done within a half hour, but started running into problems when I tried to install libraries. I tried using pods at first, but kept getting the error "No module found," so I tried Carthage, and importing the files locally. Still, it wasn't building. I switched back onto pods and finally found a reddit post that said that I might have to add $(inherited) to my Framework Search Paths in Build Settings. After an hour of struggling to import libraries, it was such a simple solution to fix it. I quickly implemented the encryption functionality thereafter using CryptoSwift. And then had the project write the data into a file.

In the future, I would look into making the UI lots better (adding an App Icon, making the buttons more appealing, adding transitions using hero kit, adding flash transitions for each time the camera takes a photo). I would definetely also add an alert to show that the app is encrypting (maybe a loading icon "Encrypting..."), instead of just printing that action to the console. I would also have an alert Controller appear when the app is all finished storing the encryption.

Moreover, instead of writing the data to a local file, I would use a local database, either Realm or CoreData to store the data locally. That way, it can be accessed without reading a file.


