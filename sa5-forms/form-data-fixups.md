# Form Data Fixups

e.g.

* Preserving line breaks

```
<script>
document.addEventListener("DOMContentLoaded", function() {
    var form = document.getElementById('id-of-form');
    form.addEventListener('submit', function(event) {
        event.preventDefault(); // Prevent the form from submitting immediately

        // Get the textarea value
        var textarea = document.getElementById('id-of-textarea');
        var modifiedText = textarea.value.replace(/(\r\n|\r|\n)/g, '\\n');

        // Set the modified text back to the textarea or prepare it for sending
        textarea.value = modifiedText;

        // Now submit the form programmatically
        form.submit();
    });
});
</script>
```
