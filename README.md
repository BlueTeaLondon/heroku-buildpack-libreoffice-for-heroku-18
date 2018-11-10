# Working LibreOffice 6.1 buildpack for the heroku-18 stack 🎉

A frustration-free, working recipe for LibreOffice 6.1 on the heroku-18 stack, after a lot of trial & error. Particularly useful if you use the `libreconv` gem for document conversion to PDF in Ruby on Rails applications, and results in a much smaller slug size (which will likely keep you under heroku's soft limit as an added bonus) when compared to the java buildpack alternative.

Add the `heroku-buildpack-apt` buildpack to your project:
```
heroku buildpacks:add --index 1 https://github.com/heroku/heroku-buildpack-apt.git
```

Add our LibreOffice buildpack to your project:
```
heroku buildpacks:add --index 2 https://github.com/BlueTeaLondon/heroku-buildpack-libreoffice-for-heroku-18.git
```

Create an `Aptfile` file in your project root with the following content only:
```
libreoffice
libharfbuzz0b
libharfbuzz-icu0
```

Redeploy your project after committing the above file.
