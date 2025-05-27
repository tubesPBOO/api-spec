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
## getOrderDetails (Customer) endpoint
`api/customers/getOrdersDetail`
## Body Response
```json
[
    {
        "payId": 3060,
        "deliverId": 9123,
        "payMethod": "Not yet paid",
        "payDate": "2025-05-27T08:26:22.120+00:00",
        "deliveryAddress": "Brebes",
        "trackingNumber": "AD23547E",
        "status": "Pending",
        "deliveryStatus": "Not delivered",
        "customer": {
            "id": "682b7f2f8ff0c15c6bbcfec9", // this will be removed later its for test only
            "name": "momoo", 
            "email": "momoo@gmail.com", // this will be removed later its for test only
            "password": "$2a$10$iyeToJiTSzofR8xbOFtdO.Pa5TqFW0hBdERfufZ0WH7IEd33qWiV6", // this will be removed later its for test only
            "role": "ROLE_CUSTOMER", // this will be removed later its for test only
            "address": "Brebes",
            "phoneNumber": "08135628888",
            "orders": [
                {
                    "id": 101,
                    "name": "Order-101",
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
                    "tukangs": [], 
                    "customer": null, // this will be removed later its for test only
                    "tukangCount": 0 
                },
                {
                    "id": 102,
                    "name": "Order-101",
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
                            "id": "6828d80ef191bd3c86049e71",
                            "name": "Budi Tukang",
                            "email": "budi@example.com", // this will be removed later its for test only
                            "password": "$2a$10$QqcGsTB01WYhS8kycVvmy.qSgS6CrZsrOtErVhgY6NuJ4ttzgEpHC", // this will be removed later its for test only
                            "role": "ROLE_TUKANG", // this will be removed later its for test only
                            "availability": false, 
                            "phoneNumber": "081234567890",
                            "average": 0.0,
                            "username": "Budi Tukang",
                            "authorities": [
                                {
                                    "authority": "ROLE_TUKANG"
                                }
                            ],
                            "enabled": true,
                            "credentialsNonExpired": true,
                            "accountNonExpired": true,
                            "accountNonLocked": true
                        }
                    ],
                    "customer": null,
                    "tukangCount": 0
                },
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
                    "tukangs": [],
                    "customer": null,
                    "tukangCount": 3
                },
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
                            "id": "6828f22c530db76d5be50a6d",
                            "name": "Sumatra",
                            "email": "sumatra@example.com",
                            "password": "$2a$10$j8BoLaDzI1fOwjAt/RD50O2qGpZ1zpYN0PVkF8GklRqRCrz6lrdI6", // this will be removed later its for test only
                            "role": "ROLE_TUKANG", // this will be removed later its for test only
                            "availability": false,
                            "phoneNumber": "081234567890",
                            "average": 0.0,
                            "username": "Sumatra",
                            "authorities": [
                                {
                                    "authority": "ROLE_TUKANG"
                                }
                            ],
                            "enabled": true,
                            "credentialsNonExpired": true,
                            "accountNonExpired": true,
                            "accountNonLocked": true
                        },
                        {
                            "id": "6828f35f530db76d5be50a6f",
                            "name": "Budi Santoso",
                            "email": "budi.santoso@example.com",
                            "password": "$2a$10$TXc5Lf6k3hZQLaEkT2teLuLOFwVE3A1EGkYgUd/jVom19.NOFbj1y",
                            "role": "ROLE_TUKANG",
                            "availability": false,
                            "phoneNumber": "081234567890",
                            "average": 0.0,
                            "username": "Budi Santoso",
                            "authorities": [
                                {
                                    "authority": "ROLE_TUKANG"
                                }
                            ],
                            "enabled": true,
                            "credentialsNonExpired": true,
                            "accountNonExpired": true,
                            "accountNonLocked": true
                        }
                    ],
                    "customer": null,
                    "tukangCount": 2
                },
                {
                    "id": 1,
                    "name": "Order-1",
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
                            "id": "6828d80ef191bd3c86049e71",
                            "name": "Budi Tukang",
                            "email": "budi@example.com",
                            "password": "$2a$10$QqcGsTB01WYhS8kycVvmy.qSgS6CrZsrOtErVhgY6NuJ4ttzgEpHC",
                            "role": "ROLE_TUKANG",
                            "availability": false,
                            "phoneNumber": "081234567890",
                            "average": 0.0,
                            "username": "Budi Tukang",
                            "authorities": [
                                {
                                    "authority": "ROLE_TUKANG"
                                }
                            ],
                            "enabled": true,
                            "credentialsNonExpired": true,
                            "accountNonExpired": true,
                            "accountNonLocked": true
                        },
                        {
                            "id": "6828f0fd530db76d5be50a6b",
                            "name": "Jawa",
                            "email": "jawa@example.com",
                            "password": "$2a$10$v64kDCmliGHdj1mPfO11XO2IrgC8x4w.doTeM4tu3go8py0246XAa",
                            "role": "ROLE_TUKANG",
                            "availability": false,
                            "phoneNumber": "081234567890",
                            "average": 0.0,
                            "username": "Jawa",
                            "authorities": [
                                {
                                    "authority": "ROLE_TUKANG"
                                }
                            ],
                            "enabled": true,
                            "credentialsNonExpired": true,
                            "accountNonExpired": true,
                            "accountNonLocked": true
                        }
                    ],
                    "customer": null,
                    "tukangCount": 2
                }
            ],
            "username": "momoo",
            "authorities": [
                {
                    "authority": "ROLE_CUSTOMER"
                }
            ],
            "enabled": true,
            "credentialsNonExpired": true,
            "accountNonExpired": true,
            "accountNonLocked": true
        },
        "orderId": 1
    }
]
```
## getOrders (Tukang) endpoint
`/api/tukang/getOrders`
## Body Response
```json
[
    {
        "id": 1,
        "name": "Order-1",
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
                "id": "6828f22c530db76d5be50a6d",
                "name": "Sumatra",
                "email": "sumatra@example.com",
                "password": "$2a$10$j8BoLaDzI1fOwjAt/RD50O2qGpZ1zpYN0PVkF8GklRqRCrz6lrdI6",
                "role": "ROLE_TUKANG",
                "availability": false,
                "phoneNumber": "081234567890",
                "average": 0.0,
                "username": "Sumatra",
                "authorities": [
                    {
                        "authority": "ROLE_TUKANG"
                    }
                ],
                "enabled": true,
                "credentialsNonExpired": true,
                "accountNonExpired": true,
                "accountNonLocked": true
            },
            {
                "id": "68357f33dabf4e176a6fcdd1",
                "name": "Budi Santoso",
                "email": "budi.santoso@example.com",
                "password": "$2a$10$CFlRD.H/D4K8R6b2Yjvqx.66VxuUk.zkbxhA3Bl08J4xeOTq/JZhS", // this will be removed later its for test only
                "role": "ROLE_TUKANG", // this will be removed later its for test only
                "availability": false,
                "phoneNumber": "081234567890",
                "average": 0.0,
                "username": "Budi Santoso",
                "authorities": [
                    {
                        "authority": "ROLE_TUKANG"
                    }
                ],
                "enabled": true,
                "credentialsNonExpired": true,
                "accountNonExpired": true,
                "accountNonLocked": true
            }
        ],
        "customer": null,
        "tukangCount": 2
    }
]
```
