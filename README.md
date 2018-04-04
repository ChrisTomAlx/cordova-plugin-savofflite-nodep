# cordova-plugin-document-scanner

This plugin defines a global `scan` object, which provides an API for scan the document from taking pictures and choosing image from the system's library. 

Although the object is attached to the global scoped `window`, it is not available until after the `deviceready` event.

    document.addEventListener("deviceready", onDeviceReady, false);
    function onDeviceReady() {
        console.log(scan);
    }

## Installation


This requires cordova 5.0+
npm link :- https://www.npmjs.com/package/cordova-plugin-document-scanner

    cordova plugin add cordova-plugin-document-scanner
    

### scan.scanDoc(sourceType, successCallback, errorCallback)
Takes a photo using the scan, or retrieves a photo from the device's
image gallery.  The image is passed to the document scanner and the scanned image passed to success callback as the URI for the image file.

The `scan.scanDoc` function opens the device's default scan
application that allows users to snap pictures by default - this behavior occurs,
when `sourceType` equals `1`.
Once the user snaps the photo, the scan application closes and the application is restored.

If `sourceType` is `0`, then a dialog displays
that allows users to select an existing image.

The return value is sent to the [`scanSuccess`](#module_scan.onSuccess) callback function, in
the fileUri formats.

You can do whatever you want with the URI, for
example:

- Render the image in an `<img>` tag.

__Supported Platforms__

- Android
- iOS

**Example**  
```js
scan.scanDoc(sourceType, scanSuccess, scanError);
```

## `scan.scanDoc`

Take a photo and retrieve the image's file location:

    scan.scanDoc(0, onSuccess, onFail);

    function onSuccess(imageURI) {
        var image = document.getElementById('myImage');
        image.src = imageURI;
    }

    function onFail(message) {
        alert('Failed because: ' + message);
    }



    //////////////////////////////////


        var savoff=cordova.require("cordova-plugin-savofflite.savofflite")

        var db= 'dbnumbersop';
        savoff.createDbOfflite(db);

        var obj = 'one';
        var _id= 'oneid';
        savoff.putOfflite(db, obj, _id);


        var obj = 'two';
        var _id= 'twoid';
        savoff.putOfflite(db, _id, obj);


        var obj = 'three';
        var _id= 'threeid';
        savoff.putOfflite(db, _id, obj);

        var obj = 'four';
        var _id= 'fourid';
        savoff.putOfflite(db, _id, obj);
        
        var obj = 'five';
        var _id= 'fiveid';
        savoff.putOfflite(db, _id, obj);


        // console.log(sizedbofflite(db));
//
//
// console.log(infodbofflite(db));
//
//
// console.log(getofflite(db, _id));


//  console.log(remofflite(db, _id));


// console.log(sizedbofflite(db));


// console.log(infodbofflite(db));


//console.log(closedbofflite(db));


//console.log(deldbofflite(db));



createDbOfflite : function (dbz) 
getOfflite : function (dbz, _id)
putOfflite : function (dbz, _id, obj) 
remOfflite : function (dbz, _id) 
closeDbOfflite : function (dbz) 
delDbOfflite : function (dbz) 
getAllDocIdsOfflite : function (dbz)
getAllDocsOfflite : function (dbz) 
infoDbOfflite : function (dbz) 


    ///////////////////////////////////

## iOS Quirks

NOTE :- iOS has only document scan via camera for now (Any argument passed will start the camera scan). Document Scan from gallery will be available in future version.

An example file URI obtained from success call back of scanDoc function looks like this  file:///var/mobile/Containers/Data/Application/8376778A-983B-4FBA-B21C-A4CFDD047AAA/Documents/image.png

## Credits / Native library links

Android :- https://github.com/jhansireddy/AndroidScannerDemo <br/>
iOS :- https://github.com/charlymr/IRLDocumentScanner

Huge thanks to these authors for making their document scanning native libraries public.

## More about us!

Find out more or contact us directly here :- http://www.neutrinos.co/

Facebook :- https://www.facebook.com/Neutrinos.co/ <br/>
LinkedIn :- https://www.linkedin.com/company/25057297/ <br/>
Twitter :- https://twitter.com/Neutrinosco <br/>
Instagram :- https://www.instagram.com/neutrinos.co/



