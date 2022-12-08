# java-mqtt-example
Q.1
Q.1
import java.io.File;

import java.io.FileWriter;

import java.io.IOException;

import java.util.Scanner;

public class FileCreation 

{

  public static void main(String[] args) 

  {

	  Scanner sc =new Scanner(System.in);

	  System.out.println("Enter Your Details ");

	  String name = sc.nextLine();

	  try 

	  {  

	        FileWriter fwrite = new FileWriter("D:FileOperationExampleFileOperationExample.txt");  

	        // writing the content into the FileOperationExample.txt file  

	        fwrite.write(name); 

	   

	        // Closing the stream  

	        fwrite.close();   

	        System.out.println("Content is successfully wrote to the file.");  

	  } 

	  catch (IOException e) 

	  {  

	        System.out.println("Unexpected error occurred");  

	        e.printStackTrace();  

	  }   

  }  

}



Q.2
Q.2
import java.io.File;

import java.io.FileNotFoundException;

import java.util.Scanner;

public class ReadingFile 

{

	public static void main(String[] args) 

	{  

        try 

        {    

            File f1 = new File("D:FileOperationExample.txt");    

            Scanner reader = new Scanner(f1);  

            while (reader.hasNextLine()) 

            {  

                String data = reader.nextLine();  

                System.out.println(data);  

            }  

            reader.close();  

        } 

        catch (FileNotFoundException exception) 

        {  

            System.out.println("Unexcpected error occurred!");  

            exception.printStackTrace();  

        }  

    }  

}



Q.3
Q.3
import java.io.File;

import java.io.FileOutputStream;

import java.util.Scanner;

public class AppendUserString 

{

public static void main(String[] args) 

{

try 

{

File f1 = new File("D:info.txt");

if(f1.exists()==false)

{

if(f1.createNewFile())

{

System.out.println("File created Successfully");

}

else

{

System.out.println("File creation failed");

System.exit(0);

}

}

Scanner sc = new Scanner(System.in);

System.out.println("Enter text to write into file : ");

String text = sc.nextLine();

FileOutputStream file = new FileOutputStream(f1,true);

file.write(text.getBytes());

file.close();

System.out.println("File saved ");

}

catch(Exception Ex)

{

  System.out.println("Exception : "+ Ex.toString());

}

}

}




Q.4
Q.4
import java.io.File;

import java.util.Date;

public class FileDetails 

{

	public static void main(String[] args) 

	{

		File file = new File("D:info.txt");  

        if (file.exists()) 

        {  

            // Getting file name  

            System.out.println("The name of the file is: " + file.getName());  

   

            //Getting last updated date and time

            long lastModified = file.lastModified();

            Date date = new Date(lastModified); 

            System.out.println("Last modified date & time :"+date);  

   

            // Checking whether the file is writable or not  

            System.out.println("Is file writeable: " + file.canWrite());    

   

            // Checking whether the file is readable or not  

            System.out.println("Is file readable: " + file.canRead());    

   

            // Getting the length of the file in bytes  

            System.out.println("The size of the file in bytes is: " + file.length());



            // Getting free space of the file   

            System.out.println("The absolute path of the file is: " + file.getFreeSpace());

    

            // Getting path of the file   

            System.out.println("The absolute path of the file is: " + file.getAbsolutePath());

        } 

        else 

        {  

            System.out.println(" The file does not exist ");  

        }  

	     

	}  

}  



Q.5
Q.5
import java.io.File;

public class RenameFile

{

	public static void main(String[]args)

	{

		File oldName = new File("D:info.txt");

		File newName = new File("D:names.txt");

		if(oldName.exists())

		{

			System.out.println(oldName.renameTo(newName));

		
		else

		{

			System.out.println("File doesn't exists");

		}

	}

}

