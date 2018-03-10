# A simple, minimal Maven example: hello world

To create the files in this git repo we've already run `mvn archetype:generate` from http://maven.apache.org/guides/getting-started/maven-in-five-minutes.html

    mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

Now, to print "Hello World!", type either...

    cd my-app
    mvn compile
    java -cp target/classes com.mycompany.app.App

or...

    cd my-app
    mvn package
    java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App

Running `mvn clean` will get us back to only the source Java and the `pom.xml`:

    murphy:my-app pdurbin$ mvn clean --quiet
    murphy:my-app pdurbin$ ack -a -f
    pom.xml
    src/main/java/com/mycompany/app/App.java
    src/test/java/com/mycompany/app/AppTest.java

Running `mvn compile` produces a class file:

    murphy:my-app pdurbin$ mvn compile --quiet
    murphy:my-app pdurbin$ ack -a -f
    pom.xml
    src/main/java/com/mycompany/app/App.java
    src/test/java/com/mycompany/app/AppTest.java
    target/classes/com/mycompany/app/App.class
    murphy:my-app pdurbin$ 
    murphy:my-app pdurbin$ java -cp target/classes com.mycompany.app.App
    Hello World!
