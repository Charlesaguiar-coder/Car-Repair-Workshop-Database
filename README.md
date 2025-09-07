# 🛠️ Car Repair Workshop Database

## 📖 Project Description
This project represents a **database schema for a car repair workshop**. The system is designed to manage and track **work orders**, **vehicles**, **customers**, **mechanics**, and the services and parts used for repairs. It ensures proper coordination between customers, vehicles, and mechanical teams.

---

## 🗂️ Entities

### **Customer** 👤
- Stores customer information.
- Attributes: `idCustomer`, `Name`, `Address`, `Phone`, `Email`
- A customer can own **multiple vehicles**.

### **Vehicle** 🚗
- Represents a vehicle brought in for service.
- Attributes: `idVehicle`, `Brand`, `Model`, `Year`, `Plate`, `Customer_idCustomer`
- Each vehicle belongs to **one customer**.
- Each vehicle can have **multiple work orders**.

### **Work Order** 📝
- Represents a service order for a vehicle.
- Attributes: `idWork_order`, `Number`, `Issue_date`, `Value`, `Status`, `Due_date`, `Labor_cost`, `Parts_cost`, `Vehicle_idVehicle`
- Each work order is associated with **one vehicle**.
- A work order can involve **multiple services** and **multiple parts**.

### **Service** 🔧
- Represents labor services performed.
- Attributes: `idService`, `Description`, `Type`, `Reference_value`
- Services are linked to **work orders**.

### **Part** 🧩
- Represents spare parts used in repairs.
- Linked via `Work_order_service` and `Work_order_part` tables.

### **Mechanic** 👨‍🔧
- Represents individual mechanics.
- Attributes: `idMechanic`, `Name`, `Address`, `Specialty`, `ID_Number`
- Mechanics belong to **mechanical teams**.

### **Mechanical Team** 👥
- Represents teams of mechanics.
- Attributes: `idMechanical_Team`, `Team_Name`
- Teams can work on multiple **work orders**.

### **Authorization** ✅
- Represents customer approval for work order execution.
- Attributes: `idAuthorization`, `Customer_idCustomer`, `Work_order_idWork_order`, `AuthorizationDate`
- Each authorization links a **customer** to a **work order**.

---

## 🔗 Relationships

- **Customer → Vehicle**: 1:N  
- **Vehicle → Work Order**: 1:N  
- **Work Order → Service**: N:M (via `Work_order_service`)  
- **Work Order → Mechanical Team**: N:M (via `Work_order_mechanical_team`)  
- **Mechanical Team → Mechanic**: N:M (via `mechanical_team_mechanic`)  
- **Customer → Authorization → Work Order**: 1:N  

---

## 🛠️ Features
- Tracks customers and their vehicles.  
- Manages work orders with services and parts.  
- Assigns work orders to mechanical teams.  
- Records authorizations from customers.  
- Stores mechanic specialties and team compositions.  

---

## 📂 Usage
1. Import the **SQL script** into MySQL Workbench.  
2. Use the EER diagram to visualize relationships.  
3. Manage work orders, mechanics, services, and parts efficiently.

---

## 🚀 Future Improvements
- Add **payment and invoice management**.  
- Implement **service scheduling** and reminders.  
- Add **vehicle history tracking** for regular maintenance.

---

