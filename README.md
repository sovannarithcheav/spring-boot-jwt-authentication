# spring-boot-jwt-authentication

### Login

```
curl --request GET \
  --url http://localhost:8080/login \
  --cookie JSESSIONID=5FA5EEA7DD75D076246B3CAF23E73615 \
  --data '{
	"username":"admin",
	"password":"password"
}'
```
After logging in succeed, then check the response header for token.

### Access data source using token

```
curl --request GET \
  --url http://localhost:8080/users \
  --header 'authorization: GG eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJhZG1pbiIsImV4cCI6MTU2Mzk2ODcyM30.9ziW-sZ6EPCmhK2iZqVGtcDzbN4ZpGwflywyM0WztIv6j4nP-Kjg4yFN1up1Ip_R2IkIJC8xoop8eg66a3f0kA' \
  --cookie JSESSIONID=5FA5EEA7DD75D076246B3CAF23E73615
```
response
```
{
  "users": [
    {
      "firstname": "Richard",
      "lastname": "Feynman"
    },
    {
      "firstname": "Marie",
      "lastname": "Curie"
    }
  ]
}
```