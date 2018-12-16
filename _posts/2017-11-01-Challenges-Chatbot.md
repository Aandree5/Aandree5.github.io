---
title: Challenges Chatbot
githubLink: https://github.com/Aandree5/Chatbot-Jeff
categories: ["Python", "GitHub"]
---

A basic chatbot, in python, round the concept of a ‘pub quiz chatbot’. Able to ask question to the user and tell him fun facts, whilst able to maintaining a casual conversation.


{% include title.html title="Netwrok" %}
The server must be ran first, opening a connection for the client to connect to. The client is currently listening for messages from the server until he receives the string <code>"EndOfMessage"</code>, after that the client stops listening and prepares to send a message, the server in turn starts listening.
Every time a message is sent from either the server or the client, they hold sending more and wait for a <code>"Received"</code> message to check if it was successful or if needs to send again.

<center>
<code><span style="color: #008000; font-weight: bold">def</span> <span style="color: #0000FF">sendMessage</span>(message, EOM <span style="color: #5d5d5d">=</span> <span style="color: #008000">True</span>): 
    <span style="color: #BA2121; font-style: italic">''' Given a message input, and a False value, send the </span>
<span style="color: #BA2121; font-style: italic">message and the client keeps wayting for another message '''</span>
    resp <span style="color: #5d5d5d">=</span> <span style="color: #BA2121">""</span>
    <span style="color: #008000; font-weight: bold">while</span> (resp <span style="color: #5d5d5d">!=</span> <span style="color: #BA2121">"Received"</span>):             <span style="color: #408080; font-style: italic"># If not received</span>
        conn<span style="color: #5d5d5d">.</span>send(<span style="color: #008000">str</span>(message)<span style="color: #5d5d5d">.</span>encode())    <span style="color: #408080; font-style: italic"># Send message</span>
        <span style="color: #008000; font-weight: bold">print</span>(<span style="color: #BA2121">"SERVER: {}"</span><span style="color: #5d5d5d">.</span>format(message)) <span style="color: #408080; font-style: italic"># Print message sent</span>
        resp <span style="color: #5d5d5d">=</span> conn<span style="color: #5d5d5d">.</span>recv(<span style="color: #5d5d5d">1024</span>)<span style="color: #5d5d5d">.</span>decode()     <span style="color: #408080; font-style: italic"># Wait client feedback </span>
    <span style="color: #008000; font-weight: bold">if</span> (EOM):                               <span style="color: #408080; font-style: italic"># If is last message</span>
        conn<span style="color: #5d5d5d">.</span>send(<span style="color: #BA2121">"EndOfMessage"</span><span style="color: #5d5d5d">.</span>encode())  <span style="color: #408080; font-style: italic"># Was last message</span>
</code>
</center>


{% include title.html title="Information" %}
The chatbot connects to a free online database that has different types of questions with the respective answers, gets the information through the website's API that returns it in JSON format.

There's also three files that come together with the server, that were found online in another free website, they contain information that is used to show fun facts about historical events, famous birthdays or famous quotes, they are also used to build question for the user with that information.


{% include title.html title="Functionality" %}
With all that information the chatbot can build single or multiple question to challenges the user, give him historical fun facts or just try and have a casual conversation with the user, if it doesn't know the answer for any question it will perform a search on Google Search to try and answer the user.


{% include title.html title="Reflection" %}
It was a group work, so not everything was done by me, but the things that I done, although they work, they are not as efficient as they could be, some things would be done differently to improve performance and quality.
