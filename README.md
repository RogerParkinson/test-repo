# test-repo

[ ![Codeship Status for RogerParkinson/test-repo](https://app.codeship.com/projects/196b1240-3e99-0135-ed23-36e701660dc1/status?branch=master)](https://app.codeship.com/projects/229543)

Codeship deploy script
git config user.name $gitusername
git config user.email $gitemail
git checkout production
wget https://s3-ap-southeast-2.amazonaws.com/test-hello-springboot/settings.xml
mvn -B --settings ./settings.xml release:clean release:prepare release:perform -Dusername=$gitusername -Dpassword=$gitpassword

plus we have a maven settings file in the project.
... it definitely needs the username and password
https://s3-ap-southeast-2.amazonaws.com/test-hello-springboot/settings.xml

wget https://s3-ap-southeast-2.amazonaws.com/test-hello-springboot/settings.xml
