###YO-TOOLS

YO-tools is a repo of materials and scripts to assist me (and anyone really) in creating some slick HTML emails quickly and easily using a set of HTML extensions and Ruby scripts. The environment provides a few layouts that require a minimum level of knowledge of Ruby and HTML/CSS to use.

####Setup

You'll need the following things to use this suite of tools
```
bash
ruby
sass
premailer (ruby gem)
mail (ruby gem)
```
This repo also packages a slightly modified version of Ink, an email templating framework.

####Basic Use
* `./testmail.sh < <file>` is a one-shot script that, when properly configured, converts the templated file <file> to HTML and plaintext and then sends a multipart email to a specified account.
* `./sendmail.sh <file> <recipient email` does the same thing, only it also runs testmail and sleeps for 5 minutes before proceeding to send the message to the (presumably intended) recipient

####HTML Extensions + Building The Email
I define several HTML "tags" for use in order to make the delivery of content as smooth as possible. They abstract out annoying code bits and clutter but also severely limit the flexibility you have outside of these custom built "directives". Many of the names are self explanatory

All custom tags MUST reside on their own line, be followed by a line (or more) of content and be closed with a corresponding closing tag that also resides on its own line.
* `<subject>` Defines the subject of the email
* `<container` Container tag. You should start your email with this and close it with `</container>`
* `<header>`
* `<subtitle>`
* `<quotebox>` Useful for creating a space to put a quotation
* `<quote>`
* `<quotee>`
* `<row>` Creates a 12 column wide row with text padding.
* `<footer>`
* `<signoff>`
* `<signature>`
