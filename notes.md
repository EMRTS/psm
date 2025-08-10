- ran /init in claude code on the project
- it generated the CLAUDE.md file with a very good overview of the project
I gave it this prompt:
```
  this project is about 7 years old. please look through the java code and give a more thorough analysis of the
  code and structure of the project
```
and it updated the CLAUDE.md file with a more detailed analysis of the code and structure of the project

---

# Install SDKMAN!
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"

# List available Java versions
sdk list java

# Install specific Java versions
sdk install java 17.0.9-tem     # Temurin JDK 17
sdk install java 11.0.21-tem    # Temurin JDK 11
sdk install java 8.0.392-tem    # Temurin JDK 8

# Switch between versions
sdk use java 17.0.9-tem         # Use for current session
sdk default java 17.0.9-tem     # Set as default

# Check current version
sdk current java

---

192.200.104.250 wnx0018618 wnx0018618.emrts.us 192.200.104.250.static.gorillaservers.com

---

VERSION=42.7.7; PWORD=psm; ./bin/jboss-cli.sh --connect <<EOF
xa-data-source add \
--name=TaskServiceDS \
--jndi-name=java:/jdbc/TaskServiceDS \
--driver-name=postgresql-${VERSION}.jar \
--xa-datasource-class=org.postgresql.xa.PGXADataSource \
--valid-connection-checker-class-name=org.jboss.jca.adapters.jdbc.extensions.postgres.PostgreSQLValidConnectionChecker \
--exception-sorter-class-name=org.jboss.jca.adapters.jdbc.extensions.postgres.PostgreSQLExceptionSorter \
--enabled=true \
--use-ccm=true \
--background-validation=true \
--user-name=psm \
--password=${PWORD} \
--xa-datasource-properties=ServerName=localhost,PortNumber=5432,DatabaseName=psm
xa-data-source add \
--name=MitaDS \
--jndi-name=java:/jdbc/MitaDS \
--driver-name=postgresql-${VERSION}.jar \
--xa-datasource-class=org.postgresql.xa.PGXADataSource \
--valid-connection-checker-class-name=org.jboss.jca.adapters.jdbc.extensions.postgres.PostgreSQLValidConnectionChecker \
--exception-sorter-class-name=org.jboss.jca.adapters.jdbc.extensions.postgres.PostgreSQLExceptionSorter \
--enabled=true \
--use-ccm=true \
--background-validation=true \
--user-name=psm \
--password=${PWORD} \
--xa-datasource-properties=ServerName=localhost,PortNumber=5432,DatabaseName=psm
EOF


--

install process notes

- gradle build required update to the build.gradle file to use more recent version of node.

do to db:update

```bash
export _JAVA_OPTIONS="-Djavax.xml.accessExternalSchema=all -Djavax.xml.accessExternalDTD=all"
./gradlew db:update
```

---

make sure to run the db commands to get all the tables or else it will break the functionality

---

when creating a new application the links to add a new specialty and add license/certification do not do anything. there are no errors either that i could find on the front end or in the backend

---

BUG: "same as above" on personal details page under "contact info" pulls the first name but last name is "undefined" so if it was filled out "Thomas Le" when clicking "same as above" it says "Thomas undefined"
