#### <span style="color:blue">WEEK1-HTML:</span>

<hr/>
##### Exercise1.1:

1.When a user enters an URL in the browser, how does the browser fetch the desired result ? Explain this with the below in mind and Demonstrate this by drawing a diagram for the same.

<hr/>

Solution :

![Browser Request Server Response](https://i.ibb.co/3dbzm9C/tcpip.png)

**1. We type URL**
When we type any URL on the browser for example ([https://sachinkamat.vercel.app](https://sachinkamat.vercel.app/)) then the browser checks the cache for a DNS record to find the corresponding IP address of [https://sachinkamat.vercel.app](https://sachinkamat.vercel.app/).
</br>
**2. DNS record check corresponding IP**
DNS(Domain NBame System) is a database that maintain the name of the website(URL) and particular IP address it links to.
<em> **Note:** Every single URL on the internet has a unique IP address assigned to it. </em>
The IP address belongs to the computer which hosts the server of the website we are requesting to access.
For example : [https://sachinkamat.vercel.app](https://sachinkamat.vercel.app/) has a IP address 76.76.21.142
So, if you'd like , you can reach [https://sachinkamat.vercel.app](https://sachinkamat.vercel.app/) by typing http://76.76.21.142 on your browser.
<em> **Note:** DNS is a list of URLs and their IP addresses, like how phone book is a list of Names and their corresponding phone numbers.</em>
To Find the DNS records, the browser checks four caches

- First, it check the browser cache.
- Second, the browser checks the OS cache
- Third, it checks the router cache
- Forth, it checks the ISP cache.

**3 If the requested URL is not in the cache**
ISP's DNS server initate a DNS query to find the IP address of the server that hosts sachinkamat.vercel.app
The purpose of DNS query is to search multiple DNS servers on the internet until it finds the correct IP address for the website(URL).
<em>**Note:** This type of search called recursive search </em>
Now the domain name server ( vercel.app) will find the matching IP address for sachinkamat.vercel.app in the DNS record and return it to your browser.

**4 The browser inititate a TCP connection with the server**
Once the browser receives the correct IP address it will build a connection with the server that matches the IP address to transfer informations.
<em>**Note:** Browser use Internet Protocols to build such connection</em>

**5 The browser send an http request to webserver**
Once the TCP connection established, it is time to start transferring data.
The browser will send a GET request asking for sachinkamat.vercel.app webpage.
<em>**Note:** If we type credential or submitting form, this could be a POST request.
</em>

**6. The Server handle the request and sends back a response.**
The server contains a webserver(i.e Apache) that recieves the request from the browser and passes it to a request handler to read and generate a response.
<em>**Note:** Request handler is a program written in Asp.net, PHP, Ruby etc. </em>
Request handler reads the request, then it assemble a response in a particular format(JSON, XML, HTML).

**7 The server sends out an HTTPs response**
The server response contains the web page you requested as well as the status code, content-encoding, cache-control, cookies etc

**8. Finally the browser displays the HTML content(website)**
The browser displays the HTML content in phases

- first, HTML skeleton
- second, check the HTML tags and send out GET requests for addtional elements on web page, like css, js files etc
  <em>**Note:** These static file are cached by the browser, so it doesn't have to fetch them again the when next time you visit the page.</em>

Now finally you'll see the sachinkamat.vercel.app appearing on the browser
