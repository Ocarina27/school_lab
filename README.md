// ***********************************************
// Program Identification
// Name: Caleb Owens
// Class: java
// Date: 2/23/16
// File Location: \\student\student$\17.caleb.owens\My Documents
// ***********************************************

// ***********************************************
// Program Abstract
// This program demonstrates both inheritance and composition.
// A rocketship is-a . A rocketship has-a porthole. 
// ***********************************************

// ***********************************************
// Program Variable Dictionary
// 
// ***********************************************

import java.awt.*;
import java.applet.*;


public class RocketShip extends Applet
{
	public void paint(Graphics g)
	{
		Rocket opollo = new Rocket(g);
	}
}


class Rocket
{
	public Rocket(Graphics g)
	{
		g.setColor(Color.red);
		g.fillOval(300,100,200,600);
	}	

   public void Features(Graphics g)
   {
      drawFins(g);
      drawBody(g);
   }
   
   public void drawFins(Graphics g)
   {
      Polygon fins = new Polygon();
		fins.addPoint(350,340);
		fins.addPoint(450,340);
		fins.addPoint(400,270);
		g.fillPolygon(fins);
   }
   
   public void drawBody(Graphics g)
   {
      g.fillOval(200,200,100,100);
   }

}
class RocketFeatures
{

}
class Rocketship extends Rocket
{
	private RocketFeatures rf;
	
	public Rocketship(Graphics g)
	{
		super(g);
		rf = new Rocket(g);
	}	
}
