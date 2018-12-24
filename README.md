# slack-dark-them
dark theme for slack

On a Mac, navigate to this directory:

`cd /Applications/Slack.app/Contents/Resources/app.asar.unpacked/src/static`

Edit the file ssb-interop.js with a text editor.
`open ssb-interop.js`

Add this code to the very bottom

```
document.addEventListener('DOMContentLoaded', function() {
 $.ajax({
   url: 'https://raw.githubusercontent.com/atoomic/slack-dark-theme/master/dark.css',
   success: function(css) {
     let overrides = `
     code { background-color: #535353; color: #85c5ff; } /* Change color: to whatever font color you want */
     .c-mrkdwn__pre, .c-mrkdwn__quote { background: #535353 !important; background-color: #535353 !important; }
     `
     $("<style></style>").appendTo('head').html(css + overrides);
   }
 });
});
```

Save the file and restart Slack, you should have a Dark theme!

Source: https://dev.to/changoman/easy-dark-mode-for-slack-1mmn
