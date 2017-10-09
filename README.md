Heroku buildpack: Stackray
==========================

A [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks)
for adding [Stackray](http://www.stackray.com/) Modeler into your
project.

Usage
-----

Use this buildpack with [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi):

	heroku buildpacks:add heroku/ruby
	heroku buildpacks:add http://github.com/stackray/heroku-buildpack-stackray.git
	
See Heroku docmentation [here](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app).

You can always check which buildpacks are currently set with:

	heroku buildpacks

Building:

    $ git push heroku master
    ...
    -----> Heroku receiving push
    -----> Fetching custom buildpack
    -----> Found a .stackray file
           Downloading jar https://s3.amazonaws.com/stackray/releases/stackray.jar
    ...

The buildpack will detect that your app has a `.stackray` file in the
root. It feches a tar and extracts a jar into your application's
root directory, and runs .profile.d/start-service.

