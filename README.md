EasyOkcash-PHP
===============

A simple class for making calls to Okcash's API using PHP.

Getting Started
---------------
1. Include easyokcash.php into your PHP script:

	`require_once('easyokcash.php');`
2. Initialize Okcash connection/object:

	`$okcash = new Okcash('username','password');`

	Optionally, you can specify a host, port. Default is HTTP on localhost port 6969.

	`$okcash = new Okcash('username','password','localhost','6969');`

	If you wish to make an SSL connection you can set an optional CA certificate or leave blank
	`$okcash->setSSL('/full/path/to/mycertificate.cert');`

3. Make calls to okcashd as methods for your object. Examples:

	`$okcash->getinfo();`
	`$okcash->getrawtransaction('0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098',1);`
	`$okcash->getblock('000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f');`

Additional Info
---------------
* When a call fails for any reason, it will return false and put the error message in $okcash->error

* The HTTP status code can be found in $okcash->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $okcash->response while the raw JSON is stored in $okcash->raw_response