import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.MalformedURLException;
import java.net.URL;
import java.net.URLConnection;
import java.net.UnknownHostException;

public class Main {

	public static void main(String[] args) throws IOException {
  
  //replace null with the URLs
  //make sure that each URL is separated by a new line (denoted by "\n")
		String deargodwhy = "null";

  //creates array with a URL per index
		String [] arrayOfStrings = deargodwhy.split("\n");

		for (int i = 0; i < arrayOfStrings.length; i++) {
			String imageUrl = arrayOfStrings[i];
      //saves images as jpg by the numerical order 
			String destinationFile = i + ".jpg";
			saveImage(imageUrl, destinationFile);
			System.out.println("Processing number:" + i + "\n");
		}
		
		System.out.println("PROCESSING COMPLETE");
		System.out.println("Successfully collected " + arrayOfStrings.length + "images");
	}

	public static void saveImage(String imageUrl, String destinationFile) throws MalformedURLException {
		URL url = new URL(imageUrl);

		try {
  //prevents connection from taking too long
			URLConnection c = url.openConnection();
			c.setConnectTimeout(4000);
			c.setReadTimeout(4000);

			InputStream is = url.openStream();


			OutputStream os = new FileOutputStream(destinationFile);

			byte[] b = new byte[2048];
			int length;

			while ((length = is.read(b)) != -1) {
				os.write(b, 0, length);
			}

			is.close();
			os.close();
      
      //Catch Errors
		} catch (UnknownHostException exception) {
			System.out.println("Unknown Host Exception" + "\n");
		} catch (FileNotFoundException e){
			System.out.println("File Not Found Exception" + "\n");
		} catch (IOException e){
			System.out.println("IO Exception" + "\n");
		} 
		
	}

}
