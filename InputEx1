public class InputEx1 extends JFrame {
    JButton btnInsert, btnDelete, btnUpdate, btnSelect, btnSearch;
    JTextField tfId, tfName, tfDept, tfSearch;
    JTextArea ta;
    JRadioButton rbId, rbName, rbDept;
    Connection conn;
    Statement stmt;
    ResultSet rs;
    
    public InputEx1(){
        this.setTitle("학생 프로젝트");
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        createGUI();
        
	}
	
	public void createGUI(){
	    Container c = this.getContentPane();
	    c.setLayout(new FlowLayout());
	    
	    c.add(new JLabel("학번"));
	    tfId = new JTextField(20);
	    c.add(tfId);
	    
	    c.add(new JLabel("이름"));
	    tfName = new JTextField(20);
	    c.add(tfName);
	    
	    c.add(new JLabel("전공"));
	    tfDept = new JTextField(20);
	    c.add(tfDept);
	    
	    btnInsert = new JButton("입력");
	    c.add(btnInsert);
	    
	    btnDelete = new JButton("삭제");
	    c.add(btnDelete);
	    
	    btnUpdate = new JButton("수정");
	    c.add(btnUpdate);
	    
	    btnSelect = new JButton("선택");
	    c.add(btnSelect);
	    
	    //검색
	    tfSearch = new JTextField(18);
	    rbId = new JRadioButton("학번", true);
	    rbName = new JRadioButton("이름");
	    rbDept = new JRadioButton("학과");
	    
	    ButtonGroup group = new ButtonGroup();
	    group.add(rbId);
	    group.add(rbName);
	    group.add(rbDept);
	    
	    btnSearch = new JButton("검색");
	    JPanel pn1 = new JPanel();
	    pn1.add(new JLabel(""));
	    pn1.add(tfSearch);
	    pn1.add(btnsarch);
	    
	    JPanel pn2 = new JPanel();
	    pn2.add(rbId);
	    pn2.add(rbName);
	    pn2.add(rbDept);
	    
	    JPanel pMiddle = new JPanel(new BorderLayout(0, 0));
	    pMiddle.add(BorderLayout.NORTH, pn1);
	    pMiddle.add(BorderLayout.CENTER, pn2);
	    
	    TitleBorder tb = new TitledBorder("검색");
	    pMiddle.setBorder(tb);
	    c.add(pMiddle);
	    
	    ta.new JTextArea(15, 20);
	    c.add(ta);
	}
	
	//dbSearch
	public void dbSearch(){
	    conn = DBConn.dbConnection();
	    stmt = conn.createStatement();
	    
	    String searchText = tfSearch.getText().toString();
	    String searchSql = "";
	    
	    if(rbId.isSelected()){
	        searchSql = "select * from student where id = '" + searchText + "';"; }
	    else if(rbName.isSelected()){
	        searchSql = "select * from student where id = '" + searchText + "';";  }
	    else{
	        searchSql = "select * from student where id = '" + searchText + "';"; }
	   
	    rs = stmt.executeQuery(searchSql);
	    
	    String line = "";
	    ta.setText("     id         name       dept        \n");
	    ta.append("========================================\n");
	    while(rs.next()){
	        String name = rs.getString("name");
	        String dept = rs.getString("dept");
	        String id = rs.getString("id");
	        
	        line = "|" + id "|" + name + "|" + dept + "\n";
	        System.out.println("rs => " + line);
	        ta.append(line);
	    } 
	    stmt.close();
	    conn.close();
	}
	
}
}
