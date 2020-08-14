# Assignment – 2 

The Assignment’s primary goal is to apply usability & design principles for creating the UI of the Web Application. The User Interface is created from the already drawn wireframes in the Assignment-1.

### Deployment Link: https://a2-romal-sehgal.herokuapp.com/ 
Created Web Pages For Assignment-2: 
	##  Page-1: Landing Page Link: "https://a2-romal-sehgal.herokuapp.com/" 
	##  Page-2: User Profile Page Link (Registration) Link: "https://a2-romal-sehgal.herokuapp.com/register" 
	##  Page-3: Post Advertisement Page  Link: "https://a2-romal-sehgal.herokuapp.com/postad"
	##  Page-4: About Us Page Link : "https://a2-romal-sehgal.herokuapp.com/about" 

* Date Created: 14 06 2020
* Last Modification Date: 15 06 2020

### Author

* Romal Sehgal (rm359099@dal.ca) 

### About Assignment-2 

	For this Assignment, a total of 4 pages were created including:

	(1) Home Page ( Landing Page) 

	    Accessing Page: This is main and entry point page of the application. 

	(2) Registration (User Profile)  

	    Accessing Page: Can be accessed by clicking on “Sign-Up” button in the Nav-Bar or through create Account link in the side-bar menu.

	(3) Post Advertisement Page (Unique Page)
	 
	    Accessing Page: Can be accessed by clicking on “Post-Ad” button in the Nav-Bar   or through the side-bar menu.  

	(4) About Us Page (Unique Page) 

	    Accessing Page: Can be accessed from the Side-bar menu or from the footer area.

### Prerequisites

	See the following section for detailed step-by-step instructions on how to install this software / libraries / plug-ins

### Installing

	(1) pip install flask

	(2) For installing the react-bootstrap library run: npm install react-bootstrap bootstrap

	(3) For installing the material-UI core and icons library run:
	    
	    1. npm install @material-ui/core 
	    
	    2. npm install @material-ui/icons

	(4) For installing the react router dom library run:

	       npm install react-router-dom 
       

# Justifications

	## Design Justifications 


	### Color Pallets

		Since, the primary goal of the Project is to assist international students in finding room, apartment or house. Keeping that aspect in mind, the application uses blue and Grey color 		        pallets as part of UI design process.

		The reason behind using Blue and Grey Color Pallets were:

		(1) Blue Pallet: 

		We want our users to trust in our service. Since, most of the users of our 	website would be international students. They may be initially hesitant about using our website for     			finding room or apartment. As a result, it becomes crucial for us to build the trust with the user for providing necessary services. That’s why we decided to use Blue color Pallet    			for our application which is a symbolism of Trust, Confidence, Depth and other factors.   
	  

		(2) Grey Pallet 

		Since, the application is mainly meant to provide professional services to uses. With that aspect in mind, website uses Grey color pallet for creating various components in the 		Website.That’s why, grey color pallet has been used for designing the application which is a symbolism of being formal, balanced and sophisticated. 



	### Typography 

		For Typography, Sans-Serif Font-Family is used throughout the application for designing headings, links, button text and other components.

		Under the Sans-Serif family, a total of three font types were used mainly: “Roboto”, “Helvetica" and "Arial. 	

		The reason behind using Sans-Serif font-family was because of its:
	 
		(1) Easier to read across multiple devices or screens. 

	      	(2) Symbolizes a feeling of being an approachable and affable source. 

	      	(3) Attracts the Users who are especially in the age of 20-40 years. 


      ### Frameworks & Use of Libraries  

		The front-end design of the application is developed using React, CSS, “Material UI”, “React-Bootstrap”. 

		Why React was chosen as the front-end framework ?
	 
		(1) The main reason behind using React was not only for taking advantage of re-usable components but also because of its minimalistic nature.

		(2) Being already familiar with JavaScript, it was easy to quickly adapt to 	the writing code in React JS.

      		Why Material UI & React-Bootstrap libraries were used ? 

	    	For developing various components of the website, “Material UI & React- Bootstrap” libraries were used. However, when creating these component, a customized CSS was written for each 			of them to stay in compliance of the wireframes designed for the application. Components including Sidebar, Navbar, Forms, and Footer Section make use of the 			    			libraries and the customized CSS for maintaining look and feel of the website.  



## Running the Project 

	(1) Inside "REACT-FRONTEND" run command: npm run build

	(2) Go to flask directory

	(3) Now run command: python app.py or python3 app.py  (if version of python is 3) 


## Deployment

	As soon as the commit is made to github repo, Heroku operation is triggered which fetches the code from repo and performs build and deployment task on Heroku cloud.
	Once the build and deployment is complete, the website is automatically refreshed with the updated content. This serves the purpose of Continuous integration and Continuous deployment.


## Built With

	This tutorial is built with React as the front-end framework, while the back-end is served on Flask framework.


