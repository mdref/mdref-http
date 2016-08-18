# http\Client Changelog

0. v2.3.0
	* Deprecated methods:
		* http\Client::enablePipelining()
		* http\Client::enableEvents()
	* Added methods:
		* http\Client::configure()
		* http\Client::getAvailableConfiguration()
		* http\Client::getAvailableOptions()
0. v2.6.0, v3.1.0
	* Added methods:
		* http\Client::setDebug()
	* Added constants:
		* http\Client::DEBUG_INFO
		* http\Client::DEBUG_IN
		* http\Client::DEBUG_OUT
		* http\Client::DEBUG_HEADER
		* http\Client::DEBUG_BODY
		* http\Client::DEBUG_SSL
