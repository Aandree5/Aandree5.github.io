---
title: Challenges Chatbot
githubLink: https://github.com/Aandree5/Chatbot-Jeff
categories: ["Python", "GitHub"]
organization: "Coventry Univeristy"
---

A chatbot around the concept of a ‘pub quiz chatbot’. Can test the user with questions and tell him fun facts, whilst maintaining a "casual" conversation.


{% include title.html title="Netwrok" %}
The server must be ran first, opening a connection for the client to connect to. The client is currently listening for messages from the server until he receives the string ```"EndOfMessage"```, after that the client stops listening and prepares to send a message, the server in turn starts listening.
Every time a message is sent from either the server or the client, they hold sending more and wait for a ```"Received"``` message to check if it was successful or if needs to send again.


```python
def sendMessage(message, EOM = True): 
    ''' Given a message input, and a False value, send the 
message and the client keeps wayting for another message '''
    resp = ""
    while (resp != "Received"):             # If not received
        conn.send(str(message).encode())    # Send message
        print("SERVER: {}".format(message)) # Print message sent
        resp = conn.recv(1024).decode()     # Wait client feedback 
    if (EOM):                               # If is last message
        conn.send("EndOfMessage".encode())  # Was last message 
```


{% include title.html title="Information" %}
The chatbot connects to a free online database that has different types of questions with the respective answers, gets the information through the website's API that returns it in JSON format.

There's also three files that come together with the server, that were found online in another free website, they contain information that is used to show fun facts about historical events, famous birthdays or famous quotes, they are also used to build question for the user with that information.


{% include title.html title="Functionality" %}
With all that information the chatbot can build single or multiple question to challenges the user, give him historical fun facts or just try and have a casual conversation with the user, if it doesn't know the answer for any question it will perform a search on Google Search to try and answer the user.


{% include title.html title="Reflection" %}
It was a group work, so not everything was done by me, but the things that I done, although they work, they are not as efficient as they could be, some things would be done differently to improve performance and quality.