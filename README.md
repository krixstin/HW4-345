## REST Client

![image](https://user-images.githubusercontent.com/55266110/112777222-ac074980-900f-11eb-897a-10f6a2493ffb.png)

## REST Server
Link to my demonstration of working server: 

https://stevens.zoom.us/rec/share/ou6Gq4OuNbJ63EEWIeMrMYFhzpaTAipX-FwTe4cwQPHnIo1wYMNuILGeFBR3nTx8.RT5RBfiYK__lUDa2

#### 1. Run a server in /server
```
node index.js
```

#### 2. Check
```
curl http://localhost:3000/
```

#### 3. Post content to server
```
curl -d '{"coffee":1, "milk":1, "sugar":1,"chocolate":1}' -H "Content-Type: application/json" -X POST http://localhost:3000/share

(return)
          {"success":true,"link":"http://localhost:3000/pvqyqemfr0waff25"}
```

#### 4. Retrieve content using URL returned (ex: pvqyqemfr0waff25)
```
curl http://localhost:3000/pvqyqemfr0waff25

(return) 
        {"coffee":1,"milk":1,"sugar":1,"chocolate":1}
```

#### 5. Second retrieval will fail
```
curl http://localhost:3000/pvqyqemfr0waff25

(return)
       {"success":false,"error":404,"message":"Not Found"}
```

## Shell

### Setting up Git Token
```
setx GITHUBTOKEN xxx
```

### Getting all repos of authenicated user
**only works in gitbash (no ctrl+c/v allowed)**

```
curl --request GET -H "Authorization: token $GITHUBTOKEN" https://api.github.com/user/repos
```

![image](https://user-images.githubusercontent.com/55266110/112711097-2747ee80-8e9c-11eb-8da6-fd7cfe672e8c.png)

```
node index.js
```

![image](https://user-images.githubusercontent.com/55266110/112711180-cc62c700-8e9c-11eb-92dd-5e194dd159df.png)


### List Branches

```
curl -H "Accept: application/vnd.github.v3+json" https://api.github.com/repos/krixstin/CS555/branches
```

![image](https://user-images.githubusercontent.com/55266110/112711450-dc7ba600-8e9e-11eb-9937-c5e2ee54a687.png)
