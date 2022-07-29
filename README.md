# Load Balancer
Very simples HTTP/TCP Load Balancer.
Implemented in Python3, single thread, using OS selector.
The code contains 4 classes that implement different strategies to select the next back-end server:

1. **N to 1:** all the requests are routed to a single server
2. **Round Robin:** the requests are routed to all servers in sequence
3. **Least Connections:** the request is routed to the server with fewer processed connections
4. **Least Response Time:** the request is routed to the server with less average execution time

## Course
This project was developed under the Distributed Computing course of [University of Aveiro](https://www.ua.pt/).

## Installation
* Clone the repository:
```console
$ git clone https://github.com/leo-dsf/Load_Balancer
```
* Install requirements:
```console
$ python3 -m venv venv
$ source venv/bin/activate
$ pip3 install -r requirements.txt
```

## How To Run
* Run Bash Script:
```console
$ source venv/bin/activate
$ ./setup.sh
```
* In another terminal:
```console
$ curl -s http://localhost:8080/10
```
* Or use a browser to open:
```console
http://localhost:8080/10
```

## How to access the load balancer
Go to a browser and open this [link](http://localhost:8080/100).
The number after the URL specifies the precision of the computation.

## How to Stress Test
* Run Stress Test:
```console
$ ./stress_test.sh
```
* Alternative:
```console
$ httperf --server=localhost --port=8080 --uri=/100 --num-conns=100 --rate=5
```

## Author
* **Leonardo Flórido** - [leo-dsf](https://github.com/leo-dsf)

## License
This project is licensed under the [MIT License](LICENSE).