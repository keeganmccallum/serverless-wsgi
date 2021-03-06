# 1.3.0
## Features
* Load subdirectory packages by adding the subdirectory to the search path (i.e. setting the wsgi handler to something like `dir/api.app.handler`).

  Previously, the subdirectory was expected to be a package (i.e. containing `__init__.py`)

## Bugs
* Skip removing `.requirements` if `packRequirements: false`

  *Alex DeBrie*

* Supply wsgi.input as BytesIO on Python 3

  *Brett Higgins*


# 1.2.2
## Features
* Add default package includes for `.wsgi_app` and `.requirements`

## Bugs
* Fix requirement packaging on Mac OS with Python 3.6 (Anaconda)

  *Vitaly Davydov*


# 1.2.1
## Features
* Support base64 encoding of binary responses automatically based on MIME type

  *Andre de Cavaignac*

## Bugs
* Properly handle Python 3 bytestring response

  *Andre de Cavaignac*


# 1.2.0
## Features
* Python 3 support


# 1.1.1
## Features
* Pass Lambda context in the `context` property of the WSGI environment.

  *Lucas Costa*


# 1.1.0
## Features
* Support for multiple Set-Cookie headers (#11). *Thanks to Ben Bangert for creating an issue and providing an implementation.*

* Forward API Gateway authorizer information as API_GATEWAY_AUTHORIZER in the WSGI request environment (#7). *Thanks to Greg Zapp for reporting.*


# 1.0.4
## Features
* Optional requirement packaging: Skips requirement packaging if `custom.wsgi.packRequirements` is set to false

  *Lucas Costa*

* Adds support for packaging requirements when wsgi app is in a subdirectory (i.e. setting the wsgi handler to something like `dir/app.handler`).

  *Lucas Costa*

* Package WSGI handler and requirements on single-function deployment

  *Lucas Costa*


# 1.0.3
## Features
* Adds support for packaging handlers inside directories (i.e. setting the wsgi handler to something like `dir/app.handler`).

  *Lucas Costa*


# 1.0.2
## Features
* Added unit tests.

## Bugs
* Internal requirements file was not included when user requirements file was present.


# 1.0.1
## Features
* Enable using the requirements packaging functionality alone, without the WSGI handler. This is enabled by omitting the `custom.wsgi.app` setting from `serverless.yml`.
* Load provider and function environment variables when serving WSGI app locally.

## Bugs
* If no `requirements.txt` file is present and the WSGI handler is enabled, make sure to package werkzeug.
