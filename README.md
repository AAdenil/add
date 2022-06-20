import java.awt.Checkbox;
import java.awt.Choice;
import java.awt.Color;
import java.awt.GridLayout;
import java.awt.TextArea;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.ItemEvent;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;import java.sql.Statement;
import javax.swing.BorderFactory;
import javax.swing.ButtonGroup;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JRadioButton;
import javax.swing.JTextField;
import javax.swing.border.TitledBorder;
public class GAS extends JFrame implements ActionListener {
private static final long serialVersionUID=1L;
//CRIANDO OBJEYO**jp**e**jp1**
private JPanel JP1=new JPanel();
private JPanel JP2=new JPanel();
private JPanel JP3=new JPanel();
private JPanel JRB=new JPanel();
private JPanel JP4=new JPanel();
//CRIANDO JRADIOUTTON
JRadioButton rmasc,rfem;
ButtonGroup Sexo;ButtonGroup Auto;
//criando a Guia Chice
Choice civil;
Choice uf;
Choice t1;
Choice t2;
Choice t3;
TextArea area;
String novalinha;
//CRIANDO**BOTÕES**
JButton butIncluir =new JButton("Incuir");
JButton butAlterar =new JButton("Alterar");
JButton butExcluir =new JButton("Excluir");
JButton butLimpar =new JButton("Limpar");
JButton butPesquisar =new JButton("Pesquisar");
//CRIANDO**LABEL'S**
JLabel labidcliente =new JLabel("Código:");
JLabel labendereco =new JLabel("Endereço:");
JLabel labcep =new JLabel("cep:");
JLabel labemail =new JLabel("E-mail:");
JLabel labrg =new JLabel("Rg:");
JLabel labbairro =new JLabel("Bairro:");
JLabel labcpf =new JLabel("CPF:");
JLabel labcidade =new JLabel("Cidade:");
JLabel labnome =new JLabel("Nome:");
JLabel labsexo =new JLabel("Sexo:");
JLabel labdados =new JLabel("Exibir Cadastro:");
JLabel labnum =new JLabel("N:");
JLabel labcomp =new JLabel("Complemento:");
JLabel labnasc =new JLabel("Nasc:");
JLabel labecivil =new JLabel("Estado Civil:");
JLabel labcnh =new JLabel("CNH:");
JLabel labplaca =new JLabel("Placa:");
JLabel labrenavan =new JLabel("Renavan:");
JLabel labuf =new JLabel("UF:");
JLabel labtel =new JLabel("Telefone:");
//CRIANDO**CAIXA DE TEXTO**
JTextField txidcliente =new JTextField();
JTextField txnasc =new JTextField();
JTextField txbarrio =new JTextField();
JTextField txendereco =new JTextField();
JTextField txnum =new JTextField();
JTextField txcomp =new JTextField();
JTextField txcidade =new JTextField();
JTextField txemail =new JTextField();
JTextField txcep =new JTextField();
JTextField txrg =new JTextField();JTextField txcpf =new JTextField();
JTextField txnome =new JTextField();
JTextField txcnh =new JTextField();
JTextField txplaca =new JTextField();
JTextField txrenavan =new JTextField();
JTextField txuf =new JTextField();
JTextField txtelefone =new JTextField();
JTextField txt1 =new JTextField();
JTextField txt2 =new JTextField();
JTextField txt3 =new JTextField();
//ABRINDO MÉTODO CONSTRUTOR
 public GAS(){

 area=new TextArea(5,30);
 area.setEditable(false);
 add(area,"South");
getContentPane().setLayout(null);
addWindowListener(new WindowAdapter(){
public void windowClosing(WindowEvent evt)
{
System.exit(0);
}
});
//Guia Choicevil=new Choice();
civil.addItem("Solteiro(a):");
civil.addItem("Casado(a):");
civil.addItem("Divorciado(a):");
civil.addItem("Viúvo(a):");
t1=new Choice();
t1.addItem("Residencia:");
t1.addItem("Comercial:");
t1.addItem("Celular:");
t1.addItem("Outro(s):");
t2=new Choice();
t2.addItem("Residencia:");
t2.addItem("Comercial:");
t2.addItem("Celuar:");
t2.addItem("Outro(s):");
t3=new Choice();
t3.addItem("Residencia:");
t3.addItem("Celular:");
t3.addItem("Outro(s):");
uf=new Choice();
uf.addItem("AC:");uf.addItem("AL:");
uf.addItem("AP:");
uf.addItem("AM:");
uf.addItem("BA:");
uf.addItem("CE:");
uf.addItem("DF:");
uf.addItem("ES:");
uf.addItem("GO:");
uf.addItem("MA:");
uf.addItem("MT:");
uf.addItem("MS:");
uf.addItem("MG:");
uf.addItem("PA:");
uf.addItem("PB:");
uf.addItem("PR:");
uf.addItem("PE:");
uf.addItem("PI:");
uf.addItem("RJ;");
uf.addItem("RN:");
uf.addItem("RS;");
uf.addItem("RO;");
uf.addItem("RR:");
uf.addItem("SC:");
uf.addItem("SP;");
uf.addItem("SE;");
uf.addItem("TO:");uf.addItem("AA:");
JP1.setLayout(null);
JP1.setBorder(new
javax.swing.border.EtchedBorder());
JP2.setLayout(null);
JP2.setBorder(new
javax.swing.border.EtchedBorder());
JP3.setLayout(null);
JP3.setBorder(new
javax.swing.border.EtchedBorder());
JP4.setLayout(null);
JP4.setBorder(new
javax.swing.border.EtchedBorder());
 TitledBorder tit=
 BorderFactory.createTitledBorder("Sexo");

 Sexo=new ButtonGroup();

 rmasc=new JRadioButton("Masc:,true");
 rmasc.setActionCommand("Masculino");
 rfem=new JRadioButton("Fem:,true"); rfem.setActionCommand("Feminino");

 //ADICIONANDO**LABEL'S**AO PAINEL JP1

 JP1.add(labidcliente);
 JP1.add(labnome);
 JP1.add(labcpf);
 JP1.add(labrg);
 JP1.add(labnasc);
 JP1.add(labecivil);

 //ADICIONANDO**LABEL'S**AO PANEL JP2

 JP2.add(labendereco);
 JP2.add(labbairro);
 JP2.add(labcomp);
 JP2.add(labnum);
 JP2.add(labcep);
 JP2.add(labbairro);
 JP2.add(labcidade);
 JP2.add(labemail);
 JP2.add(labuf);
 JP2.add(labtel);

 //ADICIONAR**LABAL'S AO PAINEL JP3JP3.add(labdados);

 //ADICIONAR**LABAL'S AO PAINEL JP4

 JP4.add(labcnh);
 JP4.add(labplaca);
 JP4.add(labrenavan);

 //ADICIONANDO**BOTÕES**AO PAINEL P3

 JP3.add(butIncluir);
 JP3.add(butAlterar);
 JP3.add(butExcluir);
 JP3.add(butLimpar);
 JP3.add(butPesquisar);

 //ADICIONANDO**CAIXA DE TEXTO** AO PAINEL JP1

 JP1.add(txidcliente);
 JP1.add(txnome);
 JP1.add(txrg);
 JP1.add(txcpf);
 JP1.add(txnasc);
 JP1.add(civil); //ADICIONANDO**CAIXA DE TEXTO**AO PAINEL JP1

 JP2.add(txendereco);

 JP2.add(txcomp);
 JP2.add(txnum);
 JP2.add(txemail);
 JP2.add(txcep);
 JP2.add(txcidade);
 JP2.add(uf);

 JP2.add(t1);
 JP2.add(t2);
 JP2.add(t3);
 JP2.add(txt1);
 JP2.add(txt2);
 JP2.add(txt3);

 //ADICIONANDO**CAIXA DE TEXTO**AO PAINEL JP3

 JP3.add(area);

 //ADICIONANDO**CAIXA DE TEXTO **AO PAINEL JP4

 JP4.add(txplaca);JP4.add(txcnh);
 JP4.add(txrenavan);

 Sexo.add(rmasc);
 Sexo.add(rfem);
 JRB.setBorder(tit);
 JRB.add(rmasc);
 JRB.add(rfem);

 rfem.setBounds(95,5,60,20);
 rmasc.setBounds(10,5,60,20);
 JRB.setBounds(550,12,145,88);

 getContentPane().add(JRB);

 //ADICIONANDO**AçÃO**AOS BOTÕES

 butIncluir.addActionListener(this);
 butAlterar.addActionListener(this);
 butExcluir.addActionListener(this);
 butLimpar.addActionListener(this);
 butPesquisar.addActionListener(this);

 txnome.setBounds(10,20,400,25);
 txidcliente.setBounds(420,20,111,25);
 txcpf.setBounds(10,63,120,25);txrg.setBounds(150,63,120,25);
 txnasc.setBounds(290,63,120,25);
 civil.setBounds(420,65,111,05);
 txendereco.setBounds(10,20,260,25);
 txcep.setBounds(510,20,170,25);

 txnum.setBounds(290,20,40,25);
 txcomp.setBounds(345,2,160,25);
 txcidade.setBounds(150,65,182,25);
 txemail.setBounds(10,110,388,25);
 txcnh.setBounds(270,25,120,25);
 txplaca.setBounds(150,25,70,25);
 txrenavan.setBounds(270,25,100,25);
 txt1.setBounds(510,65,170,24);
 txt2.setBounds(510,115,170,24);
 txt3.setBounds(510,115,170,24);

 //AJUSTANDO O TAMANHO DAS **LABEL'S P/JP2**

 labnome.setBounds(10,04,50,15);
 labidcliente.setBounds(420,04,50,15);
 labcpf.setBounds(10,35,50,40);
 labrg.setBounds(150,35,50,40);
 labnasc.setBounds(290,35,50,40);
 labecivil.setBounds(420,50,100,10); //AJUSTANDO O TAMANHO DAS **LABEL'S/JP2**

 labendereco.setBounds(10,04,70,15);
 labnum.setBounds(290,05,170,15);
 labcomp.setBounds(345,05,300,15);
 labcep.setBounds(510,05,70,15);
 labbairro.setBounds(10,35,50,40);
 labcidade.setBounds(150,35,45,40);
 labemail.setBounds(10,80,45,40);
 labcnh.setBounds(10,05,120,25);
 labplaca.setBounds(150,05,70,25);
 labrenavan.setBounds(270,05,100,25);
 labtel.setBounds(410,50,100,10);
 labuf.setBounds(345,50,50,10);
 uf.setBounds(345,65,50,05);
 t1.setBounds(410,65,95,10);
 t2.setBounds(410,115,95,10);
 t3.setBounds(410,115,95,10);

 //AJUSTANDO O TAMANHO DAS **LABE'S P/JP3**

 labdados.setBounds(10,05,300,15);
 area.setBounds(10,05,300,15);

 //definindo tamanho DO PAINEL
 //10 proximo da Panel a cima //10proximo da Panel a cima
 //730 largura
 //40 altura

 JP1.setBounds(10,10,695,100);
 JP2.setBounds(10,118,695,145);
 JP3.setBounds(10,340,695,210);
 JP4.setBounds(10,270,695,65);

 getContentPane().add(JP1);
 getContentPane().add(JP2);
 getContentPane().add(JP3);
 getContentPane().add(JP4);

 //AJUSTANDO**TAMANHO** e**POSIÇÃO**DOS BOTÕES

 butIncluir.setBounds(30,170,100,30);
 butAlterar.setBounds(160,170,100,30);
 butExcluir.setBounds(290,170,100,30);
 butLimpar.setBounds(420,170,100,30);
 butPesquisar.setBounds(550,170,100,30);

 //TAMANHO DA JANELA


 setTitle("Cadastro"); setSize(735,600);
 setVisible(true);}

 public void itemStateChanged(ItemEvent e){
 String resp=Sexo.getSelection
 ().getActionCommand();

 JOptionPane.showMessageDialog(null,resp);
 }

 public static void main(String[]args){
 new GAS();


}
}

