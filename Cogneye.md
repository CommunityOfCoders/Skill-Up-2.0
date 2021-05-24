![HTML](https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white)
![Javascript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Ruby](https://img.shields.io/badge/Ruby-CC342D?style=for-the-badge&logo=ruby&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-0095D5?&style=for-the-badge&logo=kotlin&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)
![bootstrap](https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=whi)
# CognEye

## Team Members
* [Jaivanti Dhokey](https://github.com/jaivanti)
* [Atharva Alshi](https://github.com/atharva1608)
* [Sanika Gadge](https://github.com/Sanikagadge15)
* [Vriddhi Gupta](https://github.com/Vriddhigupta)
* [Krishna Ashar](https://github.com/Krishna26Ashar)
* [Chanchal Agrawal](https://github.com/chanchal221b)
* [Aishwarya Harkare](https://github.com/Aishwarya856)
* [Purva Anjarlekar](https://github.com/Caddonix)

## Mentor
* [Shreyansh Chordia](https://github.com/shreyanshchordia)

## Description
The cogneye app opens up with a logo screen, which further moves towards a screen which reads out App features. User can either click on any of the feature or speak out the name of the feature. Eventually the feature will activate camera of the smartphone. Once the Phone's camera is moved around an object/Letter/Paragraph, the voice is enabled and it reads out the object/letter/paragraph aloud.
Currently, the app is still in development mode, cogneye team is working efficiently to improve the quality of the app.
> Code snippet for splash screen
```bash
val SPLASH_TIME_OUT = 4000.toLong()
Executors.newSingleThreadExecutor().execute {
       Thread.sleep(SPLASH_TIME_OUT)
       startActivity(Intent(this, MainActivity::class.java))
       finish()
}
```

>Code Snippet for OCR feature.

```bash
SparseArray<TextBlock> sparseArray = detections.getDetectedItems();
StringBuilder stringBuilder = new StringBuilder();

       for (int i = 0; i<sparseArray.size(); i++){
              TextBlock textBlock = sparseArray.valueAt(i);
               if (textBlock != null && textBlock.getValue() !=null){
                     stringBuilder.append(textBlock.getValue() + " ");
                    }
                }

final String stringText = stringBuilder.toString();
```

> Code snippet for Object detection
```bash
private fun bindPreview(cameraProvider: ProcessCameraProvider){
        val preview = Preview.Builder().build()
        val cameraSelector =CameraSelector.Builder()
            .requireLensFacing(CameraSelector.LENS_FACING_BACK)
            .build()
        preview.setSurfaceProvider(binding.previewView.surfaceProvider)
        val imageAnalysis = ImageAnalysis.Builder()
            .setTargetResolution(Size(720,1280))
            .setBackpressureStrategy(ImageAnalysis.STRATEGY_KEEP_ONLY_LATEST)
            .build()
        imageAnalysis.setAnalyzer(ContextCompat.getMainExecutor(this),ImageAnalysis.Analyzer{ imageProxy ->
            val rotationDegrees = imageProxy.imageInfo.rotationDegrees
            val image = imageProxy.image
            if (image != null){
                val processImage= fromMediaImage(image,rotationDegrees)
                objectDetector
                    .process(processImage)
                    .addOnSuccessListener { objects ->
                        for (i in objects){
                            if(binding.parentLayout.childCount >1) binding.parentLayout.removeViewAt(1)
                            val element = Draw(context =this,
                                rect = i.boundingBox,
                                text = i.labels.firstOrNull()?.text ?: "Undefined")
                            binding.parentLayout.addView(element,1)
                            fun processTexttoSpeech() {
                                val objectname = i.labels.firstOrNull()?.text ?: "Undefined"
                                tts!!.speak(objectname, TextToSpeech.QUEUE_FLUSH, null, "")
                            }
                            processTexttoSpeech()
                        }
                        imageProxy.close()
}
```

>Code snippet from android manifest file.
```bash
    <uses-permission android:name="android.permission.CAMERA"></uses-permission>
    <uses-permission android:name="android.permission.RECORD_AUDIO"></uses-permission>
```

<!--Don't forget to replace the link here with **_your own Github repository_** link. -->

## Important Links

* GitHub repo link: [CognEye Repo](https://github.com/CognEye/CognEye)
* Drive link: [CognEye drive link](https://drive.google.com/drive/folders/1pjNYFkQNOuKjL1RA7lDQqLeqY4qTpyS_?usp=sharing)
* Website link: [CognEye Website](https://cogneye.github.io/)

## Technology stack

Tools and technologies that you learnt and used in the project.

1. Java
2. Kotlin
3. HTML/CSS
4. Javascript
5. Python
6. Android Studio

## Applications
1. CognEye will act as bridge for visually impaired people to see the world through the features like object detection, optical character recognition, facial recognition, etc.
2. CognEye will activate camera and voice technologies in smartphones, to identify objects, letters, paragraph, etc around the user.
3. It will also provides a inbuilt voice assitance to help the user with understanding the app features and its use.

## What team members learned from this project



1. **Jaivanti Dhokey:** "Working with cogneye team was an amazing learning experience for me. Right from brainstorming various ideas and implementing them to deploying ML Models and entire website, Learning more about web development and ML field, has added a lot of wisdom to explore more deeply in this field."
2. **Atharva Alshi:** "Working with the team on this project was a wonderful experience.I along with my teammate Sanika implemented ML model Object Detection using ML-kit.Using TextToSpeech intent we implemented it on our model so the app speaks which object is has detected.Overall experience was really amazing and got to learn alot from the other group members as well. "
3.  **Sanika Gadge:** "Overall this was a great experience. I along with my team-mate Atharva specifically worked on Object Detection feaute of the app. We integrated a pre trained tensorflow object detection model to our UI. I learned alot of new things in various domains like ML and small introduction to Android Studio. I would just like to thank SkillUp for providing us with this opportunity and opening so many domains for learning." 
4. **Vriddhi Gupta:** - "It was a surreal experience for me. While working on this project I learnt implemenating ML models like facial recognition model. We couldn't use API for facial recognition feature since all were paid , hence I along with my partner Krishna implmented the entire facial recognition program from scratch but we could not add  this feature into our app because we still need to implement server client feature in order to use this model with the app. It was a great expereince while working on the UI with my UI team. I learnt the fact that as a part of a team we should always be ready to help each other."
5. **Krishna Asher:** "Working on this project with the CognEye team was an incredible opportunity for me. I finally got my courage up and started working on Ml concepts, learning how to apply machine learning models such as facial recognition, thanks to the encouragement of our mentor Shreyansh and the determination displayed by my fellow team mates to build an incredible project. Vriddhi and I designed our own facial recognition model from the ground up because we couldn't use APIs for facial recognition because they were all paid. However, we were unable to integrate this model into our app because, in order to do so, we needed to create a web server application to handle the requests from our app ."
6. **Chanchal Agrawal:** "I learned alot of new things in the course of this project. Everybody pitching in their new ideas and implementing them was fun. I was part of the OCR team and got to learn about new libraries and APIs. I also learned about front end development and it was overall a great experience."
7. **Aishwarya Harkare:** "Collaborating with team CognEye was wonderful experience for me! In this project meant for people with low vision I , along with my colleague Purva Anjarlekar implemented the Optical Character Recognition(OCR) feature. We used Google Mobile vision API available online for this purpose and integrated it with the app. Also I contributed in making UI for the app. Co-ordinating with the team was a great experience and I  was able to dive into whole new world of ML and App development while working on this project." 
8. **Purva Anjarlekar:** "I had just started learning ML when I joined this group project. It helped me a lot with implementation and understanding concepts. We specifically didn't work on developing a model but learning to work with APIs and integrating it with the app was very interesting to do. Thank you for this opportunity provided by SkillUp compelling me to study the subject."

## Future scope
1. We will deploy the facial recognition model that is already implemented.
2. Voice activation for opening the app and using it's feature can be also added to this app making it easy to use for visually impaired people.
3. We will also be testing our applcation on certain visual impared people to do more improvisation.
4. We will also be working on more features like location detection, Voice based QR code scanner, etc.

## Screenshots

![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM%20(4).jpeg)
![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM%20(3).jpeg)
![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM%20(2).jpeg)
![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM%20(1).jpeg)
![Screenshot alt text](https://github.com/Vriddhigupta/CognEye-1/blob/main/WhatsApp%20Image%202021-05-21%20at%202.10.08%20PM.jpeg)
