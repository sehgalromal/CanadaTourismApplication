# Canada Tourism Application 

The cloud5409_TourismApp is Web and Mobile application which helps tourist to search for location with ease and book a ticket to that location. The system is light weight and secure mobile and web client, developed using cloud computing conventions and methods and is hosted on Amazon Web Services.The application provides users to search popular tourist destinations that will result the information of provincial/national parks, major beaches and popular cities nearby. The application has a booking services for the users to reserve their seat on the tourist bus that will cover all the tourist points. 

The project is a thin application where all the back-end operations, validations and other computations (such as scaling/load balancing) is be performed on AWS cloud. The application communicates with the cloud via API calls to microservices.


* Date Created: 03 30 2020
* Last Modification Date: 08 13 2020

### Author

* Romal Sehgal 
* Hardik Dudhrejia 
* Darpan Patel 
* Vikash Salvi Manharlal 


### Architecture 

![alt text](https://github.com/sehgalromal/CanadaTourismApplication/blob/master/Projects-Assets-Screenshots/Architecture%26Flow-Diagrams/image7.jpg?raw=true)

The architecture above explains how the application works by communicating with many other services internally. The user can access either web application or the mobile application. The application load balancer handles all the incoming traffic to the application., this load balancer is provided by Elastic Container Service. The load balancer internally also has a auto scaling feature where based on the metric provided by us it creates new instances of docker and shifts the load to the appropriate service. All the docker are instantiated by Elastic Bean Stalk, the EBS hosts multi container docker based on the Docker Aws configuration provided. Each docker instance represents a single microservice running on it. The AWS Cognito is used for user authentication and management and the DynamoDB is used for data store. 


### Authentication powered by Amazon Cognito

![alt text](https://github.com/sehgalromal/CanadaTourismApplication/blob/master/Projects-Assets-Screenshots/Architecture%26Flow-Diagrams/image4.jpg?raw=true)

### Web Application 

    We developed the web application using HTML5, CSS3, Javascript and Bootstrap. The web application contains responsive web pages for searching the 		    	landmark, Description of landmark, Booking page and final ticket receipt and PDF page.  

   [Web Application Screenshots](https://github.com/sehgalromal/CanadaTourismApplication/tree/master/Projects-Assets-Screenshots/Web-Application-Screenshots)

    Web Pages:
    
    (1) Search/Home page 
    
	The homepage of the website is designed using HTML and jQuery. The styling of the contents in the homepage is done using bootstrap. The homepage consists 	  of a search bar on the top from where the user can search for different tourist locations. However, it also displays all the 40 tourist locations in the 	   form of a card view so that user can have a gist of all the places that are available on the website.
	
   
    (2) Login page 
    
        We have used AWS Cognito to provide login and user management capability to our application. We have used default login, sign-up and forgot password pages   	     for both android and web application. Since we are using Cognito we are able to achieve two-factor authentication and login management without writing   	      single piece of code, but once user have logged in we maintain user token which helps in user management throughout the application.   
   
    (3) Description Page
    
       After searching for a particular location, the user can now see a detailed view of that searched location. It gives the user a significant amount 
       of details of the searched location. After this the user can proceed to the ticket booking part. 
      
   
    (4) Booking Details Page 
    
	The booking details page provides a interface for users to enter details related to the travel. It takes in booking information using which it can book 	ticket for user. It validates the users by calling validation service and once validated it books tickets for the user. 

   
    (5) Tickets page 
    
        Once the payment is validated, the ticket is generated and shown to the user as below. The user can even download the ticket in the pdf form offline. 
	
### Mobile Application 
    
    The Cloud5409 Tourism Mobile Application follows a thin client architecture that does all the processing on the server side. The application is composed of      	 various independent modules that communicate with a specific microservice.The mobile application uses Volley library to communicate with the microservices. It     	is an HTTP library that performs basic networking operations including establishing connections and sending requests to and fro from the server.
    
   [Mobile Application Screenshots](https://github.com/sehgalromal/CanadaTourismApplication/tree/master/Projects-Assets-Screenshots/Android-Application-Screenshots)
 
    Android App Activities:
    
    (1) User Query Submission Activity:  
    
    	This is the starting point of the application where the user will search for a specific place or landmark by submitting a query. A get request is made 		using Volley and alongside with the submitted query as endpoint. The search microservice on receiving the request prepares the response corresponding to 	 the submitted query. The response is returned in the form of JSONArray which is then populated in the dropdown menu. When the user will clicks on a 		specific item from the dropdown, the application then redirects to Landmark Information activity. 
    
    (2) Landmark Information Activity:  
    
    	This activity will be responsible for communication with the description microservice that will return the response for a particular place or landmark as 	  submitted prior by the user during search.
	
    (3) User Authentication using AWS Cognito Cognito Mobile SDK:  
    
    	Before the integrating the AWS Cognito Service into the mobile application, user-pool was created to enable sign-in and sign-up services in the android. 	 After the user pool generation on AWS Cognito, the generated Cognito client ID, Cognito Client secret, Cognito Web domain can be used to create the 		instance of Auth with the userpool configuration and android app can be pointed to hosted UI pages of AWS Cognito. After UI pages are hosted, 			authentication handler is invoked which is responsible for validating the user on successful authentication, after user has entered their credentials on 	 sign-in page or have registered themselves if they are first-time user. After the successful authentication, a unique token is created associated with the 	    user. With the generated unique token, user could then proceed for booking ticket activity.  
	
### Microservices 

    We broke down the project into microservices to achieve a microservice architecture. Micorservice architecture helps the application to be loosely coupled,     	isolated, robust and scale easily when required. All the microservices are written using Python. We divided the application into following microservice: 
    
    
    (1.) Search service 
    
    	 The data for 40 tourist places in Canada is stored in the AWS DynamoDB. The search API is implemented in Python Flask. Whenever a user searches a 		 location, then the search API running on the Docker is called. This API returns all the details of the searched location for example, name of the place, 	   id, city and the detailed description of that place. 
    
    (2.) Description service
    
    	 The description service provides detaisl for all the tourist places. It fetces detail of a particular location and provides these details  to user 		 interface and mobile application. It communicates with dynamo database to get relevant details. 
    
    (3.) Validation service
    
    	 The validation service performs varios validation on fileds like card number, source location, destination location, user name, date of travel, card 		 expiry month, year and cvv number of the card. If the payment details is valid the booking is done for that user. 
    
    (4.) Booking service
    
    	 The booking service is used for booking users ticket. It talks with dynamo database to store relevant fields and these fields can then be used to  		 generate ticket which is done by the next service. 
    
    (5.) Ticket Generation service 
    
    	 After the payment made by the user is validated, the details of that particular user are stored in a different table in AWS DynamoDB. Ticket Generation 	  API then fetches the user’s booking details from this table and returns the JSON result to the client side. This JSON response is then used to generate 	   the UI of the ticket. This microservice is implemented in python Flask.  
	
    (6.) PDF Generation service 
    
    	 For ticket generation, we have created REST API as microservices in Spring Boot. Application has generalized template in PDF format which can be edited 	  in future as per the requirements without affecting the other part of the application. To fill the PDF form programmatically in the application, we used 	    iTextPdf library in Java. All business logic in a ticket generation service API is covered with unit test. Following is the image for PDF. 
	
    (7.) Location service:
    
 	 This API returns all the 40 tourist locations stored in the database as a JSON array. This is used to populate the card view of the all the tourist 		 places on the home page. 
	
    (8.) Encryption/Decryption
    
   	 All the communications performed between the client and cloud are secured. The encryption algorithm used in monoalphabetic cipher. Monoalphabetic cipher 	   is a substitution cipher which is based on a cipher key. The cipher alphabet for each alphabet in the plain text is fixed prior to the start of the 		 encryption process. For example, if encrypted alphabet for “A” is “M” then everywhere in the plain text “A” will be substituted by “M”. The security of 	  monoalphabetic cipher depends upon the secrecy of the key and hoe difficult a key is chosen.An advancement of monoalphabetic cipher is Polyalphabetic 	 cipher where the same alphabet is substituted by different alphabets at different places in the plain text. 
    
    
    
	










