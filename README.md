Added a readme file to check pollscm trigger
2nd time check


Task 3: Maven 

Maven Lifecycle Explanation
Clean Lifecycle

The Clean lifecycle is responsible for cleaning the project by deleting the target directory.

Phases:

pre-clean

clean

post-clean

Command:

mvn clean


Purpose:
Removes previous build artifacts.

Default Lifecycle

The Default lifecycle handles the build process.

Important Phases:

validate

compile

test

package

verify

install

deploy

Command examples:

mvn compile
mvn package