Gromit
==================================================

Gromit is primarily an OAuth2 client for AngularJS.  It's focused on the [Micro Focus](https://www.microfocus.com/) OAuth implementation called OSP, but it should work with generic OAuth2 providers.  

Along with OAuth2 support this library has support for other features like message handling in the UI, date formatting, safe HTML, and specialized CSS property handling.

Setting up the Gromit build environment
--------------------------------------

This project builds with [Gradle](http://gradle.org/gradle-download/).  Download the latest and add it to your path.  I like to create an alias for gradle like this:

<code>alias gr='~/bin/gradle-4.1/bin/gradle'</code>

Gromit also uses JSHint for JavaScript checking.  You must install JSHint to run the build.  JSHint depends on Node.js so the first step is to [install Node.js](http://nodejs.org/download/).  

Once you've installed Node.js you can run this command to install JSHint:

<code>npm install jshint -g</code>

Verify your setup by running the two following commands:

<pre><code>gradle -version</code>
<code>jshint -version</code></pre>

Get the Gromit source code:

<pre><code>git clone https://github.com/Gromit-Soft/gromit.git
git clone https://github.com/Gromit-Soft/gromit-sample.git</code></pre>

Building Gromit
--------------------------------------

Gromit is made up of two projects:  the Gromit core (just called Gromit) and the Gromit sample application which contains documentation and a running sample of Gromit.  Start by building the Gromit core:

<pre><code>cd gromit
gradle
</code></pre>

This build will create the Gromit core artifact and install it in your local Maven cache.  

The Gromit sample application contains an embedded server so you can easily run the application.  You can start it like this:

<pre><code>cd gromit-sample
gradle
</code></pre>

At this point your Gromit sample server will be running on [your local server](http://localhost:8081) on port 8081.  You can use this configuration to make live changes to the sample code.

Verifying the gromit-sample build
--------------------------------------

Once your change is complete you need to run an addition command to run JSHint and verify the build.  You must run this command before you commit your changes to gromit-sample.

<pre><code>gradle clean war
</code></pre>
