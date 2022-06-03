---
description: Validate input json data and support typescript types inference
---

# Object Schema & Data Validation

TLDR; If you need for client side or simple validation on node, use `yup`, else for complex validation use `joi`.&#x20;

### Yup

* Focused on client side, could be used in node
* Supports multiple locales for messaging
* Modify validation error msg, to be objects
* Supports typescript type inference
* supports `ref` but not logical operators
*



### Joi

[Joi Documentation](https://joi.dev/)&#x20;

* Supports
  * **ref**: a field to be equal to other
  * **with**: a field must be together with other. `.with('username', 'birth_year')`
  * **xor**: only one of the field is allowed: `.xor('password', 'access_token')`
  * Supports other operators like: `or`, `and`, `oxor`, `nand`, etc.
* <mark style="color:orange;">Doesn't support typescript</mark> types inference for validated object

### Alternative Libraries&#x20;
