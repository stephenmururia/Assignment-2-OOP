# Assignment-2-OOP

import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class PetDisplayApp extends JFrame {
    // Components
    private JRadioButton dogButton, catButton, birdButton, rabbitButton, pigButton;
    private ButtonGroup petGroup;
    private JLabel petLabel;

    public PetDisplayApp() {
        // Setting up the frame
        setTitle("Pet Display Application");
        setSize(400, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setLayout(new FlowLayout());

        // Create the radio buttons for different pets
        dogButton = new JRadioButton("Dog");
        catButton = new JRadioButton("Cat");
        birdButton = new JRadioButton("Bird");
        rabbitButton = new JRadioButton("Rabbit");
        pigButton = new JRadioButton("Pig");

        // Grouping the radio buttons so only one can be selected at a time
        petGroup = new ButtonGroup();
        petGroup.add(dogButton);
        petGroup.add(catButton);
        petGroup.add(birdButton);
        petGroup.add(rabbitButton);
petGroup.add(pigButton);

        // Create the label to display the pet type
        petLabel = new JLabel("Choose a pet to display");

        // Adding action listeners to the radio buttons
        dogButton.addActionListener(new PetActionListener());
        catButton.addActionListener(new PetActionListener());
        birdButton.addActionListener(new PetActionListener());
        rabbitButton.addActionListener(new PetActionListener());
        pigButton.addActionListener(new PetActionListener());

        // Add components to the frame
        add(birdButton);
        add(catButton);
        add(dogButton);
        add(rabbitButton);
        add(pigButton);
        add(petLabel);
    }

    // ActionListener for the radio buttons
    private class PetActionListener implements ActionListener {
        @Override
        public void actionPerformed(ActionEvent e) {
            if (dogButton.isSelected()) {
                petLabel.setText("You selected a Dog!");
            } else if (catButton.isSelected()) {
                petLabel.setText("You selected a Cat!");
            } else if (birdButton.isSelected()) {
                petLabel.setText("You selected a Bird!");
            } else if (rabbitButton.isSelected()) {petLabel.setText("You selected a Rabbit!");
            } else if (pigButton.isSelected()) {
                petLabel.setText("You selected a Pig!");
            }
        }
    }

    public static void main(String[] args) {
        // Create an instance of the application
        PetDisplayApp app = new PetDisplayApp();
        app.setVisible(true);
    }
}
```
