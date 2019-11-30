life cycle demo

# command

mvn archetype:generate
mvn install -X
mvn install -Pproduction -X
mvn help:active-profiles
mvn help:active-profiles -Pproduction
mvn -Denvironment.type=prod install -X

add following content to ~/.m2/settings.xml:
```
<?xml version="1.0" encoding="UTF-8"?>

<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                          https://maven.apache.org/xsd/settings-1.0.0.xsd">
    <profiles>
        <profile>
            <id>environment</id>
            <activation>
                <activeByDefault>true</activeByDefault>
            </activation>
            <properties>
                <environment.type>prod</environment.type>
            </properties>
        </profile>
    </profiles>

</settings>
```