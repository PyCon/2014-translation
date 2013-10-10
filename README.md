Translation
The PyCon site is set up for use in English and French, for the most part.

[Glossary](https://github.com/PyCon/2014/wiki/Glossary)
if you need to find out our conventions and our wording choices

### Which language is displayed
By default, the request headers control which language is displayed. A user can change their brower's settings to say what their preferred languages are, and if French comes before English, the site will use French when available. It'll fall back to English for text that isn't translated.

A language selector can optionally be displayed on the Dashboard page. This allows a user to temporarily override the displayed language for the current session. Whether the language selector is displayed is controlled by the django-constance setting SHOW_LANGUAGE_SELECTOR, which can be changed in the admin at /YEAR/admin/constance/config/.

### Translating
For CMS pages, there are two body fields. The first is for English. The second is for French. You'll have to scroll down a ways to see it when editing a CMS page.

Text on most other pages, forms, etc is translatable using Django's internationalization support. To add or update translations, a developer would:

set up a local development environment for PyCon according to the README
make a new branch off the develop branch
make sure you have Gnu gettext installed
install fabric: pip install fabric
run fab make_messages to update the .po files, in case any translatable text has changed
edit locale/fr/LC_MESSAGES/django.po, filling in msgstr with the translated version of whatever text is in the msgid just above it.
run fab compile_messages to update the .mo file with the new translations
commit the updated .po and .mo files
open a pull request against the main repo to get your updates included
If a non-developer is going to help with translation, a developer could do all the steps except editing the .po file, just sending the .po file to the translator for them to edit and send back.

Any text not translated in the translation files will be displayed as English.

### How to contribute

For the CMS pages:

A) First option

1. Pick a task:

https://github.com/PyCon/2014-translation/issues?state=open

2. Translate it by just adding the equivalent in french in the ticket itself !

3. Let us know that you are done by closing your ticket !

B) Second option (but you need to have access to the django admin of the website)

1. Create an account on the PyCon website

2. Pick an issue in the translation milestone:

https://github.com/PyCon/2014-translation/issues?state=open

3. Head your browser to: https://us.pycon.org/2014/admin/cms/page/

4. Translate !
