
# Notes

* this example is not intended to illustrate a multi-project build, so there is no `settings.gradle` at the root 

* set `SOURCE_BUILD_NUMBER` environment variable

* substitute `DOCKER_HOST` in `build.gradle` with the appropriate value

* to publish the common jar to Artifactory:

<pre>
cd common
gradle publishCodetojoyPublicationToRemoteArtifactoryRepository
</pre>

* to test the common jar via the server project:

<pre>
cd server
gradle test
</pre>

* experiment like so:
    * modify the `UserDto.VERSION`
    * bump the `SOURCE_BUILD_NUMBER` and rebuild, republish etc

* to test the common jar via the webapp project:

<pre>
cd web
gradle clean jettyRunWar
</pre>

and browse to `http://localhost:8080/codetojoy-user/`

* to publish the webapp WAR file to Artifactory:

<pre>
cd web
gradle publishCodetojoyWebAppPublicationToRemoteArtifactoryRepository
</pre> 

* to pull the webpp WAR file from Artifactory (in a simulated deployment):

<pre>
cd web-deploy
gradle deployWarToDir
</pre>
