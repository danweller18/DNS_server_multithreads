This is the ReadMe file for my multithreaded client server project.



Directions:
 
	Run the Server.jar file first and then run the Client.jar file. Please be sure to include the text file with domain names, one directory outside of the where your jar files are located. 

What this project does:
 
	When you run Server.jar, it will run the NameServer class. NameServer will look for client requests and accept client requests sent on port 6052. Then it will create a thread using the WorkerServer class for each line of code the client sends to the server. Each thread will obtain the output from the client and get the ip address for each domain name sent to the WorkerServer. WorkerServer will print out the ip address and send it back to the client. The client file will start a thread pool, read in a list of domain names line by line, and start a thread for each domain name. Then WorkerClient will send the list line by line to the server and receive the output from the server.




Questions:

What did I learn?

I gained a greater understanding of how threads work in an operating system. I also found how easy it is to make a dns server that returns ip addresses to a client machine. At first glance I did not think the implementation would be this simple.



What troubles did I face implementing this project?

I had trouble getting telnet to work. Trying to install on a Windows Server 2012 was impossible even after trying 3 different ways. At first I had trouble using telnet. Once I understood the project better I was able to test telnet and it was useful to test the server. I could not figure out how to kill the threads in my thread pool after I am finished with them. The directions on little things seemed unclear to me until I asked a few times; such as: Should the server class ever stop it self? Should the server threads kill themselves automatically?



How do the different thread pool types affect my program?

newcachedthreadpool() will create a thread when you need it. The threads should automatically kill themselves.

newfixedthreadpool(2) will create a threads when you need it, but only up to the size you specify- for example 2. The threads will automatically kill themselves and only process for example two requests at a time. This would cause the program to be slower than newcachedthreadpool()



How could I improve this program?

This is not an improvement to using a thread pool, but would be an improvement to using threads. At first I thought we should create as many threads as there are lines in the text file. The way I thought of implementing this was to have the client count the number of lines in the text file and then send that number to the server using another port. Then you would set the for loop to run, incrementing every loop, and stopping once it reaches the same number as the number of lines from the text file. This would be a good way of implementing the program without using the thread pool. 
