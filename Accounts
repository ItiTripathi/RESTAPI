## Accounts - GET operation

## Accounts collection [/accounts]
Accounts endpoint allows you to view all the customers' account related details. Responses will be returned in JSON format only.

### Accounts
Accounts as a resource represents following information:

| Property | Type | As request | As response | Description |
| :-------------------- | :---------- | :-------------------- | :-------------------- | ------------------------------------------------------------ |
| contractAccountNumber | String | `Mandatory` | `Returned always` | It is required to get all the customer details.|
| accountStatus | String | `Mandatory` | `Returned always` | It identifies the customer account as active 'A', inactive 'I' and in-progress 'I'. |
| accountBalance | String | `Mandatory` | `Returned always` | It is the amount that the user has his BG account. |
| accountBalanceStatus | String | `Optional` | `Returned always` | It is the account balance status of the accout such as 'D' for in debit, 'C' for in credit and 'N' for zero balance or empty "" for IP account. |
| paymentMethod | String | `Mandatory` | `Returned always` | It is the payment method that the customer has chosen, like 'D' or 'C'. |
| contractAccountType | String | `Mandatory` | `Returned always` | It identifies whether the user has individual account "01" or a collective account "02" or CollativeAccount "03".|
| fuelType | String | `Mandatory` | `Returned always` | It identifies the customer energy account, '01' for Electricity, '02' for Gas and '03' for dual. |
| contractStatus | String | `Mandatory` | `Returned always` |  It identifies the status of the customers account such as active 'A', In-active 'I' or In-progress 'Registration in progress'.|
| contractStartDate | String | `Optional` | `Returned always` |  It is the start date of the contract in "MM/DD/YYYY" format.|
| contractPlannedEndDate | String | `Optional` | `Returned always` |  It is the end date of the contract in "MM/DD/YYYY" format.|
| siteAddress | Address | `Mandatory` | `Returned always` |  It is the customers' site address.|



####Address
| Name | Type | As request | As response | Description |
| :---------- | :------ | -------- |---------|------------------------------------ |
| CountryCode | String | `Mandatory`| `Returned always` | Valid country code applicable as GB. |
| RegionCode | String | `Optional` | `Returned always` |It is of type like DBY.|
| StreetPostalCode | String | `Mandatory` | `Returned always` |It is the postcode of rhe region.|
| CityName | String | `Optional` | `Returned always` |It is the city name like DERBY or Loughborough.|
| StreetName | String | `Optional` | `Returned always` |It is the street name like 'Bishops Drive'.|
| Street2 | String | `Optional` | `Returned always` |It is the street name like 'Great Central Road'.|
| Street3 | String | `Optional` | `Returned always` |It is the street name like 'Unit 1'.|
| Street4 | String | `Optional` | `Returned always` |It is the street name which will not always be present.|
| HouseID | String | `Optional` | `Returned always` |It is the house ID like '438'.|
| BuildingID | String | `Optional` | `Not Returned always` |It is the sites' building ID.|
| POBoxNumber | String | `Optional` | `Not Returned always` |It is the sites' PoBox number |
| POBoxPostCode | String | `Optional` | `Not Returned always` |It is the sites' POBox postcode.|


### Retrieve accounts [GET /accounts/{id}] - 'account details found'
+ Parameters

    + id:602057034 (String) - Contract account number
	
+ Request

    + Headers

            Authorization: Bearer {accesstoken}
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 200 (application/json)
 {
	"status": "SUCCESS",
	"data": {
		"accounts": [{
			"accountID": "602057034",
			"accountStatus": "A",
			"accountBalance": "2067.86 ",
			"accountBalanceStatus": "D",
			"paymentMethod": "D",
			"contractAccountType": "01",
			"fuelType": "02",
			"contractStatus": "A",
			"contractStartDate": "04/18/2014",
			"contractPlannedEndDate": "04/18/2018",
			"siteAddress": {
				"address": {
					"countryCode": "GB",
					"regionCode": "DBY",
					"streetPostalCode": "DE21 2DF",
					"cityName": "DERBY",
					"streetName": "Bishops Drive",
					"street2": "",
					"street3": "",
					"street4": "",
					"houseID": "378",
					"buildingID": "",
					"pOBoxNumber": "",
					"pOBoxPostCode": ""
				}
			}
		}]
	},
	"errors": {}
}

+ Request 'Contract Account Number does not exist.'

    + Headers

            Authorization: Bearer {accesstoken}
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 500 (application/json)

            {
                "status": "ERROR",
                "data": {},
                "errors": [
                    {
                        "code": "service",
                        "message": "error.contractAccountNumber.does.not.exist"
                    }
                ]
            }


+ Request 'Error from SAP'

    + Headers

            Authorization: Bearer {accesstoken}
            cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526

+ Response 500 (application/json)

            {
                "status": "ERROR",
                "data": {},
                "errors": [
                    {
                        "code": "service",
                        "message": "error.system.pi.operation.fail"
                    }
                ]
            }
