---
title: About
---
Always liked technology, since I was little were my father taught me the first things I learnt about computers, from then I’ve learnt more and more over the years, a big part of the time by myself. I got the basis for programming from a school in Portugal, started with Pascal and Visual Basic, but most of the languages that I know were self-taught.

I’ve decide to come to England to take my BSc in Computer Science at Coventry University, because I wanted to expand my horizon, it has been awesome learning all this new languages and skills. Being here as taught me how to work more professionally, also how to improve efficient, test and document code.

<br>

<div class="about-skills">
    <div>
        <div class="about-icons">
            {% include logo-name.html logo="C++" %}
            {% include logo-name.html logo="Java" %}
            {% include logo-name.html logo="C#" %}
            {% include logo-name.html logo="Python" %}
            {% include logo-name.html logo="SQL" %}
        </div>
        <p>Laguanges I write</p>
    </div>
    <div>
        <div class="about-icons">
            {% include logo-name.html logo="Visual Studio" %}
            {% include logo-name.html logo="GitHub" %}
            {% include logo-name.html logo="Godot" %}
            {% include logo-name.html logo="Android Studio" %}
            {% include logo-name.html logo="Photoshop" %}
        </div>
        <p>Tools I work with</p>
    </div>
</div>



{% include title.html title="Contact Me" %}

<p id="contact-form-successful" class="contact-form-info contact-form-successful">Thank you for contacting me.</p>


<!-- Contact form -->
<form id="contact-form" class="contact-form">
  <div>
        <input type="text" id="name" placeholder="Name" name="entry.1606674600" required>
        <input type="email" id="email" placeholder="Email" name="entry.1980704307" required>
  </div>
  <div>
        <textarea id="message" placeholder="Message" name="entry.284157207" rows="10" required></textarea>
  </div>
  <div>
    <button type="submit" id="send">Send</button>
    <p id="contact-form-failed" class="contact-form-info contact-form-failed">There was an error sending the message, please try again.</p>
  </div>
</form>

<!-- Send to google forms -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script>
$('#contact-form').submit(function(e) {
    e.preventDefault();  

    $('#contact-form-failed').css('display', 'none');

    $.ajax({
        url: 'https://docs.google.com/forms/d/e/1FAIpQLSfp3G2xfyyieLi0u_3Qa61EkjzBCZvWNf1LFdBBmj1bEYml1w/formResponse',
        type: 'POST',
        data: {
            'entry.1606674600': $('#name').val(),
            'entry.1980704307': $('#email').val(),
            'entry.284157207': $('#message').val(),
        },
        statusCode: {
            0: function() {
                $('#contact-form-failed').css('display', 'block');
            },
            
            200: function() {
                $('#contact-form').css('display', 'none');
                $('#contact-form-successful').css('display', 'block');
            }
        }            
    });

    return false;
});
</script>