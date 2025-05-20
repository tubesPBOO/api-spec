# api-spec
## Start endpoint
`/auth/login`
## Login Endpoint
### Body Request for login
```json
{
    "name":"usertesst1",
    "pass": "passwordtest1"
}
```
## Register Endpoint
`/api/customers/register`, `/api/tukang/register`
### Body Request for register customer
```json
{
  "name": "jeongyeon",
  "email": "jy@gmail.com",
  "password": "Securepassword1",
  "address": "earth",
  "phoneNumber": "666666666"
}
```
### Body Request for register tukang
```json
{
  "name": "Budi Santoso",
  "email": "budi.santoso@example.com",
  "password": "Securepassword1",
  "role": "ROLE_TUKANG",
  "availability": true,
  "phoneNumber": "081234567890",
  "totrating": 0.0,
  "ratingCount": 0
}
```
## Get Customer by name endpoint
`/api/customers/{name customer}`
## Get All Customer
`/api/customers`
### Body Response for Get Customer
```json
{
    "id": "68276bf67628a8616f23b359",
    "name": "Jeongyeon",
    "email": "jy@gmail.com",
    "password": "$2a$12$tlLPrfEIb9j3je5YxGubiuOsRntgfoU/dp6K//agVMOMwAVhoopRy", // for now its visible later it will be removed from the response
    "role": "ROLE_CUSTOMER",
    "address": "Bojongsoang",
    "phoneNumber": "08135628888",
    "orders": null,
    "username": "Jeongyeon",
    "authorities": [
        {
            "authority": "ROLE_CUSTOMER"
        }
    ],
    "enabled": true,
    "accountNonExpired": true,
    "credentialsNonExpired": true,
    "accountNonLocked": true
}
```
## Get Material average rating by name endpoint
`/api/materials/ratingavg/{name material}`
## Get All Material endpoint
`/api/materials`
### Body Response for Get All Material
```json
{
        "id": "682318a0d6e38d35c9b03262",
        "stock": 0,
        "ratingCount": 10,
        "name": "Semen Tiga Roda",
        "totrating": 45.0,
        "price": 10000.0
},
```
## Update Material price by name endpoint
`/api/materials/price/{material name}`
### Body Request for Update Material price
```json
{
	"price":10000
}
```
## Update Material stock by name endpoint
`/api/materials/price/{material name}`
### Body Request for Update Material stock
```json
{
	"stock" : 200
}
```
## Add Material Rating by name endpoint
`/api/materials/rating/{material name}`
### Body Request for Update Material stock
```json
{
	"totrating" : 4.5
}
```
## Add Material endpoint
`/api/admin/materials`
### Body Request for Add Material
```json
 {
    "name": "Kayu Merbau",
    "stock": 100,
    "price": 75000,
    "ratingCount": 0,
    "totrating": 0.0
}
```
## Add Order endpoint
`/api/customers/order`
## Body Request for Add Order
```json
{
  "id": 103,
  "name": "Order-103",
  "materials": [
    { "name": "Semen Tiga Roda" },
    { "name": "Batu Bata Merah" },
    { "name": "Pasir Hitam" }
  ],
  "tukangCount": 2
}

```
### Body Response for Add Order
```json
{
    "id": 103,
    "name": "Order-103",
    "price": 260500.0,
    "materials": [
        {
            "id": "682318a0d6e38d35c9b03262",
            "stock": 0,
            "ratingCount": 10,
            "name": "Semen Tiga Roda",
            "totrating": 45.0,
            "price": 10000.0
        },
        {
            "id": "6823261fd6e38d35c9b0326e", 
            "stock": 1000,
            "ratingCount": 0,
            "name": "Batu Bata Merah",
            "totrating": 0.0,
            "price": 500.0
        },
        {
            "id": "6823272ed6e38d35c9b03272",
            "stock": 50,
            "ratingCount": 1,
            "name": "Pasir Hitam",
            "totrating": 4.5,
            "price": 250000.0
        }
    ],
    "tukangs": [
        {
            "id": "6828f22c530db76d5be50a6d", // this will be removed later its for test only
            "name": "Sumatra",
            "email": "sumatra@example.com", // this will be removed later its for test only
            "password": "$2a$10$j8BoLaDzI1fOwjAt/RD50O2qGpZ1zpYN0PVkF8GklRqRCrz6lrdI6", // this will be removed later its for test only
            "role": "ROLE_TUKANG", // this will be removed later its for test only
            "availability": false, // this will be removed later its for test only
            "phoneNumber": "081234567890",
            "average": 0.0,
            "username": "Sumatra", // this will be removed later its for test only
            "authorities": [
                {
                    "authority": "ROLE_TUKANG"
                }
            ],
            "enabled": true,
            "accountNonExpired": true,
            "credentialsNonExpired": true,
            "accountNonLocked": true
        },
        {
            "id": "6828f35f530db76d5be50a6f", // this will be removed later its for test only
            "name": "Budi Santoso",
            "email": "budi.santoso@example.com", // this will be removed later its for test only
            "password": "$2a$10$TXc5Lf6k3hZQLaEkT2teLuLOFwVE3A1EGkYgUd/jVom19.NOFbj1y", // this will be removed later its for test only
            "role": "ROLE_TUKANG", // this will be removed later its for test only
            "availability": false, // this will be removed later its for test only
            "phoneNumber": "081234567890", 
            "average": 0.0,
            "username": "Budi Santoso", // this will be removed later its for test only
            "authorities": [ // this will be removed later its for test only
                { 
                    "authority": "ROLE_TUKANG" nly
                }
            ],
            "enabled": true,
            "accountNonExpired": true,
            "credentialsNonExpired": true,
            "accountNonLocked": true
        }
    ],
    "customer": null, // this will be removed later its for test only
    "tukangCount": 2
}
```


