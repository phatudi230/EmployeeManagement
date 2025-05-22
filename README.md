# EmployeeManagement
import java.util.*;
public class EmployeesManagement {
    
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String [] names = new String[5];
        String [] iDnum = new String[5];
        String [] positions = new String[5];
        double [] salaries = new double[5];
        String [] hireDate = new String[5];
        Employees empManagement = new Employees(names, iDnum, positions, salaries, hireDate);
        boolean flag = true;
        while (flag) {

            System.out.println("Welcome to the Employee Management System");
            System.out.println("Please select an option:");
            System.out.println("1. Add Employee Details");
            System.out.println("2. Display Employee Details");
            System.out.println("3. Calculate Total Salary");
            System.out.println("4. Find Employee by ID");
            System.out.println("5. Find Employee by Name");
            System.out.println("6. Find Employee by Position");
            System.out.println("7. Find Employee by Hire Date");
            System.out.println("8. Find Employee by Salary");
            System.out.println("9. find Highest Salary");
            System.out.println("10. remove Employee");
            System.out.println("11. Exit");
            int choice;
            choice = sc.nextInt();

        switch (choice) {
            case 1:
               
                System.out.println("Enter Employee Details:");
                System.out.print("Name: ");
                String name = sc.next();
                System.out.print("ID: ");
                String id = sc.next();
                System.out.print("Position: ");
                String position = sc.next();
                System.out.print("Salary: ");
                double salary = sc.nextDouble();
                System.out.print("Hire Date: ");
                String date = sc.next();
                empManagement.addEmployeeDetails(name, id, position, salary, date);
                break;
            case 2:
                empManagement.displayEmployeeDetails();
                break;
            case 3:
                System.out.println("Total Salary: " + empManagement.calculateTotalSalary());
                break;
            case 4:
                System.out.println("Enter Employee ID to find:");
                String searchId = sc.next();
                System.out.println(empManagement.findEmployeeByID(searchId));
                break;
            case 5:
                System.out.println("Enter Employee Name to find:");
                String searchName = sc.next();
                System.out.println(empManagement.findEmployeeByName(searchName));
                break;
            case 6:
                System.out.println("Enter Employee Position to find:");
                String searchPosition = sc.next();
                System.out.println(empManagement.findEmployeeByPosition(searchPosition));
                break;
            case 7:
                System.out.println("Enter Hire Date to find:");
                String searchDate = sc.next();
                System.out.println(empManagement.findEmployeeByHireDate(searchDate));
                break;
            case 8:
                System.out.println("Enter Salary to find:");
                double searchSalary = sc.nextDouble();
                System.out.println(empManagement.findEmployeeBySalary(searchSalary));
                break;
            case 9:
                System.out.println("Highest Salary: " + empManagement.findHighestSalary());
                break;
            case 10:
                System.out.println("Enter Employee ID to remove:");
                String removeId = sc.next();
                empManagement.removeEmployeeByID(removeId);
                break;
            case 11:
                System.out.println("Exiting...");
                flag = false;
                break;
            default:
                System.out.println("Invalid choice. Please try again.");
        }
    }


    }

}
