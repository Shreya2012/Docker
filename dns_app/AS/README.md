# sample_socket_programming

Authorative Server

It is the authoritative server for US. It has two duties.
First is to handle the registration requests to pair hostnames to IP, second is to
be able to respond to DNS queries from clients.
i. Registration: Accept a UDP connection on port 53533 and register Type A
DNS record into the database. Hint: You need to store the value in
somewhere persistent, for example in a file so that you can later respond
to DNS queries.
ii. DNS Query: Respond to DNS Query on port 53533. Query should include:
(Name, Type). If the message conforms to this, server will return the IP
address in a DNS message of form: (Name, Value, Type, TTL), retrieved
from the file (note that AS can distinguish registration requests from dns
queries by simply looking at the fields provided). Here is a sample request
and response:
Request:
TYPE=A
NAME=fibonacci.com
Response:
TYPE=A
NAME=fibonacci.com
VALUE=IP_ADDRESS
TTL=10

- AS performs a registration requests as specified above.
- AS provides DNS record for a given query as specified above.