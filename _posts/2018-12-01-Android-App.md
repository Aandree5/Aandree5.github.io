---
title: Android App
githubLink: https://github.com/Aandree5/AndroidApp
categories: ["Java", "Android Studio", "GitHub"]
organization: "Coventry Univeristy"
---


An Android app built to consolidate the University information in one place. Able to check the news form the University and go through the enrolment process.


{% include title.html title="Database" %}
For the connection to the database this app uses PHP as a webservice, improving security and allowing for easier portability, since the conde doesn’t need to be embedded in the app itself. 
To connect to the PHP file, the app uses an Interface built for this purpose that get a HashMap with the key-pair values to query the server, the PHP than return the appropriate response which the app will then read.


{% include title.html title="Design" %}
The design contains different custom views to allow the app to adhere to the platform design patterns whilst having a University focused theme. The theme is kept simple and bold, so it doesn’t overcomplicate the visual effect but still gets the user attention.


{% include title.html title="Usability" %}
Fragments and activities are used as needed to help with usability, keeping the same flow that the user is used to, with the platform. Different navigation views are used depending on their needed function.