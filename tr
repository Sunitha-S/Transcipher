import java.awt.*;
import java.applet.*;
import java.awt.event.*;
/**/
public class traspositionCipher extends Applet implements ActionListener
{
/**
	 * 
	 */
	private static final long serialVersionUID = 1L;
Button enc=new Button("Encrypt");
Button dec=new Button("Decrypt");
Button reset=new Button("Reset Text Fields");
Button copy=new Button("Copy");
TextField txt,res;
int count=0;
int i,j;
char [][] plaintext=new char[100][100];
String ciphertext="";
public void init()
{
     
	Label input=new Label("Inputed String\n",Label.LEFT);
	input.setBackground(Color.BLUE);
	txt=new TextField(100);
	res=new TextField(100);
	add(input);
	add(txt);
	add(enc);
	enc.setBackground(Color.white);
	add(dec);
	dec.setBackground(Color.white);
	add(reset);
	reset.setBackground(Color.white);
	add(copy);
	copy.setBackground(Color.white);
	setBackground(new Color(0X00,0X00,0Xff));
	enc.addActionListener(this);
	dec.addActionListener(this);
	reset.addActionListener(this);
	copy.addActionListener(this);
}
public void actionPerformed(ActionEvent e)
{
	String str=e.getActionCommand();
	String s=txt.getText();
	s=s.replaceAll("\\s+","");
	int length=s.length();
	int len=(int) Math.sqrt(length);
	int sqr=(int)len;
	int square=sqr*sqr;
	int col=length-square;
	if(str.equals("Copy"))
	{
		String copyString=res.getText();
		txt.setText(copyString);
		repaint();
		ciphertext="";
	}
	if(str.equals("Reset Text Fields"))
	{
		resetTextFields(this);
		repaint();
		ciphertext="";
	}
	if(str.equals("Encrypt"))
	{
		if(square!=length)
		{
			if(col<=sqr)
			{
				count=0;
				for(i=0;i<(sqr+1);i++)
				{
					for(j=0;j<sqr;j++)
					{
						if(count<length)
						{
							plaintext[j][i]=s.charAt(count);
							count++;
						}
						else
						{
							plaintext[j][i]='*';
						}
					}
				}
				for(i=0;i<sqr;i++)
				{
					for(j=0;j<sqr+1;j++)
					{
						ciphertext=ciphertext+plaintext[i][j];
					}
				}
				res.setText(ciphertext);
			}
			else if(col>sqr)
			{
					count=0;
					for(i=0;i<sqr+2;i++)
					{
						for(j=0;j<sqr;j++)
						{
							if(count<length)
							{
								plaintext[j][i]=s.charAt(count);
								count++;
							}
							else
							{
								plaintext[j][i]='*';
							}
								
						}
					}
					for(i=0;i<sqr;i++)
					{
						for(j=0;j<sqr+2;j++)
						{
							ciphertext=ciphertext+plaintext[i][j];
						}
					}	
					res.setText(ciphertext);
			}
			
		}
		else if(length==square)
		{
			squareMatrix(sqr,s);
		}
		repaint();
		
	}
	else if(str.equals("Decrypt"))
	{
		if(square != length)
		{
			if(col<=sqr)
			{
				count=0;
				for(i=0;i<sqr;i++)
				{
					for(j=0;j<sqr+1;j++)
					{
						if(count<length)
						{
							plaintext[i][j]=s.charAt(count);
							count++;
						}
						else
						{
							plaintext[i][j]=' ';
						}
					}
				}
				for(i=0;i<sqr+1;i++)
				{
					for(j=0;j<sqr;j++)
					{
						if(plaintext[j][i]=='*')
						break;
						ciphertext=ciphertext+plaintext[j][i];
						ciphertext.replaceAll("\\s+","");
					}
				}
				res.setText(ciphertext);
			}
			else if(col>sqr)
			{
				count=0;
				for(i=0;i<sqr;i++)
				{
					for(j=0;j<sqr+2;j++)
					{
						if(count<length)
						{
							plaintext[i][j]=s.charAt(count);
							count++;
						}
						else
						{
							plaintext[i][j]=' ';
						}
					}
				}
				for(i=0;i<sqr+2;i++)
				{
					for(j=0;j<sqr;j++)
					{
						if(plaintext[j][i]=='*')
						break;
						ciphertext=ciphertext+plaintext[j][i];
						ciphertext.replaceAll("\\s+","");
					}
				}
				res.setText(ciphertext);
			}
		}
		else if(length==square)
		{
			squareMatrix(sqr,s);
		}
		
		repaint();
		ciphertext="";
	}
	
}
public static void resetTextFields(Container c) {
	Component [] components = c.getComponents();
	for(int i=0;i<components.length;i++)
		if(components[i] instanceof Container)
			resetTextFields((Container)components[i]);
			else if(components[i] instanceof TextField) 
			((TextField) components[i]).setText("");
}

public void paint(Graphics g)
{
	g.setFont(new Font("Arial",Font.BOLD,16));
	g.setColor(Color.white);
	g.drawString("Result",20,150);
	g.drawString(res.getText(),6,170);
}
public void squareMatrix(int sqr, String s)
{
	count=0;
	for(i=0;i<sqr;i++)
	{
		for(j=0;j<sqr;j++)
		{
			plaintext[i][j]=s.charAt(count);
			count++;
		}
	}
	for(i=0;i<sqr;i++)
	{
		for(j=0;j<sqr;j++)
		{
			ciphertext=ciphertext+plaintext[j][i];
		}
	}
	res.setText(ciphertext);
}
}
