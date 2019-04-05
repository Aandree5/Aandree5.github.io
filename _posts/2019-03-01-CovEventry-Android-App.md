---
title: CovEventry - Android App
githubLink: https://github.com/Aandree5/CovEventry.git
categories: ["Java", "Android Studio", "GitHub", "PHP", "SQL"]
organization: "Coventry Univeristy"
---


An Android app built to show all events around the user in one place. Is able to check the app own database for special events created in it but also scans tweets around the user relating to events and show them on a map for the user to see.


{% include title.html title="Login" %}
This app doesn’t use a username and password login to simplify its use, having no need to memorize one more password, instead it uses social media to give special functions to the user, like connecting with friends and inviting to events (feature to be added in the future). It contains custom views to allow the user to seamlessly login with either Facebook or Twitter, or both, that will then be saved on the database and synced across devices.


{% include title.html title="Twitter Events" %}
It also uses Twitter to retrieve events from posts, first it gets the user location, which will in turn ask Google for the address for that location and retrieve the user current city, uses that information to query the Twitter API (with custom built classes) to retrieve the events around the user with a special query to filter mostly events, after that it goes through each event to check if the free typed user location is the same city as the user, the last step is to pinpoint that event venue on a map, for that it queries Google Places API with the user location to retrieve a place around the user with the username from the tweet, showing it on the map after.


{% include title.html title="Database" %}
To interact with the database the app connects to PHP webservices, that will perform the operations on the database, it's a safer a cross platform approach. The events saved on the database are straight forward, they have all the needed information and the app just requests the events of the day, downloads the images and has everything it need to proper show to the user.


{% include title.html title="Usability" %}
Fragments are used to follow Google's design patterns a give the user an experience that his used to, with the system apps, also loads the important part as soon as the user opens the app, which removes the need to go through the app looking for the needed information, the user can even, with just a tap, swap to a list view instead of the map.
