
package telephoneDirectory;


	//import static java.lang.System.exit;

	//import java.util.Scanner;

//public class Contact {

	import static java.lang.System.exit;
	import java.util.Scanner;

	class Contact
	{
	String firstname;
	String lastname;
	String phoneNumber;
	String email;
	String city;
	String address;
	String sex;

	public Contact(String fname,String lname,String phone,String city,String address,String email,String sex)
	{
	this.firstname=fname;
	this.lastname=lname;
	this.phoneNumber=phone;
	this.email=email;
	this.city=city;
	this.address=address;
	this.sex=sex;
	}
	public String getFirstName()
	{
	return this.firstname;
	}
	public String getPhoneNumber()
	{
	return this.phoneNumber;
	}
	public void setPhoneNumber(String phone)
	{
	this.phoneNumber=phone;
	}
	public String toString()
	{
	String s=this.firstname+" "+this.lastname+" "+this.phoneNumber+" "+this.email+" "+this.city+" "+this.address+"\n";
	return s;
	}
	}

	 class TelephoneDirectory
	{
	public static void main(String []args)
	{
	Scanner sc = new Scanner(System.in);
	System.out.print("Enter size of the directory : ");
	int size = sc.nextInt();
	Contact directory[] = new Contact[size];
	int totalNumbers=0;
	String fname,lname,phone,city,address,email,sex;
	while(true)
	{
	System.out.println("1.Add person details");
	System.out.println("2.Update a telephone number");
	System.out.println("3.Display the entire book");
	System.out.println("4.Search a telephone number");
	System.out.println("5.Exit the program");
	System.out.print("Enter your choice : ");
	int choice = sc.nextInt();
	switch(choice)
	{
	case 1:
	System.out.print("Enter first name : ");
	fname=sc.next();
	System.out.print("Enter last name : ");
	lname=sc.next();
	System.out.print("Enter phone number : ");
	phone=sc.next();
	System.out.print("Enter city name : ");
	city=sc.next();
	System.out.print("Enter address : ");
	address = sc.nextLine();
	sc.next();
	System.out.print("Enter email : ");
	email= sc.next();
	System.out.print("Enter sex : ");
	sex = sc.next();
	directory[totalNumbers]=new Contact(fname,lname,phone,city,address,email,sex);
	totalNumbers++;
	break;
	case 2:
	System.out.print("Enter first name : ");
	fname=sc.next();
	System.out.print("Enter phonenumber : ");
	phone = sc.next();
	for(int i=0;i<totalNumbers;i++)
	{
	if(directory[i].getFirstName().equalsIgnoreCase(fname))
	{
	directory[i].setPhoneNumber(phone);
	break;
	}
	}
	break;
	case 3:
	for(int i=0;i<totalNumbers;i++)
	System.out.println(directory[i]);
	break;
	case 4:
	System.out.print("Enter first name : ");
	fname=sc.next();
	for(int i=0;i<totalNumbers;i++)
	{
	if(directory[i].getFirstName().equalsIgnoreCase(fname))
	{
	System.out.println("Telephone number is : "+directory[i].getPhoneNumber());
	break;
	}
	}
	break;
	case 5:
	exit(0);

	}
	}

	}
	}


