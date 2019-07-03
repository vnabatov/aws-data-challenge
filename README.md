# aws-rekognition-with-node-js + jhuckaby/webcamjs

**0** Clone this repo 

**1** Make AWS account

**2** Create a group with access to Rekognition in AWS IAM

**3** Add user to a new group in AWS IAM

**4** Install aws console locally 

**5** Confiure AWS cli

```
aws configure 
aws rekognition create-collection --collection-id <your collection name>
```

**6** Install node modules

```
npm i
```

**7** Configure node app to use your collection

In file **aws-config.js** on folder **/resource/config**, put the collectionName and region that you create your collection
```
module.exports.collectionName = "PUT YOUR COLLECTION NAME HERE";
module.exports.region = "PUT YOUR REGION COLLECTION HERE";
```
**8** And finally run command to start example

```
npm start 
```
The application running at port 3000

Demo with https://github.com/jhuckaby/webcamjs:
http://localhost:3000/demos/click-to-run.html

---

## Calling the methods 
Using Postman

* **POST /detect-face**
```
POST /detect-face HTTP/1.1
Host: localhost:3000
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

photo=<source with image base 64>
```

* **POST /index-new-face**
```
POST /index-new-face HTTP/1.1
Host: localhost:3000
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache
photo=<source with image base 64>&id_user=<id of user in your data base>
```

* **POST /delete-face**
```
POST /delete-face HTTP/1.1
Host: localhost:3000
Content-Type: application/x-www-form-urlencoded
Cache-Control: no-cache

face_id= <string with face id to delete>

```
***Put param photo whitout "image/png;base64,"***

## Authors

* **Wanderson Araujo** - [WanderAraujo](https://github.com/wanderaraujo)

## License

This project is licensed under the GNU License - see the [LICENSE.md](LICENSE.md) file for details
