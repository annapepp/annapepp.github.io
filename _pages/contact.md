---
layout: page
title: Contact
image: background.png
---
<script>
function getParams() {
   var idx = document.URL.indexOf('?');
   var params = new Array();
   if (idx != -1) {
      var pairs = document.URL.substring(idx+1, document.URL.length).split('&');
      for (var i=0; i<pairs.length; i++) {
         nameVal = pairs[i].split('=');
         params[nameVal[0]] = nameVal[1];
      }
   }
   return params;
}
params = getParams();
</script>

{% if site.contact-subtitle %}
<h5 class="contact-subtitle">{{ site.contact-subtitle }}</h5>
<hr>
{% else %}
{% endif %}
<form action="https://formspree.io/f/{{ site.form-id }}" method="POST" class="form">
  <div class="form-group">
    <label for="form-name">Your Name (Required)</label>
    <input class="form-input" type="text" name="name" id="form-name" required>
  </div>
  <div class="form-group">
    <label for="form-email">Your Email (Required)</label>
    <input class="form-input" type="email" name="_replyto" id="form-email" required>
  </div>
  <div class="form-group">
    <label for="form-subject">Subject</label>
    <input class="form-input" type="text" name="subject" id="form-subject" value="">
  </div>
  <div class="form-group">
    <label for="form-text">Your Message (Required)</label>
    <textarea class="form-textarea" name="text" rows="12" id="form-text" required></textarea>
  </div>
  <div class="form-group">
    <button type="submit" class="form-btn btn btn-big">Send</button>
  </div>
</form> <!-- /.form -->

<script>
   var inputbox=document.getElementById('form-subject');
   if (params["subject"]) { inputbox.value=unescape(params["subject"]) }
</script>


