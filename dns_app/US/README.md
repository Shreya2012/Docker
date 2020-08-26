# sample_socket_programming

User Server

It a simple HTTP web server (e.g Flask), running in port 8080.
It accepts a GET HTTP requests in path “/fibonacci?hostname=fibonacci.com&fs_port=K&number=X&as_ip=Y&as_port=Z”.
The path accepts five parameters: hostname and fs_port which contains the hostname and port number of the server which will be queried to get a response for Fibonacci number for a given sequence number X. 
And as_ip, as_port which are the IP address and port number of the Authoritative Server (AS). 
If any of the parameters are missing, server should return HTTP code 400 indicating the bad request. 
If the request is successful it should return HTTP code 200 with the Fibonacci number for the sequence number X. 
The only problem is that US does not know the IP address of the given hostname and therefore need to query its Authoritative DNS server to learn about it.

