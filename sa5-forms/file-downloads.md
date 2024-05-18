# File Downloads



## Download File Form

[https://discourse.webflow.com/t/file-download-on-form-submission-with-success-message/169929](https://discourse.webflow.com/t/file-download-on-form-submission-with-success-message/169929)

With success message.&#x20;



## Download File Link

Download file link

Changing the name of the saved file



[https://wishlist.webflow.com/ideas/WEBFLOW-I-819](https://wishlist.webflow.com/ideas/WEBFLOW-I-819)

Nice idea from Yeshai Lang

This can be done with some custom code. Embed the following script after the "Download File" button element:\
\<script>

document.getElementById('downloadButton').addEventListener('click', function() {

var fileNameWithPrefix = this.getAttribute('data-file');

var fileName = fileNameWithPrefix.substring(fileNameWithPrefix.indexOf('\_') + 1);

\


// Decode the filename to replace '%20' with actual spaces

fileName = decodeURIComponent(fileName);

\


// Create a temporary link element

var link = document.createElement('a');

link.href = 'path\_to\_download/' + fileName; // Replace 'path\_to\_download/' with your actual download path

link.setAttribute('download', fileName); // Set the download attribute to specify filename

link.style.display = 'none';

document.body.appendChild(link);

\


// Trigger the download

link.click();

\


// Cleanup: remove the temporary link element

document.body.removeChild(link);

});

\</script>\
\
And create a custom element set as a button:\
\<button id="downloadButton" data-file="\{{wf {\&quot;path\&quot;:\&quot;file-to-download\&quot;,\&quot;type\&quot;:\&quot;FileRef\&quot;\\} \}}" class="button">Download File\</button>\
replacing \{{wf {\&quot;path\&quot;:\&quot;file-to-download\&quot;,\&quot;type\&quot;:\&quot;FileRef\&quot;\\} \}} with the relevant field from your cms
