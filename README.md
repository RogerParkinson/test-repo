# test-repo

[ ![Codeship Status for RogerParkinson/test-repo](https://app.codeship.com/projects/f9707aa0-3ed7-0135-ed23-36e701660dc1/status?branch=master)](https://app.codeship.com/projects/229587)

Codeship Setup Script

```
wget $settingsurl
sed -i -e 's/NEXUSURL/$nexusurl/g' settings.xml
sed -i -e 's/NEXUSPWD/$nexuspwd/g' settings.xml
mvn --settings ./settings.xml  clean deploy
```

This is triggered by any push to github. It results in a snapshot version posted to nexus, the version number is not changed.

Codeship deploy script

```
git config user.name $CI_COMMITTER_USERNAME
git config user.email $CI_COMMITTER_EMAIL
git checkout -b master
git pull origin master
git checkout production
git checkout master
git merge production
wget $settingsurl
sed -i -e 's/NEXUSURL/$nexusurl/g' settings.xml
sed -i -e 's/NEXUSPWD/$nexuspwd/g' settings.xml
mvn -B --settings ./settings.xml release:clean release:prepare release:perform -Dusername=$CI_COMMITTER_USERNAME -Dpassword=$gitpassword
```
A push or merge to branch `production` will trigger Codeship to run this script. It results in a release version number being generated and the resulting build posted to nexus in the release repository. The code that built the release is tagged with the release version number.

It does depend on the gitpassword environment variable set up in the Codeship project
 
