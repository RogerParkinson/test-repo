# test-repo

[ ![Codeship Status for RogerParkinson/test-repo](https://app.codeship.com/projects/196b1240-3e99-0135-ed23-36e701660dc1/status?branch=master)](https://app.codeship.com/projects/229543)

Codeship deploy script
git config user.name "RogerParkinson"
git config user.email "roger.parkinson35@gmail.com"
git checkout production
mvn -B --settings ./settings.xml release:clean release:prepare release:perform -Dusername=RogerParkinson -Dpassword=T2mu0Yam2FmQ

plus we have a maven settings file in the project.
