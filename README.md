import java.awt.*;
import java.awt.event.ItemEvent;
import java.awt.event.ItemListener;
import javax.swing.*;
class TrafficLight extends JFrame implements ItemListener{
    public JRadioButton r1,r2,r3;
    public JLabel l1,l2;
    public JPanel p1,p2;
    public ButtonGroup bg;
    public TrafficLight(){
        setLayout(new GridLayout(2,1));
        setSize(400,400);
        p1=new JPanel(new FlowLayout());
        p2=new JPanel(new FlowLayout());
        l1=new JLabel();
        Font f=new Font("Verdana",Font.BOLD,300);
        l1.setFont(f);
        add(l1);
        p1.add(l1);
        add(p1);
        l2=new JLabel("Select Lights");
        p2.add(l2);
        r1=new JRadioButton("Red");
        r1.setBackground(Color.red);
        p2.add(r1);
        r2=new JRadioButton("Yellow");
        r2.setBackground(Color.yellow);
        p2.add(r2);
        r3=new JRadioButton("Green");
        r3.setBackground(Color.green);
        p2.add(r3);
        add(p2);
        bg=new ButtonGroup();
        bg.add(r1);
        bg.add(r2);
        bg.add(r3);
        r1.addItemListener(this);
        r2.addItemListener(this);
        r3.addItemListener(this);
        setVisible(true);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }@Override
    public void itemStateChanged(ItemEvent e){
        if(r1.isSelected()){
            l1.setForeground(Color.RED);
            l1.setText("STOP");
        }else if(r2.isSelected()){
            l1.setForeground(Color.YELLOW);
            l1.setText("READY");
        }else{
            l1.setForeground(Color.GREEN);
            l1.setText("GO");
        }
    }
}
public class Lab7 {
    public static void main(String[] args) {
        TrafficLight t=new TrafficLight();
    }
}
