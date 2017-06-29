# test-repo

[ ![Codeship Status for RogerParkinson/test-repo](https://app.codeship.com/projects/f9707aa0-3ed7-0135-ed23-36e701660dc1/status?branch=master)](https://app.codeship.com/projects/229587)

Codeship deploy script
git config user.name $gitusername
git config user.email $gitemail
git checkout production
git checkout master
git merge production
wget https://s3-ap-southeast-2.amazonaws.com/test-hello-springboot/settings.xml
mvn -B --settings ./settings.xml release:clean release:prepare release:perform -Dusername=$gitusername -Dpassword=$gitpassword


Todo:

 * A release goes recursive. The commit of the new version causes the trigger of a new build
 * Review security on the S3
 * merge to production did not trigger. Huh?