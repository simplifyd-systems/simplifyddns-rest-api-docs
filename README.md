# API

## Requests

### **GET** - /v1/developer/constants/licenses

#### Description
This request gets all valid license types that can be applied to a customer. The license applied to a customer controls what features the customer gets.

#### CURL

```sh
curl -X GET "https://api2.dns.simplifyd.systems/v1/developer/constants/licenses"
```

### **GET** - /v1/developer/constants/customers/auth_types

#### Description
This request gets all supported authentication methods that can be applied to a customer. This controls how authentication is done when the customer attempts to log in. For example, if the RADIUS authentication method is applied to a customer, the RADIUS authenticator specified is used to authenticate the customer during login.

#### CURL

```sh
curl -X GET "https://api2.dns.simplifyd.systems/v1/developer/constants/customers/auth_types"
```

### **GET** - /v1/developer/customers

#### Description
This request gets all customers.

#### CURL

```sh
curl -X GET "https://api2.dns.simplifyd.systems/v1/developer/customers"
```

### **POST** - /v1/developer/customers

#### Description
This request creates a new customer using a RADIUS authenticator for the customer authentication during sign in.

#### CURL

```sh
curl -X POST "https://api2.dns.simplifyd.systems/v1/developer/customers" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

#### Header Parameters

- **Content-Type** should respect the following schema:

```
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

#### Body Parameters

- **body** should respect the following schema:

```
{
  "type": "string",
  "default": "{\"email\":\"user@customer.com\",\"admin_email\":\"admin@customer.com\",\"fname\":\"admin_fname\",\"lname\":\"admin_lname\",\"mobile\":\"0123456789\",\"admin_mobile\":\"9876543210\",\"customer\":\"unique_customer_ref\",\"company\":\"Simplifyd Systems\",\"ipaddr\":\"10.10.10.10/32\",\"is_protected\":true,\"auth_type\":\"RADIUS\",\"authenticator\":\"authenticator_id\",\"license\":\"PROTECT_SME\"}"
}
```

### **POST** - /v1/developer/customers

#### Description
This request creates a new customer using the local SimplifydDNS database.

#### CURL

```sh
curl -X POST "https://api2.dns.simplifyd.systems/v1/developer/customers" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

#### Header Parameters

- **Content-Type** should respect the following schema:

```
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

#### Body Parameters

- **body** should respect the following schema:

```
{
  "type": "string",
  "default": "{\"email\":\"user@customer.com\",\"admin_email\":\"admin@customer.com\",\"password\":\"password\",\"fname\":\"admin_fname\",\"lname\":\"admin_lname\",\"mobile\":\"0123456789\",\"admin_mobile\":\"9876543210\",\"customer\":\"unique_customer_ref\",\"company\":\"Simplifyd Systems\",\"ipaddr\":\"10.10.10.10/32\",\"is_protected\":true,\"auth_type\":\"local\",\"license\":\"PROTECT_SME\"}"
}
```

### **GET** - /v1/developer/customers/5fd385447fbf580fdd58af44

#### Description
This request gets a particular/single customer with the ID specified.

#### CURL

```sh
curl -X GET "https://api2.dns.simplifyd.systems/v1/developer/customers/5fd385447fbf580fdd58af44"
```

### **DELETE** - /v1/developer/customers/5fd385447fbf580fdd58af44

#### Description
This request deletes a particular/single customer with the ID specified.

#### CURL

```sh
curl -X DELETE "https://api2.dns.simplifyd.systems/v1/developer/customers/5fd385447fbf580fdd58af44"
```

### **PUT** - /v1/developer/customers/5fd385447fbf580fdd58af44

#### Description
This request updates a particular/single customer with the ID specified.

#### CURL

```sh
curl -X PUT "https://api2.dns.simplifyd.systems/v1/developer/customers/5fd385447fbf580fdd58af44" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

#### Header Parameters

- **Content-Type** should respect the following schema:

```
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

#### Body Parameters

- **body** should respect the following schema:

```
{
  "type": "string",
  "default": "{\"email\":\"user@customer.com\",\"mobile\":\"0123456789\",\"company\":\"Simplifyd Systems\",\"ipaddr\":\"10.10.10.10/32\",\"license\":\"PROTECT_BASIC\",\"id\":\"5fd385447fbf580fdd58af44\"}"
}
```

### **PATCH** - /v1/developer/customers/5fd385447fbf580fdd58af44/protect

#### Description
This request enables protection for a particular/single customer with the ID specified.

#### CURL

```sh
curl -X PATCH "https://api2.dns.simplifyd.systems/v1/developer/customers/5fd385447fbf580fdd58af44/protect"
```

### **PATCH** - /v1/developer/customers/5fd385447fbf580fdd58af44/unprotect

#### Description
This request disables protection for a particular/single customer with the ID specified.

#### CURL

```sh
curl -X PATCH "https://api2.dns.simplifyd.systems/v1/developer/customers/5fd385447fbf580fdd58af44/unprotect"
```

## References

