---
services: cognitive-services, computer vision, face
platforms: dotnet, c#
author: easyj2j
---

# Face Finder

This sample searches a folder for image files containing a face. Selected attributes of the image and face are displayed. Searches can be filtered by age range, gender, and whether the face matches a specified person. The sample uses the Windows client libraries for the Cognitive Services Computer Vision and Face services.

## Features

* Parses a folder for image files of type bmp, gif, jpg, and png.
* Processes the image files to detect images containing a face.
* Displays thumbnails of each image containing a face, along with attributes associated with the image and face.
* Available attributes are:
  * age and gender
  * caption (as a tool tip)
  * printed character recognition (OCR)
  * date image taken and title, if available
* Image files can be filtered on:
  * age range
  * gender
  * matching person/face
* Finds all images containing a face that matches a specified person. A "person" is created by selecting one or more known images of the person. Alternatively, the first image of a person found in a folder can be used.

![Screenshot](FaceFinder/Assets/FaceFinder.jpg)

## Getting Started

### Prerequisites

* You need subscription keys for the Computer Vision and Face services to run the sample. You can get free trial subscription keys from [Try Cognitive Services](https://azure.microsoft.com/try/cognitive-services/).
* Any edition of [Visual Studio 2017](https://www.visualstudio.com/downloads/) with the .NET Desktop application development workload installed.

### Quickstart

1. Clone or download the repository.
1. Open the *FaceFinder* folder in the repository.
1. Double-click the *FaceFinder.sln* file, which opens in Visual Studio.
1. Build the project, which installs the Computer Vision and Face service NuGet packages.
1. Run the program.

1. Click the drop-down button on the upper left of the screen, which opens a dialog box.
1. Insert your valid subscription keys and associated endpoints. The keys and endpoints are stored in **IsolatedStorage**.
1. Click the drop-down button again to close the dialog box.
1. Click **Select folder** and browse to a folder that you want to search for images containing faces.
1. Click **Find faces**, which searches the folder for image files and then analyzes these files for faces. Images found with faces are displayed along with information about the faces. By default, the file name, gender, and age are displayed.

## Known issues

* Performance is related to image size due to uploading and processing time. Small images on the order of 20 KB can provide good results.
* Image metadata is not available.
* Person Group thumbnails aren't displayed (but still used) after changing the Person and then returning to the previous Person.
* Future features:
  * Persistence of settings other than subscription keys and endpoints
  * Search subfolders
  * Confidence slider for what constitutes a matched face
  * Number picker to limit number of images processed
  * Image reduction/compression before upload
  * Azure blob storage

## Resources

* [Included Help guide](HELP.md)
* [Computer Vision service documentation](https://docs.microsoft.com/azure/cognitive-services/computer-vision/)
* [Computer Vision API - v2.0](https://westus.dev.cognitive.microsoft.com/docs/services/5adf991815e1060e6355ad44/operations/56f91f2e778daf14a499e1fa)
* [Microsoft.Azure.CognitiveServices.Vision.ComputerVision 3.2.0](https://www.nuget.org/packages/Microsoft.Azure.CognitiveServices.Vision.ComputerVision/3.2.0) client library NuGet package
* [Face service documentation](https://docs.microsoft.com/azure/cognitive-services/face/)
* [Face API](https://docs.microsoft.com/azure/cognitive-services/face/apireference)
* [Microsoft.Azure.CognitiveServices.Vision.Face 2.2.0-preview](https://www.nuget.org/packages/Microsoft.Azure.CognitiveServices.Vision.Face/2.2.0-preview) client library NuGet package