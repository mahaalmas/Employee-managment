# Employee-managment
For any company wants a mobile application that handle their employees’ data through a mobile phone. This app have two sides: admin and employee.

# Introduction


Welcome to the product vision document delineating the development of a comprehensive mobile application , designed to simplify the process of managing employee records within organizations. This report serves as a comprehensive guide to the application's development, documenting its design, implementation, evaluation, and the considerations that went into its creation. The application leverages modern technology to provide a user-friendly and efficient solution for employee management tasks, including adding, updating, deleting, and retrieving employee information.
This report will describe the objectives of the project, the challenges encountered while developing the project, and the action taken to overcome the challenges. The hosted project is available on a GitHub repository itself, and codebase integration is provided through a RESTful API for facilitating CRUD (Create, Read, Update, Delete) operations. The application is developed for Android devices and incorporates best practices in software engineering and user experience design.

To illustrate the capabilities of Employees managment  application, we have furnished a or visit link ( housing the project code, alongside a YouTube video () that provides a visual demonstration of the application's functionality. Throughout this document, we meticulously explore various dimensions of the Employees managment application, offering insights into its background, legal considerations, social and ethical implications, professional impact, interface design, system architecture, implementation strategies, testing methodologies, and adherence to usability heuristic principles. Each section is crafted to provide a holistic understanding of how Employees managment application meets expectations of Software Engineering subject ASSESSMENT 2.

# Background
Managing employee data is a critical aspect of organizational operations. However, many organizations still rely on outdated or manual processes that are prone to errors and inefficiencies. The Employee Management System was conceived as a solution to address these issues by providing a digital platform for managing employee records seamlessly. The application aims to enhance productivity and accuracy in HR and administrative tasks.
The target users of this application are HR personnel, administrators, and managers who need to keep track of employee information such as personal details, job roles, and performance data. By using a centralized system, organizations can ensure data consistency and streamline workflows. The application also adheres to modern data security standards to protect sensitive employee information.
## 2.1 Project Vision
For any company wants a mobile application that handle their employees’ data through a mobile phone. This app have two sides: admin and employee. 
The admin is responsible for managing employees’ data, while the employee side allows employees to view and edit their details. The app is supposed to push notifications to inform users (admins and employees) of specific information based on their preferences (e.g., when details get updated).
The admin gets notified when an employee requests a holiday. Employees get notified when their request is approved or declined. Both users need to log in to their account to perform the functionalities. Users should be able to turn notifications off. Users can manage preferences in their account. The design of the interfaces should consider different screen sizes for various mobile devices.
## 2.2 The admin side:
For administrators who need to enter their employees’ details, the RESTful API web service provides simple and robust access to the data store via the HTTP infrastructure. Admins also have the capacity to approve or decline employees’ holiday requests if they wish to.
Functional Requirements
As an administrator, add employees’ details.
As an administrator, check that the employees’ details have been uploaded.
As an administrator, edit employees’ details.
As an administrator, delete an employee's details.
The app also apply an automatic increment of 5% to the employee's salary when they complete one year.
## 2.3 The employee side:
Functional Requirements
As an employee, view my details.
As an employee, edit my details.
As an employee,  book/manage my annual leave/holiday (the allowance is 30 days per year).
# 3. Legal, Social, Ethical, and Professional (LSEP)
Legal, social, ethical, and professional considerations are essential components of software development, particularly when dealing with sensitive data such as employee records. During the development of the Employee Management System, we identified and addressed several key issues to ensure compliance with regulations and ethical standards.
Privacy: The application incorporates robust measures to protect the privacy of employee data. All sensitive information is stored securely, and data transmission between the app and the server is encrypted using secure protocols. Role-based access control ensures that only authorized users can access specific data or perform certain actions.
Ethics: Ethical considerations were paramount during the design of the application. We ensured that the app does not collect unnecessary data and that all features align with the principles of transparency and accountability. Employees are informed about how their data is used, and they have the right to request updates or deletions of their personal information.
Professionalism: The project adhered to professional software development practices, including thorough documentation, extensive testing, and user feedback integration. By following these practices, we ensured that the application meets the highest standards of quality and reliability.

# 4. Design
The design of the Employee Management System focuses on simplicity and usability. The application's interface is intuitive, allowing users to easily navigate and perform tasks. The design process involved creating wireframes and high-fidelity prototypes to visualize the layout and functionality of the app before development began.
Key design features include:
1. A login screen with user authentication.
2. An admin dashboard that provides access to employee management features.
3. A detailed employee profile page for viewing and updating employee information.
4. A search functionality for quickly finding specific employees.
5. A responsive design that ensures compatibility with various screen sizes.
The user interface was designed using Android's Material Design guidelines to ensure a consistent and modern look and feel. The design also emphasizes accessibility, with features such as large buttons, clear labels, and support for screen readers.
## 4.1 For Front End Implementation:
Mobile App Interface by Java language using Java Android Studio IDE: The user interacts with the Sea Moon app through a mobile interface, where they can browse tables, make reservations, and access other features.

## 4.2 Backend Implementation:
The backend architecture will be based on the Retrofit platform, which provides a comprehensive set of tools and services to handle various aspects of application development. This service provides various authentication methods, such as email/password.

 ## 4.3 API service design in the application

 import retrofit2.Call;
 import retrofit2.http.GET;
 import retrofit2.http.POST;
 import retrofit2.http.Body;

 public interface ApiService {
 @GET("/employees")
 Call<List<Employee>> getEmployees();

 @POST("/employees")
 Call<Employee> createEmployee(@Body Employee employee);
 }
 ## 5. Implementation
The Employee Management System was deployed using a front-end and a back-end combination of technologies. The front-end was programmed in Java with Android Studio and the back-end with a RESTful API. The library Retrofit was employed for API communication and facilitating smooth communication between the app and server.

Database operations are performed through SQLite on the server and through HTTP (GET, POST, PUT, and DELETE) requests for CRUD operations by the app. For example, the  API route returns a list of all employees, and the  route introduces a new employee in the database.

The app includes several key features: The app includes several key features:
1. Secure user authentication to prevent unauthorized access.
2. Access restriction and the role-based access control of limiting the usage to admin users.
3. Validation of user inputs to ensure data integrity.
4. Methods of error handling to deliver meaningful feedback to users when errors occur.
The implementation process involved regular code reviews and testing to identify and fix bugs. The source code is hosted on a GitHub repository for version control and collaboration.
# 6. Evaluation
The evaluation of the Employee Management System involved extensive testing and user feedback. We conducted several types of tests to ensure the functionality, usability, and performance of the application.
Testing included:
1. Unit Testing: Verifying the functionality of individual components, such as the login screen and API calls.
2. Integration Testing: Ensuring smooth communication between the front-end and back-end.
3. Performance Testing: Measuring the app's responsiveness and scalability under various conditions.
4. User Testing: Gathering feedback from HR personnel and administrators to identify areas for improvement.
The feedback from user testing was overwhelmingly positive. Users appreciated the app's simplicity and functionality, noting that it significantly improved their productivity. Suggestions for future enhancements included adding reporting features and integrating the app with third-party HR systems.
The evaluation of the Employee Management System involved extensive testing and user feedback. We conducted several types of tests to ensure the functionality, usability, and performance of the application.
An example of testing the API endpoints is shown below:

 @Test
 public void testGetEmployees() {
 ApiService apiService = ...; // Initialize the ApiService
 Response<List<Employee>> response = apiService.getEmployees().execute();
 assertNotNull(response.body());
 assertEquals(200, response.code());
 }

 
# 7. Summary
The Employee Management System is a comprehensive solution for managing employee records in organizations. It combines a user-friendly interface with powerful features to streamline HR and administrative tasks. The app adheres to legal, ethical, and professional standards, ensuring the privacy and security of employee data.
The project demonstrated the importance of collaboration, thorough testing, and user feedback in software development. Future improvements will focus on adding more advanced features, such as analytics and integration with other systems, to further enhance the app's value.
# 8. References
[1] Android Developers Documentation: https://developer.android.com/
[2] Retrofit Library Documentation: https://square.github.io/retrofit/
[3] Employee Management API Documentation (User-provided).





