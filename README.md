Heroku buildpack: Stackray
==========================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks)
for adding [Stackray](http://www.stackray.com/) Modeler into your project.

Usage
-----

To compile your heroku app use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to
combine it, along with a Java buildpack and your existing language/stack buildpack.

Building
--------

    $ heroku create --stack cedar --buildpack http://github.com/stackray/heroku-buildpack-stackray.git

    $ git push heroku master
    ...
    -----> Heroku receiving push
    -----> Fetching custom buildpack
    -----> Found a .stackray file
           Vendoring https://s3.amazonaws.com/stackray/stackray.jar
    ...

The buildpack will detect that your app has a `.stackray` file in the
root. It feches a tarball and extracts a jar into your application's
root directory, and runs .profile.d/start-service.

