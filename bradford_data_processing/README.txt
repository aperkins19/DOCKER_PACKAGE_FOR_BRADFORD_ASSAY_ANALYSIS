This app will allow you to easily analysed 96 well bradford assay data based on Alex's Bradford Protocol
You may have to change the dilutions & standards

Note: this is for windows only.

SETUP


BUILD AND RUN DOCKER CONTAINER.

1. Check Docker is installed.
e.g.

docker --version

2. Check that the docker Daemon is actually running.
This youtube vid will help.
https://www.youtube.com/watch?v=YFUhdxI4kcA

3. Download the repo from git or unzip the zip file.


4. Open command line and navigate to the folder bradford_data_processing

You can get the path by 'Copy address as text' in the URL of your file manager.
Be sure to stick it in quotes as below

cd "mypath"


5. Run the docker image.
Use Nadanai's Jupyter Docker Image.
e.g.
docker run -p 8888:8888 --rm -it -v "%CD%":/home/jovyan nadanai263/nllab-jupyter:005

If the image isn't already on your machine, it'll be downloaded.

The way it works is by:
a. starting a Docker Container
b. Mounting your current directory ("%CD%") to a directory in the container ("/home/jovyan") so that files can be shared and moved in and out.
c. starting a jupyter server.

6. If it has started correctly, you'll get a url token. Copy the token provided into your brower URL

It should look like this:

http://127.0.0.1:8888/?token=3c96d2a50decb4302c3e96b87ba7444d286e335d07c478fe

It should open up a Jupyter File explorer in the directory in your browser.


7. Move your rawdata file (.CSV) into the directory and check it's appeared in the Jupyter directory.

8. Open bradforddataprocessing.ipynb and execute all cells using the double arrow icon.

9. It will create an output directory, move the raw data file into it, perform the analysis and put the products into the output directory.
You can now move the output directory out and put it where ever you like.

10. Shutdown Jupyter by CTRL-C and typing 'y' ENTER when prompted.


https://www.youtube.com/watch?v=YFUhdxI4kcA