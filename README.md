package radiobuttondemo;
        import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class RadioButtonDemo extends JFrame implements ActionListener {

    JRadioButton bird, cat, dog, rabbit, pig;
    JLabel imageLabel;

    public RadioButtonDemo() {

        setTitle("Animal Viewer");
        setSize(600, 450);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());

        bird = new JRadioButton("Bird");
        cat = new JRadioButton("Cat");
        dog = new JRadioButton("Dog");
        rabbit = new JRadioButton("Rabbit");
        pig = new JRadioButton("Pig");

        ButtonGroup group = new ButtonGroup();
        group.add(bird);
        group.add(cat);
        group.add(dog);
        group.add(rabbit);
        group.add(pig);

        bird.addActionListener(this);
        cat.addActionListener(this);
        dog.addActionListener(this);
        rabbit.addActionListener(this);
        pig.addActionListener(this);

        JPanel panel = new JPanel(new GridLayout(5,1));
        panel.add(bird);
        panel.add(cat);
        panel.add(dog);
        panel.add(rabbit);
        panel.add(pig);

        imageLabel = new JLabel();

        add(panel);
        add(imageLabel);

        setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {

        if (bird.isSelected()) {
            imageLabel.setIcon(new ImageIcon(getClass().getResource("/images/Bird.jpg")));
        } else if (cat.isSelected()) {
            imageLabel.setIcon(new ImageIcon(getClass().getResource("/images/Cat.jpg")));
        } else if (dog.isSelected()) {
            imageLabel.setIcon(new ImageIcon(getClass().getResource("/images/Dog.jpg")));
        } else if (rabbit.isSelected()) {
            imageLabel.setIcon(new ImageIcon(getClass().getResource("/images/Rabbit.jpg")));
        } else if (pig.isSelected()) {
            imageLabel.setIcon(new ImageIcon(getClass().getResource("/images/Pig.jpg")));
        }
    }

    public static void main(String[] args) {
        new RadioButtonDemo();
    }
}
