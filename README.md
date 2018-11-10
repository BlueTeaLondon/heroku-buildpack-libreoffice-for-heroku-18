# Fully working LibreOffice 6.1.3 buildpack for the heroku-18 stack 🎉

Shamefully simple, and utilising an official AppImage copy of LibreOffice with its dependencies directly from the vendor... a frustration-free, working buildpack for LibreOffice 6.1.3 (others possibly supported via a variable change) on the heroku-18 stack (others possibly supported but you may be asking for trouble if you try), after a lot of trial & error.

Particularly useful if you use the `libreconv` gem for document conversion to PDF in Ruby on Rails applications, and results in a manageable slug size (which will likely keep you under heroku's soft limit as an added bonus) when compared with other options.

If you need the additional capabilities of headless LibreOffice 6.x particularly for closer conversion of files to accurate PDF files, this buildpack is for you.

Add the `heroku-buildpack-apt` buildpack to your project:
```
heroku buildpacks:add --index 1 https://github.com/heroku/heroku-buildpack-apt.git
```

Add our LibreOffice buildpack to your project:
```
heroku buildpacks:add --index 2 https://github.com/BlueTeaLondon/heroku-buildpack-libreoffice-for-heroku-18.git
```

Optionally, add the following buildpack, which provides a handy combination of fonts for LibreOffice to use:
```
heroku buildpacks:add --index 3 https://github.com/debitoor/heroku-buildpack-converter-fonts.git
```

Create an `Aptfile` file in your project root with the following content (do NOT include libreoffice here):
```
libsm6
libice6
libxinerama1
libdbus-glib-1-2
libharfbuzz0b
libharfbuzz-icu0
```

Redeploy your project after committing the above file, et voilà...!
