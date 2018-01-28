# Heroku Buildpack for Libreoffice

Makes no assumptions about the LibreOffice version. Simply links the `.apt` binary into the `vendor` directory.

To be used in conjuction with  [heroku-buildpack-apt](https://github.com/heroku/heroku-buildpack-apt)

```
heroku buildpacks:add --index 1 https://github.com/heroku/heroku-buildpack-apt.git
heroku buildpacks:add --index 2 https://github.com/sumeetattree/heroku-buildpack-libreoffice.git
```

Create an `Aptfile` at the project root
```
:repo:deb http://http.us.debian.org/debian stretch main

libreoffice
```
