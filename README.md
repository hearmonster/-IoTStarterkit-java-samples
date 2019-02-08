# Java samples for the SAP Cloud Platform Internet of Things for the Cloud Foundry Environment

Contains various Java samples which illustrate the API usage across different use cases.

### Prerequisites

* Maven
* JDK 1.8 or higher

>IMPORTANT: After the very first import from GitHub, ensure to run `mvn clean install` for the current reactor project in order to build [commons](./commons) - a Maven module containing generic logic which is used by the provided samples.

## Upstream. Sending measures from the device.

* [Model "Ambient" measure and send its values either through HTTP or MQTT to the Gateway as well as consume them later on via the API](./send-measure)

## Downstream. Sending commands to the device.

* [Model "Switch" command and send it to the device as well as listen to incoming commands on the device side](./send-command)

# My Notes

## Compile in Eclipse
Ensure you've converted the Project to a Maven project (RMC on Project >> Configure >> Convert to Maven Project)

RMC on Project >> Run As... >> Maven clean
RMC on Project >> Run As... >> Maven install

The 'install' goal produces four jars, only two of which are usable
* send-measure/target/send-measure.jar (usable)
* send-command/target/send-command.jar (usable)
* commons/target/commons.jar (a dependency, used by the two jar above)
* target/java-samples.jar (worthless, avoid it)

## Preconfigure (prior to run)
Drop a 'sample.properties' file into: send-measure/target

(You'll find a template file here: send-measure/src/main/java/resources/sample.properties)

Or within Eclipse - run as an "External Tool"

>> External Tools (button)(looks like a green 'play' button but with a red suitcase) >> External Tool Configurations...

>> RMC on 'Program' >> New Configuration


Property | Value
-------- | -----
Name: | Java jar
Location: | C:\Program Files\Java\jdk1.8.0_201\bin\java.exe
Working Directory: | ${container_loc}
Argument: | -jar ${resource_loc}

## Run
The install produces four jars, only two of which are usable
* send-measure/target/send-measure.jar
* send-command/target/send-command.jar


command line: use "java -jar send-command.jar" to run

Eclipse:  RMC on Project >> External Tools (button) >> "Java jar"