## References


	### Ref No. 1
          
	(1) Author: React Bootstrap https://react-bootstrap.github.io/components/cards/ <Website>

	(2) Why it was used?: React bootstrap makes it easy to create Grid Layout by using Containers and creating Customized forms. 

	(3) Where it was used? File locations: "Navbar.jsx", "Register.jsx" and “PostAd.jsx”, “Footer.jsx”. 

	(4) How it was used?: For creating forms in the web application, react-boostrap “Forms” component was used from which Fields such as Radio buttons, Checkbox were created. 

	For creating the Grid Components in the application, react-boostrap’s “Container” Component was used which assisted in laying out the different areas by Rows and Columns. 

	### Ref. No. 2

	(1) Author: React Material UI https://material-ui.com/getting-started/usage/ 
	    <website>

	(2) Why it was used? Material UI components were used in the application to mainly Navigation Bar, App bar, customizing the Icon button and Typography in the application.  

	(3) Where it was used? File locations: “Navbar.jsx”, “Landing Page.jsx”, “PostAd.jsx”. 

	(4) How it was used? 

	With <AppBar> Component of the Material-UI library, the top navigation bar of the website was integrated into application in which, Material UI Components such as <Typography>, <Menu>, 	<IconButton> were added. Similarly, these components were used in other web pages as well. 


	### Ref. No. 3 

	(1) Author: Hemadri Dasari  https://stackoverflow.com/questions/54050784/react-bootstrap-form validation-need-one-function-per-field  
	    <website>

	(2) Why it was used? For performing validations in “User-Profile” Page (Registration). 

	(3) Where it was used? File location: “register.jsx”.

	(4) How it was used? The main idea of how to perform the validation is followed from this reference. Inside the file, it consists of two methods mainly: “handleFormFieldChange” and 		“handleSubmit” methods that handle primary validation logic. Based on the requirements, the code was written according to the project’s requirements by following the core idea of how 		validation is performed in the reference. 



	### Ref. No. 4 

	(1) Author: Telerik https://www.telerik.com/blogs/up-and-running-with-react-form-validation <website>

	(2) Why it was used? For performing validations in “User-Profile” Page. 

	(3) Where it was used? File location: “register.jsx” 

	(4) How it was used? Both references 3 and 4 provides the basic core idea of how validations should be used when working with “react-bootstrap” forms component. As mentioned in the Reference 		3, the primary validation logic is build inside the two methods as specified in the previous reference. 


	### Ref. No. 5


	(1) Author: Button Generator https://www.bestcssbuttongenerator.com/ 
	    <website>

	(2) Why it was used: For designing customized buttons for application including specifically for “Post Advertisement” buttons 

	(3) Where it was used: File location: “Navbar.css” and “PostAd.css” 

	(4) How it was used?: The website provides a tools for creating buttons, After the corresponding CSS for the button is created. It was then customized manually to meet the application 	   requirements and color pallete. 



##  Image Assets References

	### Image Asset Reference No. 1

	     (1) Author: bqlqn https://www.flaticon.com/free-icon/home_2948210?term=home&page=1&position=4 <website> 

	     (2) Where & Why it was Used? Used in “Navbar.jsx” file to display it as a temporary logo for the website.   


	### Image Asset Reference No. 2

	     (1) Author: Huddle https://huddle.today/halifax-unemployment-rate-continues-to-fall/ <website>

	     (2) Where & Why it was used? Used in “LandingPage.jsx” file to display dummy card image on Landing Page on the website. 

	### Image Asset Reference No. 3 

	     (1) Author: shermantravel https://www.shermanstravel.com/advice/luxury-guide-to-prince-edward-island <website> 

	     (2) Where & Why it was used? Used in “LandingPage.jsx” file to display dummy card image on Landing Page on the website. 

	### Image Asset Reference No. 4 


	     (1) Author: David McBee (Pexels)  https://www.pexels.com/photo/high-angle-shot-of-suburban-neighborhood-1546168/ <website> 

	     (2) Where & Why it was used? Used in “About.jsx” file to display the landing image on the “About Us” Page. .


	### Image Asset Reference No. 5 

	     (1) Author: Expect Best (Pexels) https://www.pexels.com/photo/apartment-architectural-design-architecture-building-323772/ 

	     (2) Where & Why it was used? Used in “LandingPage.jsx” to display the primary landing page image on entry point page of the website. 
	     
	
	### Image Asset Reference No. 6
	
	     (1) Author: Cool Backgrounds https://coolbackgrounds.io/ . 
	     
	     (2) Where & Why it was used? The website provides tools from which customized textures can be created. The customized background was u
	         used in "LandingPage.jsx", "PostAd.jsx", and "Register.jsx" Components to display the background image.




## Acknowledgments

* bqlqn
* Expect Best
* Material UI Documentation
* Traversy Media (YouTube Channel) 
* w3Schools
* Pexels.com 
* Telerik 
* React-bootstrap documentation
* CssButtonGenerators
* Flaticons.com
