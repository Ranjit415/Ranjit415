import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class RegistrationForm extends JFrame implements ActionListener {
    // Components of the Form
    private Container container;
    private JLabel titleLabel, nameLabel, passwordLabel, emailLabel;
    private JTextField nameText, emailText;
    private JPasswordField passwordText;
    private JButton registerButton;

    public RegistrationForm() {
        setTitle("Registration Form");
        setBounds(300, 90, 400, 300);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setResizable(false);

        container = getContentPane();
        container.setLayout(null);

        titleLabel = new JLabel("Register");
        titleLabel.setFont(new Font("Arial", Font.BOLD, 24));
        titleLabel.setSize(200, 30);
        titleLabel.setLocation(130, 20);
        container.add(titleLabel);

        nameLabel = new JLabel("Username:");
        nameLabel.setFont(new Font("Arial", Font.PLAIN, 14));
        nameLabel.setSize(100, 20);
        nameLabel.setLocation(50, 70);
        container.add(nameLabel);

        nameText = new JTextField();
        nameText.setFont(new Font("Arial", Font.PLAIN, 14));
        nameText.setSize(200, 20);
        nameText.setLocation(150, 70);
        container.add(nameText);

        passwordLabel = new JLabel("Password:");
        passwordLabel.setFont(new Font("Arial", Font.PLAIN, 14));
        passwordLabel.setSize(100, 20);
        passwordLabel.setLocation(50, 110);
        container.add(passwordLabel);

        passwordText = new JPasswordField();
        passwordText.setFont(new Font("Arial", Font.PLAIN, 14));
        passwordText.setSize(200, 20);
        passwordText.setLocation(150, 110);
        container.add(passwordText);

        emailLabel = new JLabel("Email:");
        emailLabel.setFont(new Font("Arial", Font.PLAIN, 14));
        emailLabel.setSize(100, 20);
        emailLabel.setLocation(50, 150);
        container.add(emailLabel);

        emailText = new JTextField();
        emailText.setFont(new Font("Arial", Font.PLAIN, 14));
        emailText.setSize(200, 20);
        emailText.setLocation(150, 150);
        container.add(emailText);

        registerButton = new JButton("Register");
        registerButton.setFont(new Font("Arial", Font.PLAIN, 14));
        registerButton.setSize(120, 30);
        registerButton.setLocation(130, 200);
        registerButton.addActionListener(this);
        container.add(registerButton);

        setVisible(true);
    }

    // Handle register button click
    public void actionPerformed(ActionEvent e) {
        String name = nameText.getText();
        String password = new String(passwordText.getPassword());
        String email = emailText.getText();

        if (name.isEmpty() || password.isEmpty() || email.isEmpty()) {
            JOptionPane.showMessageDialog(this, "Please fill all fields!", "Error", JOptionPane.ERROR_MESSAGE);
        } else {
            JOptionPane.showMessageDialog(this, "Registration successful!\nWelcome, " + name + "!", "Success", JOptionPane.INFORMATION_MESSAGE);
        }
    }

    public static void main(String[] args) {
        new RegistrationForm();
    }
}