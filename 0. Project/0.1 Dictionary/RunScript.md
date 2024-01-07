Run Script command
```bash 
cd /root/
chmod +x runDictionary.sh
./runDictionary.sh
```
Create Run Script 
#Step1 Create runDictionary.sh
```
cd /root/
touch runDictionary.sh
nano ./runDictionary.sh
```
#Step2 Copy and paste below script to the screen 
#Step2_1 Ctrl+O to save that file then Ctrl+ X to exit 
```bash
pm2 delete eureka apigateway authentication history search

cd /root/dictionary/eureka/
mvn clean package
cd /root/dictionary/apigateway/
mvn clean package
cd /root/dictionary/authentication/
mvn clean package
cd /root/dictionary/history/
mvn clean package
cd /root/dictionary/search/
mvn clean package

cd /root/dictionary/
pm2 start "java -jar eureka/target/eureka-0.0.1-SNAPSHOT.jar" --name "eureka"
pm2 start "java -jar apigateway/target/apigateway-0.0.1-SNAPSHOT.jar" --name "apigateway"
pm2 start "java -jar authentication/target/authentication-0.0.1-SNAPSHOT.jar" --name "authentication"
pm2 start "java -jar history/target/history-0.0.1-SNAPSHOT.jar" --name "history"
pm2 start "java -jar search/target/search-0.0.1-SNAPSHOT.jar" --name "search"
```
### Delete PM2 With AppId
```bash
pm2 delete eureka apigateway authentication history search
```
### Start HTTH
```bash
pm2 start "java -jar target/HTTHbyT-1.0-jar-with-dependencies.jar" --name htth
```
### Switch Java version
```bash
sudo update-alternatives --config java
```