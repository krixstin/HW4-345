# REST API

## Setting up Git Token
`setx GITHUBTOKEN xxx`

## Getting all repos of authenicated user
**only works in gitbash (no ctrl+c/v allowed)**

`curl --request GET -H "Authorization: token $GITHUBTOKEN" https://api.github.com/user/repos`

![image](https://user-images.githubusercontent.com/55266110/112711097-2747ee80-8e9c-11eb-8da6-fd7cfe672e8c.png)

![image](https://user-images.githubusercontent.com/55266110/112711102-2f079300-8e9c-11eb-9ba5-cc7c820fad24.png)

`node index.js`

![image](https://user-images.githubusercontent.com/55266110/112711180-cc62c700-8e9c-11eb-92dd-5e194dd159df.png)


## List Branches

shell

`curl -H "Accept: application/vnd.github.v3+json" https://api.github.com/repos/krixstin/CS555/branches`

![image](https://user-images.githubusercontent.com/55266110/112711450-dc7ba600-8e9e-11eb-9937-c5e2ee54a687.png)

## Create a repo 

Replace ACCESS_TOKEN with my token and NEW_REPO_NAME with my New Repository Name

`curl -H "Authorization: token ACCESS_TOKEN" --data '{"name":"NEW_REPO_NAME"}' https://api.github.com/user/repos`
-> `curl -H "Authorization: token 62db2d7c2e01a7d8dd78df49e74437afb6dc3a4b" --data '{"name":"created-by-api"}' https://api.github.com/user/repos`

`curl -X POST -H "Accept: application/vnd.github.v3+json" https://api.github.com/user/repos -d '{"name":"name"}'`

`curl -X POST -H "Accept: application/vnd.github.v3+json" https://api.github.com/user/repos -d '{"name":"created-by-api"}'`
`-X` 

#Replace ACCESS_TOKEN with Token and NEW_REPO_NAME with your New Repository Name in the command below:

`-H` allows you to set headers as part of your request.
`-d` data


`curl -u "userNameHere" https://api.github.com/user/repos -d > '{"name":"repoNameHere","private":true}'`
