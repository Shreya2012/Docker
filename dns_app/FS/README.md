# sample_socket_programming

Fibonacci Server (FS) 

Itis an HTTP web server, running in port 9090, that provides
the Fibonacci value for a given sequence number X. In order to achieve this
objective, FS performs the following:
1. Hostname Specification: FS accepts a HTTP PUT request at path “/register”
where the body contains the name and IP address of the server (FS) and IP
address of the Authoritative Server (AS). You can choose any name of your
choice, let’s say “fibonacci.com”. The body should contain a json object as
below. FS should parse the body and noted that hostname and IP and IP, port
of the AS and moved to step 2 for registration to authoritative server.
{
“hostname”: “fibonacci.com”,
“ip”: “172.18.0.2”,
“as_ip”: “10.9.10.2”,
“as_port”: “30001”
}
2. Registration to Authoritative Server Once the request is retrieved at path
“/register”, the hostname needs be registered with Authoritative server (AS)
via UDP on port 53533. Your DNS message should include (Name, Value,
Type, TTL) where the type in this case is “A” and TTL in seconds. Below is a
simplified DNS registration request (please follow the format as below --
without the dashes--, each line ends with a new line):
----
TYPE=A
NAME=fibonacci.com
VALUE=IP_ADDRESS
TTL=10
----
3. Once registration is successful, returns back a HTTP response with code 201.
4. Serve a path in “/fibonacci?number=X” which accepts HTTP GET request and
returns Fibonacci number for the sequence number X. Return 200 as a status
code if successful. If X is not an integer (for example a string) return 400
indicating the bad format.