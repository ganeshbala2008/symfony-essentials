Configurations based on environments:

<b>Development:</b>
<p>Build the image:</p>
<p>docker-compose -f docker-compose.yml -f docker-compose.debug.yml build</p>

<p>Run the containers:</p>
<p>docker-compose -f docker-compose.yml -f docker-compose.debug.yml up -d</p>

Note: Xdebug is configured automatically when the above command are executed.

<b>Production:</b>
<p>Build the image:</p>
<p>docker-compose build</p>

<p>Run the containers:<p>
</p>docker-compose up -d</p>
Note: Remove the xedbug configuration in the docker file
