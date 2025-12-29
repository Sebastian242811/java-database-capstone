Section 1: Architecture summary
-------------------------------------------------------
This Spring Boot application uses both MVC and REST controllers. Thymeleaf templates are used for the Admin and Doctor dashboards, while REST APIs serve all other modules. 
The application interacts with two databases—MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, 
which in turn delegates to the appropriate repositories. MySQL uses JPA entities while MongoDB uses document models.

Section 2: Numbered flow of data and control
-------------------------------------------------------
1. User accesses Dashboards, Appointment or other pages from the aplication.
2. The action is routed to the appropriate Thymeleaf or REST controller.
3. The controller calls the common service layer which applies the correspondig validation and business rules to the incoming data.
4. In case of error, validation or other type, the corresponding message will be returned.
5. Depending on the interface being use by the user in that moment the data could be routed to the MySQL or the MongoDB repositories.
6. The data would use JPA entities for relational data management with MySQL, and document-based models for data storage and retrieval in MongoDB.
7. The result of the transaction will be displayed in the interface layer depending on the initial interface used by the user.
