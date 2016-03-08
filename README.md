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


public class RocketShipLab extends Applet
{
	public void paint(Graphics g)
	{
		Rocket opollo = new Rocketship(g);
	}
}


class Rocket
{
	public Rocket(Graphics g)
	{
		drawBody(g);
	   drawFin1(g);
      drawFin2(g);
   }
   
   public void drawFin1(Graphics g)
   {
      Polygon fin1 = new Polygon();
      g.setColor(Color.blue);
		fin1.addPoint(225,620); //left up
		fin1.addPoint(225,720); //left down
		fin1.addPoint(350,600); //right down
		fin1.addPoint(350,475); //right up
		g.fillPolygon(fin1);
   }
   
   public void drawFin2(Graphics g)
   {
      Polygon fin2 = new Polygon();
      g.setColor(Color.blue);
		fin2.addPoint(575,620); //right up
		fin2.addPoint(575,720); //right down
		fin2.addPoint(450,600); //left down
		fin2.addPoint(450,475); //left up
		g.fillPolygon(fin2);
   }

   public void drawBody(Graphics g)
   {
      g.setColor(Color.red);
		g.fillOval(300,100,200,600);
	}

	
}

class Rocketship extends Rocket
{
	private Rocket r;
	
	public Rocketship(Graphics g)
	{
		super(g);
		r = new Rocket(g);
      
	}	
   
   public void drawPorthole(Graphics g)
   {
      g.setColor(Color.white);
      g.fillOval(350,300,100,100);
   }
   
   public void drawLadder(Graphics g)
   {
      g.drawRect(360,310,10,410);
      g.drawRect(360,310,10,410);
   }
}
