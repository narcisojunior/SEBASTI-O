# SEBASTI-O

//Código para a tela inicial do projeto São Sebastião

package Principal;



import java.awt.*;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.plaf.nimbus.NimbusLookAndFeel;
import java.awt.Font;
import java.awt.Color;
import javax.swing.JLabel;
import javax.swing.UIManager;
import javax.swing.JButton;
import javax.swing.UnsupportedLookAndFeelException;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import java.text.ParseException;
import javax.swing.ImageIcon;




@SuppressWarnings("serial")
public class TelaInicial extends JFrame {

	private JPanel contentPane;
	/**
	 * @author Miguel Wolfgrann
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
		
		        
			public void run() {
				try {
				  
					UIManager.setLookAndFeel(new NimbusLookAndFeel());
					TelaInicial frame = new TelaInicial();					
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	public TelaInicial() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 1177, 625);
		
		contentPane = new JPanel();
		contentPane.setForeground(new Color(51, 204, 51));
	
		contentPane.setBackground(UIManager.getColor("CheckBox.background"));
		contentPane.setToolTipText("");
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		JLabel lblNewLabel = new JLabel("Par\u00F3quia Evang\u00E9lica de Confiss\u00E3o Luterana em S\u00E3o Sebasti\u00E3o\r\n\r\n");
		lblNewLabel.setFont(new Font("Arial Black", Font.ITALIC, 17));
		lblNewLabel.setBounds(311, 47, 585, 28);
		contentPane.add(lblNewLabel);
	
		
	
		JLabel lblCadastros = new JLabel("MEMBROS");
		lblCadastros.setFont(new Font("Arial Black", Font.BOLD | Font.ITALIC, 14));
		lblCadastros.setBounds(460, 189, 131, 14);
		contentPane.add(lblCadastros);
		
		JButton btnMembros = new JButton("");
		btnMembros.setIcon(new ImageIcon(TelaInicial.class.getResource("/Fotos/membro.jpg")));
		btnMembros.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				telaCadastroMembro t;
				try {
					UIManager.setLookAndFeel(new NimbusLookAndFeel());
					t = new telaCadastroMembro();
					t.setLocationRelativeTo(null);
					t.setVisible(true);
				} catch (ParseException e) {
					
					e.printStackTrace();
				} catch (UnsupportedLookAndFeelException e) {
					
					e.printStackTrace();
				}
				
			}
		});
		btnMembros.setBounds(448, 252, 131, 120);
		contentPane.add(btnMembros);
		
		JButton btnFamilias = new JButton("");
		btnFamilias.setIcon(new ImageIcon(TelaInicial.class.getResource("/Fotos/Familia.jpg")));
		btnFamilias.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				try {
					new telaCadastroFamilia().setVisible(true);
				} catch (ParseException e1) {
					
					e1.printStackTrace();
				}
			}
		});
		btnFamilias.setBounds(610, 252, 131, 120);
		contentPane.add(btnFamilias);
		
		JButton btnSair = new JButton("SAIR");
		btnSair.setBackground(new Color(250, 128, 114));
		btnSair.setForeground(new Color(0, 0, 0));
		btnSair.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				
				System.exit(0);
			}

			
		});
		btnSair.setBounds(883, 519, 127, 42);
		contentPane.add(btnSair);
		
		JLabel lblFamlias = new JLabel("FAM\u00CDLIAS");
		lblFamlias.setFont(new Font("Arial Black", Font.BOLD | Font.ITALIC, 14));
		lblFamlias.setBounds(625, 189, 131, 14);
		contentPane.add(lblFamlias);
		
		
	
	}
}
