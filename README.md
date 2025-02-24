**Hostel Database System**  
An SQL-based database management system for hostel operations.  

---

### **Overview**
This system is designed to efficiently manage hostel-related data, including student details, staff records, and visitor logs. It serves as a structured repository for handling various hostel operations, ensuring easy access to relevant information.

### **Core Entities & Attributes**
1. **Hostel**  
   - **Attributes:** Hostel ID (Primary Key), Capacity, Name, Available Rooms, and Facilities.
   - **Facilities include:** Mess ID (Foreign Key), Sports, Newspaper.

2. **Skilled Employees**  
   - **Attributes:** Full Name, Employee ID (Primary Key), Gender, Salary, Age, Contact Details (Multi-valued), Email, Designation.
   - **Relationship:** Linked to the hostel entity through a management relation.

3. **Non-Skilled Employees**  
   - **Attributes:** Full Name, Employee ID (Primary Key), Gender, Salary/Wages, Age, Contact Details (Multi-valued), Contractor Name, Role.
   - **Relationship:** Associated with the hostel entity through maintenance assignments.

4. **Visitor Records**  
   - **Attributes:** Record ID (Primary Key), Check-in & Check-out Timestamps, Contact Information, Visitor Name, Visited Hostel ID.
   - **Relationship:** Linked to the hostel entity through a visitation record.

5. **Student Entry/Exit Logs**  
   - **Attributes:** Record ID (Primary Key), Check-in & Check-out Timestamps, Student Roll Number (Foreign Key).
   - **Relationship:** Connected to the student entity through monitoring records.

6. **Student Information**  
   - **Attributes:** Roll Number (Primary Key), Full Name, Date of Birth, Derived Age, Room Number, Contact Details, Email, Address.
   - **Relationship:** Assigned to a hostel in a many-to-one association.

7. **Internet Access**  
   - **Attributes:** (Hostel ID, Room Number) as Primary Key, IP Address.
   - **Relationship:** Associated with hostel facilities.

### **Mess System (Normalized)**
- **Mess Administration:**  
  - **Attributes:** Mess ID (Primary Key), Caterer Name, Representative.
- **Mess Menu:**  
  - **Attributes:** (Mess ID, Day, Time) as Primary Key, Menu Details.
- **Relationship:** Both sets are linked to the hostel entity via service relations.

### **Transactional Records**
1. **Skilled Employee Transactions**  
   - **Attributes:** ID (Primary Key), Attendance, Work Days, Assigned Hostel.
   - **Relationship:** Maintains updates with the skilled employee entity.

2. **Non-Skilled Employee Transactions**  
   - **Attributes:** ID (Primary Key), Attendance, Work Days, Assigned Hostel.
   - **Relationship:** Updates linked to the non-skilled employee entity.

3. **Student Transactions**  
   - **Attributes:** Roll Number (Primary Key), Attendance, Days in Hostel, Current Hostel.
   - **Relationship:** Updates associated with the student entity.

### **Composite Attributes Breakdown**
- **Full Name:** Includes First Name, Last Name.
- **Address Details:** Includes House Number, Street Number.
- **Pin Code Breakdown:** Includes City, State, Country, ZIP Code.

### **Stakeholders & Access Permissions**
This database supports various user roles to facilitate hostel administration. The primary stakeholders include:
- **Warden & Supervisors:** Maintain student and employee records.
- **Security Officers:** Monitor visitor check-ins and student movements.
- **Administrators:** Oversee student allotments, salary disbursements, and database modifications.
- **Inspection Authorities:** Can be granted access to audit hostel records upon request.

This system provides structured, efficient, and easily retrievable data for effective hostel management.

