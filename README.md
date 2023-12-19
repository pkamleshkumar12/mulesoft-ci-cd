# Mulesoft CI/CD Jenkins

# Pre-requisites

1. Java
2. Maven
3. Git setup

# Implement Mule Project & Push to GitHub

```java
<build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-clean-plugin</artifactId>
				<version>3.2.0</version>
			</plugin>
			<plugin>
				<groupId>org.mule.tools.maven</groupId>
				<artifactId>mule-maven-plugin</artifactId>
				<version>${mule.maven.plugin.version}</version>
				<extensions>true</extensions>
				<configuration>
					<uri>https://anypoint.mulesoft.com</uri>
					<muleVersion>4.4.0</muleVersion>
					<username>Mule-playground</username>
					<password></password>
					<applicationName>Mulesoft-CICD-app</applicationName>
					<environment>Sandbox</environment>
					<worker>1</worker>
					<workerType>Micro</workerType>
					<objectStoreV2>true</objectStoreV2>
				</configuration>
			</plugin>
		</plugins>
	</build>
```

### Setup Jenkins

[macOS Installers for Jenkins LTS](https://www.jenkins.io/download/lts/macos/)

# Create Pipeline Items

### 1. Create a new Item for checkout

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%201.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%202.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%203.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%204.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%205.png)

### 2. Create a new Item for Build

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%206.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%207.png)

### 3. Configure Post-build action

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%208.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%209.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2010.png)

### 4. Configure the Built step

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2011.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2012.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2013.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2014.png)

### 5. Create a new Item for Deploy

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2015.png)
```
// for setting the password use below code
-Danypoint.password=somePassword
```
![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2016.png)

### 6. Verify Plugins

Make sure to have plugins

1. Git
2. Maven Integration plugin
3. Pipeline Integration

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2017.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2018.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2019.png)

![Untitled](Mulesoft%20CI%20CD%20Jenkins%20c6c243a9357d42868567eccff9077a79/Untitled%2020.png)

# Verify Deployment in CloudHub