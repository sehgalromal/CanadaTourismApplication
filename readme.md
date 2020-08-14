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

![alt text](https://github.com/sehgalromal/CanadaTourismApplication/blob/master/Projects-Assets-Screenshots/image7.jpg?raw=true)

The architecture above explains how the application works by communicating with many other services internally. The user can access either web application or the mobile application. The application load balancer handles all the incoming traffic to the application., this load balancer is provided by Elastic Container Service. The load balancer internally also has a auto scaling feature where based on the metric provided by us it creates new instances of docker and shifts the load to the appropriate service. All the docker are instantiated by Elastic Bean Stalk, the EBS hosts multi container docker based on the Docker Aws configuration provided. Each docker instance represents a single microservice running on it. The AWS Cognito is used for user authentication and management and the DynamoDB is used for data store. 


### Authentication powered by Amazon Cognito

![alt text](https://github.com/sehgalromal/CanadaTourismApplication/blob/master/Projects-Assets-Screenshots/image4.jpg?raw=true)

### Web Application 

We developed the web application using HTML5, CSS3, Javascript and Bootstrap. The web application contains responsive web pages for searching the landmark, Description of landmark, Booking page and final ticket receipt and PDF page.  

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
    










