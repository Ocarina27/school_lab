






import javax.swing.*;
import images.*;
import java.io.*;

public class NegativeExample
{
	public static void main(String args[])
	{
		JFileChooser fc = new JFileChooser();
		fc.showOpenDialog(null);							//Prompt user to select a file
		File file = fc.getSelectedFile();					//Get the file selected by the user
		if (file == null)
			System.exit(0);									//Close if no file was selected
		APImage img = new APImage(file.getPath());	//Load the image
		APImage resizedImage = new APImage(img.getWidth() / 3, img.getHeight() / 3);

		int redAverage;
      		int greenAverage;
      		int blueAverage;
   
      		// The following nested loop processing selects a column and goes through 
      		// through each row vertically.  If you reverse the order of the loops, it will process
      		// each column value before moving to the next row.
      
      		for (int x = 1; x < img.getWidth() - 1; x+=3)			          //Loop through the columns
			{  
				for (int y = 1; y < img.getHeight() - 1; y+=3)		          //Loop down the rows 
				{
            		Pixel pCenter = img.getPixel(x, y);                       //select center pixel
            		Pixel pAbove = img.getPixel(x - 1, y);                    //
            		Pixel pAboveR = img.getPixel(x - 1, y + 1);               //all
            		Pixel pRight = img.getPixel(x, y + 1);                    //pixels
            		Pixel pBelowR = img.getPixel(x + 1, y + 1);               //that
            		Pixel pBelow = img.getPixel(x + 1, y);                    //are
            		Pixel pBelowL = img.getPixel(x + 1, y - 1);               //surrounding
            		Pixel pLeft = img.getPixel(x, y - 1);                     //center
            		Pixel pAboveL = img.getPixel(x - 1, y - 1); 			       //pixel
                                                                      //
         		redAverage = (pCenter.getRed() + pAbove.getRed() + pAboveR.getRed() + pRight.getRed() + pBelowR.getRed() + pBelow.getRed() + pBelowL.getRed() + pLeft.getRed() + pAboveL.getRed()) / 9;
			greenAverage = (pCenter.getGreen() + pAbove.getGreen() + pAboveR.getGreen() + pRight.getGreen() + pBelowR.getGreen() + pBelow.getGreen() + pBelowL.getGreen() + pLeft.getGreen() + pAboveL.getGreen()) / 9;
			blueAverage = (pCenter.getBlue() + pAbove.getBlue() + pAboveR.getBlue() + pRight.getBlue() + pBelowR.getBlue() + pBelow.getBlue() + pBelowL.getBlue() + pLeft.getBlue() + pAboveL.getBlue()) / 9;
			resizedImage.setPixel(x, y, new Pixel(redAverage, greenAverage, blueAverage));
			}
		}
		
		img.draw();								         //Draw the image
		resizedImage.draw();                      //Draw the resized image
	}
}
