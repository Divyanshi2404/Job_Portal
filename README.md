# Running the Project on Gitpod
The convenient method to run this project is to run it over Gitpod as you don’t have to download too
many things on your machine.

To run this project on Gitpod simply add https://gitpod.io/# in front of the github repositry link.

Now we have to setup the gitpod environment to run this project .


For frontend :
Open bash Terminal in your gitpod
Step 1 :- Head over to your frontend folder with the command
cd frontend
Step 2 :- Install npm to run the react setup
npm install
Step 3 :- Install reduxJS to run the Slices created
npm install @reduxjs/toolkit react-redux
Step 4 :- Install Testing Library React for the react setup
npm install --save-dev @testing-library/react @testing-library/jest-dom
If you want to run the tests manually you can run the command
npm test
Step 5 :- We have added tailwind graphics to our project that you need to download using
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
We are done with the frontend part of our project after this.


For backend :
Open bas Terminal in your gitpod
Step 1 :- Headover to the backend folder with the command
cd backend
Step 2 :- Ensure your enviroment is ready with JDK 17 or above if not then install it in your machine
To check java version use java -version
If its lower that Java 17 setup jdk 17 using a .gitpot.Dockerfile and add the given set of
code in that
FROM gitpod/workspace-full
# Install Java 17
RUN sudo apt-get update && \
sudo apt-get install -y openjdk-17-jdk
# Set Java 17 as the default Java version
RUN sudo update-alternatives --config java
RUN sudo update-alternatives --config javac
Step 3 :- Set java version for maven using and pom.xml file and aplly this code in that file
<build>
<plugins>
<plugin>
<groupId>org.apache.maven.plugins</groupId>
<artifactId>maven-compiler-plugin</artifactId>
<version>3.8.1</version>
<configuration>
<source>17</source>
<target>17</target>
</configuration>
</plugin>
</plugins>
</build>
Step 4 :- Clean and build the project
Clean the project using ./mvnw clean
Install the dependencies using ./mvnw install
Run the application using ./mvnw spring-boot:run
Now we are done with fixing the both frontend and backend environment in our gitpod


To run the overall project at once we need to create 2 terminals where
In Terminal 1 :-
cd frontend
npm start
In Terminal 2 :-
cd backend
./mvnw spring-boot:run
These commands will automatically build the whole project into your local browser port.
