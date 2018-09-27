# java-assignment
import java.io.BufferedReader;
import java.io.FileReader;
import java.util.ArrayList;


public class Assignment{
	public static void main(String args[])
	{
		BufferedReader reader = null;
		ArrayList inputString = new ArrayList<String>();
		String obj1 = "A";
		String obj2 = "B";
		String effect = "C";
		int totalObj = 0;
		try{

			reader = new BufferedReader(new FileReader("ObjectInputStream.csv"));
			String data = reader.readLine();
			while((data =reader.readLine())!=null)
			{
				data = data.split(",")[1];
				if(data.equals(obj1))
				{
					if((data = reader.readLine())!=null&&data.equals(obj2))
					{
						totalObj++;
						
					}
				}
				inputString.add(data);
			}
			System.out.println(inputString);

		}
		catch(Exception e)
		{
			e.printStackTrace();
		}
	}
}


//Next thing 
import java.io.BufferedReader;
import java.io.FileReader;
import java.util.ArrayList;



public class Assignment2{
	public static void main(String args[])
	{
		BufferedReader reader = null;
		ArrayList inputString = new ArrayList<String>();
		ArrayList inputPattern = new ArrayList<String>();
		String obj1 = "A";
		String obj2 = "B";
		String effect = "C";
		int totalObj = 0;
		int success = 0;
		inputPattern.add(obj1);
		inputPattern.add(obj2);
		try{

			reader = new BufferedReader(new FileReader("ObjectInputStream.csv"));
			String data = reader.readLine();
			String data1,data2;
			int i = 0;
			while((data =reader.readLine())!=null)
			{
				i = 0;
				data = data.split(",")[1];
				if(data.equals(obj1))
					{
						System.out.println("A found");
						inputString.add(data);
						i = 1;
						data1 = reader.readLine();
						if(data1!=null&&data1.split(",")[1].equals(obj2))
						{
							inputString.add(data1.split(",")[1]);
							System.out.println("next letter is B");
							totalObj++;
							data2 = reader.readLine();
							if(data2!=null && data2.split(",")[1].equals(effect))
								{
									System.out.println("hello");
									System.out.println("next Letter is C - success case");
									inputString.add(data2.split(",")[1]);
									success++;
								}
						

						}
					}
				if(i!=1)
				inputString.add(data);
			}

			System.out.println(inputString+"\n"+totalObj+"\n"+success);

			System.out.println("Success rate "+ ((float)success/totalObj)*100);
		}
		catch(Exception e)
		{
			e.printStackTrace();
		}
	}
}


































