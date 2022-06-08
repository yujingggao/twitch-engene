# twitch-engene
Web app that allows users to search and get recommendation for twitch resources (stream/video/clip). Users can login to favorite records.

<img src="frontend/public/twitch_engene.png" width="800" >

# Requirements
The following instruction applies to Linux/MacOS development environment.

## ItelliJ Ultimate IDE
- Download and install the latest IntelliJ IDEA Ultimate from [here](http://jetbrains.com/idea/download). 
- Choose the Ultimate version (>=2020.02).
- Refer to [Installation Guide](https://www.jetbrains.com/help/idea/run-for-the-first-time.html)to perform the initial setup
## Apache Tomcat
- Open [this page](http://tomcat.apache.org/download-90.cgi), and select the binary based on your US under the `Core` section
	- Mac: tar.gz
	- Windows: 64-bit Windows zip
- For macOS user only: make the `catalina.sh` script in the bin folder executable.  `cd` to your apache-tomcat directory, then run the following command
```shell
>$ chmod 755 bin/catalina.sh
```
## Java
- Download Java 8 or higher from [here](https://www.oracle.com/java/technologies/downloads/#java8)

# Backend Configuration
## Apache Tomcat
Open the `first` folder In the ItelliJ IDE, and add Apache Tomcat as a Run/Debug configuration, so that the IDE knows how to run the program.  
- On top right of the IDE, click `Add Configuration...`
- In the new window, select `Add new` - `Tomcat Server` - `Local`
- In the new dialog, under the `Server` tab, click the `Configure...` button on the right of `Application server`
- Specify the _Tomcat Home_. Locate where the Tomcat directory you saved on your disk
- There will be a warning at the bottom.  Click `Fix`, and in the new window select the `Problem` tab, and define the project SDK
- Close the Configuration window
- There will be a small window on the bottom right of the IDE that says `Maven built project found`.  Select `first`
- Open the configuration window again, and click `Fix` in warning, and choose `first: war exploded`
- Under the deployment tab, change the application context to `/`
- Click `OK` to apply and save all changes

## Database
This project is using RDS MySQL engene from AWS.  If you'd like to connect to another database, the following code in ` ` needs to be modified


## Start the Backend Server
- On the tab of the right side of the IDE, find the `Maven` tab
- Select `first` - `Lifecycle` - `clean` to clear all previous builds
- Select `first` - `Lifecycle` - `install` to start a new build
- Now we have a Run_/Debug Configuration_ setup. You can build and run by clicking the green ▶️ button
- Open your browser and use the following address to make sure your Tomcat server is running correctly: [http://localhost:8080/]

# Start the Frontend Server
Go to `frontend` folder and install modules from package.json
```shell
>$ npm install 
```

Start the fronend server
```shell
>$ npm start
```
