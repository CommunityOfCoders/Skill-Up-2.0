
# Skillup WOmen Safety App

## Team members
* Alicia Sunny
* Neha Binwal
* Sneha Balwani
* Sneha Takle
* Vedika

## Mentors
* Palak
* Saif
* Hrishikesh

## Description

* Shaking the phone 7 times is enough when in you feel the Danger.
* It sends message to 3 people about current location with a quote "I might  need help. With location_link."
* We do have a special pattern of shaking i.e 7 times side-by-side.
* To make sure it doesn't move by accident   
* Also it needs to move approximately 7 times a bit aggressively to function.
* User can edit/change the registered name, three contacts and profile image in the app's profile.
* About app and how to use it also mentioned in help section.
* User can sign out if they want.


```bash
    Add appropriate code snippets here (4 spaces indent)
```

>val x = event.values[0]
            val y = event.values[1]
            val z = event.values[2]
            lastAcceleration = currentAcceleration
            currentAcceleration = sqrt((x * x + y * y + z * z).toDouble()).toFloat()
            val delta: Float = currentAcceleration - lastAcceleration
            acceleration = acceleration * 0.9f + delta
            if (acceleration > 12) {
                count++
            }
            if(count == 7){
                count = 0
                Toast.makeText(applicationContext, "Shake event detected in service", Toast.LENGTH_SHORT)


* GitHub repo link: [Link to repository](https://github.com/vedika-2000/Womans-Safety-App)
* Drive link: [Drive link here](https://drive.google.com/)

## Technology stack
1. Frontend - XML
2. Backend - Kotlin , Firebase
3. Database - Firestore

Tools and technologies that you learnt and used in the project.

1. Kotlin
2. Android App Development
3. Firebase
4. Google maps to show location.

## Applications
>How can your project do its part in solving a real-life problem? What are its possible applications? Decribe here.

1. This project is implemented to enhance women security by just shaking up your android phone several time when you feel in danger/unsafe it provides you to send your location to three contacts with which user is registered without dealing with any complicated procedure.
2. This android app makes easy tool to send your location to your family/friends at the same time.
3. Really helpful for women to give them a sense of protection

## What did you learn from this project

Each team member and mentor can briefly describe what they learnt during Skill Up 2.0, how they applied it to their project and what challenges they faced.

1. Alicia : Learnt Android development in Kotlin. Developed knowledge in front end development.
2. Neha Binwal: Learnt Android app development using kotlin.
3. Sneha: Learnt Android app development using kotlin. Got to know about various services android provides and their implementation basics. Learnt how to use firebase with an android app for authentication, and storing and retrieving data.
4. Sneha Takle - "As a beginner I got to learn basics of App development. "
5. Vedika - Learnt Android app development using kotlin . Learnt how to use firebase , Firestore database to retrieve the data.

## Future scope
>Mention ways in which the project can be improved and built upon in the future.

1. One of three contacts registered can have a call for emergency.
2. If a user shook phone in particular area several times we can save that area or location and pre-notify users if they are entering that area as " It is an unsafe area. "


## Screenshots
Add a few screenshots here to give the viewer a quick idea of what your project looks like. After all, a picture speaks a thousand words.

You'll have to link the screenshots from your drive folder here.

![image](https://drive.google.com/uc?export=view&id=1wqAOgAqbprguHI7gtackJ1PCSHNojisZ)
![image](https://drive.google.com/uc?export=view&id=1AdShdxao6lbYpIjOIkeAR9KtI6N2Y0Al)
![image](https://drive.google.com/uc?export=view&id=1m5uXn8yjIKVa-wGfV_rEyLhAJxqy1aln)
![image](https://drive.google.com/uc?export=view&id=15-n8edf_78UvGxOhvyuJzymGJZ6Al3ZJ)
![image](https://drive.google.com/uc?export=view&id=1CoALO6LhfwH5dgQ9NjUqzFtq3u_r14Ju)
