---
layout: page
title: About
permalink: /about/
---

{% image rogin-avatar.jpg alt="Logo" id="rogin" class="alignright" %}
<h2 id="subline"><em>Rogin Farrer is a theater-maker and pixel-pusher. He loves to tell stories, whether by designing for the stage or for the web. He also builds stuff with wood.</em></h2>

<h2 class="t-center">Welcome</h2>
	
Enough of the 3rd person. Hi there! My name is Rogin and I'm a theater-maker and pixel-pusher based in the Greater Boston area. I was born and raised just west of Boston.
	
My focus as a theater-maker is in lighting and scenic design and carpentry. I currently work for the <a href="http://gloucesterstage.com">Gloucester Stage Company</a> as their inaugural Scenic Design/Carpentry Apprentice.
	
I also design and develop websites. I especially love to create personal portfolios and blogs. I have a soft spot for typography and mobile-responsive design. I'm currently looking for clients. See my contact info below.
	
This site was built with [Jekyll][1], [GitHub][2], [Brackets.io][3], Terminal, [Sass][4], [Compass][5], and [Typekit][6].

[1]: http://jekyllrb.com/         "Jekyll"
[2]: http://github.com/           "Github"
[3]: http://brackets.io/          "Brackets Text Editor"
[4]: http://sass-lang.com/        "Sass"
[5]: http://compass-style.org/    "Compass"
[6]: http://typekit.com/          "Adobe Typekit"

<br />

<div id="form-messages"></div>
<p class="t-center"><strong>Get in touch via the form below!</strong></p>
<form id="contact-form" name="form">
<div>
<label>Name</label>
<input placeholder="Name (required)" name="name" type="text" tabindex="1" required>
</div>
<div>
<label>Email</label>
<input placeholder="E-mail (required)" name="_replyto" type="email" tabindex="2" required>
</div>
<div>
<label>Telephone</label>
<input placeholder="Tel #" type="tel" name="telephone #" tabindex="3">
</div>
<div>
<label>Message</label>
<textarea placeholder="Hi, Rogin..." type="text" name="message" tabindex="4" rows="5" required></textarea>
</div>
<input type="hidden" name="_subject" value="New RoginFarrer.com submission" />

<input type="text" name="_gotcha" style="display:none" />
<div>
<button type="submit" id="contact-submit" class="btn-send"><i class="fa fa-envelope"></i> Send Email</button>
</div>
</form>

<!-- Hidden message to show if contact is successful. -->
<div id="submit-success" class="collapse">
<h3 style="text-align:center;">Message received! I'll be in touch.</h3>
</div>

<!-- Hidden message to show if user encounters errors. -->
<div id="submit-errors" class="collapse">
It looks like there was an error submitting the form.
Please try again later.
</div>

<br />



<script>
$("#contact-form").validate({
submitHandler: function(form) {
$.ajax({
url: "//formspree.io/rogin@roginfarrer.com", 
method: "POST",
data: {
name: $(form).find("input[name='name']").val(),
_replyto: $(form).find("input[name='_replyto']").val(),
message: $(form).find("textarea[name='message']").val()
},
dataType: "json",
success: function() {
$("#submit-success").fadeIn();
$("#contact-form").fadeOut();
},
error: function() {
$("#submit-errors").fadeIn();        
}
});
}
});
</script>