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
		RocketShip opollo = new RocketShip(g);
	}
}


class Rocket
{
	public Rocket(Graphics g)
	{
		g.setColor(Color.red);
		g.fillOval(200,100,400,450);
		g.setColor(Color.blue);
		g.fillRect(390,30,20,80);
	}	
}


class RocketFeatures
{
	
	public RocketFeatures(Graphics g)
	{
		drawFins(g);
		drawBody(g);
		drawMouth(g);
	}	
	
	public void drawFins(Graphics g)
	{
		g.setColor(Color.black);
		g.fillOval(200,200,100,100);
		g.fillOval(500,200,100,100);
	}
	public void drawBody(Graphics g)
	{
		Polygon nose = new Polygon();
		nose.addPoint(350,340);
		nose.addPoint(450,340);
		nose.addPoint(400,270);
		g.fillPolygon(nose);
	}
	
	public void drawMouth(Graphics g)
	{
		Polygon mouth = new Polygon();
		mouth.addPoint(300,400);
		mouth.addPoint(200,350);
		mouth.addPoint(250,450);
		mouth.addPoint(400,500);
		mouth.addPoint(550,450);
		mouth.addPoint(600,350);
		mouth.addPoint(500,400);
		g.fillPolygon(mouth);
	}
}
class Rocketship extends Rocket
{
	private RocketFeatures rf;
	
	public Rocketship(Graphics g)
	{
		super(g);
		rf = new Face(g);
	}	
}
