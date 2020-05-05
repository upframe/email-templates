# ✉️  Email Templates

These are all the email templates used by Upframe. All the files in the [email directory](emails) on master are 
automatically uploaded to the [email S3 bucket](https://console.aws.amazon.com/s3/buckets/upframe-email-templates/?region=eu-west-2)
where the API will load them from.

The emails are written in [MJML](https://mjml.io/documentation/) which makes it a lot less painful to create templates
that display consistently in different clients. Some of the old templates might still be written in plain HTML, but they
will be converted as soon as we need to modify them.

You can use the [Mustache templating language](https://mustache.github.io/mustache.5.html) to add placeholders that will
be dynamically filled in when the API compiles & sends the template. E.g. `Hello {{ name }},` might be converted to `Hello John,`.
You can also use it to perform more advanced operations like excluding sections. Please read it's documentation (it probably won't take you
longer than 5 minutes). If you are adding new mustache tags, you will of course need to make sure that the API knows how to fill
them in when sending the email.

If you are using VS Code to edit the email templates, I would recommend to install the [MJML extension](https://marketplace.visualstudio.com/items?itemName=attilabuti.vscode-mjml)
which gives you a live preview of what the email will look like.
