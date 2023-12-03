# pogiko
jomari tapusin mo to

 public Form1()
 {
     InitializeComponent();
 }
 private void pictureBox1_Click(object sender, EventArgs e) { }
 private void button1_Click(object sender, EventArgs e)
 {
     string picture = "";
     try
     {
         OpenFileDialog pic = new OpenFileDialog();
         pic.Filter = "JPEG files(*.jpg)|*.jpg|PNG files(*.png)|*.png|All Files(*.*)|*.*";
         if(pic.ShowDialog() == DialogResult.OK) 
         {
             picture = pic.FileName;
             pictureBox1.ImageLocation = picture;
         }
     }
     catch(Exception) 
     {
         MessageBox.Show("error", "error", MessageBoxButtons.OK, MessageBoxIcon.Error);
     }

 }
 private void button2_Click(object sender, EventArgs e)
 {
     string name = $"{textBox2.Text} {textBox3.Text} {textBox1.Text}";
     string gender = Gender();
     string bday = $"{comboBox2.Text} {comboBox1.Text}, {comboBox3.Text}";
     string bday2 = bday;
     string program = comboBox4.Text;

     if (string.IsNullOrWhiteSpace(name))
     {
         MessageBox.Show("Name cannot be empty.", "ERROR", MessageBoxButtons.OK, MessageBoxIcon.Error);
         return;
     }
     else if (string.IsNullOrWhiteSpace(textBox1.Text))
     {
         MessageBox.Show("Name must be complete, sorry.", "ERROR", MessageBoxButtons.OK, MessageBoxIcon.Error);
         return;
     }
     else if (string.IsNullOrWhiteSpace(textBox2.Text))
     {
         MessageBox.Show("Name must be complete, sorry.", "ERROR", MessageBoxButtons.OK, MessageBoxIcon.Error);
         return;
     }
     else if (string.IsNullOrWhiteSpace(textBox3.Text))
     {
         MessageBox.Show("Name must be complete, sorry.", "ERROR", MessageBoxButtons.OK, MessageBoxIcon.Error);
         return;
     }

     string Gender()
     {
         if (radioButton1.Checked)
         {
             return "Male";
         }
         else if (radioButton2.Checked)
         {
             return "Female";
         }
         else
         {
             MessageBox.Show("Gender please", "ERROR", MessageBoxButtons.OK, MessageBoxIcon.Error);
             return "";
         }
     }
     

     student(name, gender, bday, program);
 }
 public void student(string name, string gender)
 {
     string info = $"\nStudent Name: {name}\nGender: {gender}";
     MessageBox.Show(info, " ", MessageBoxButtons.OK);
 }
 public void student(string name, string gender, string bday)
 {
     string info = $"\nStudent Name: {name}\nGender: {gender}\nDate of Birth: {bday}";
     MessageBox.Show(info, " ", MessageBoxButtons.OK);
 }
 public void student(string name, string gender, string bday, string program)
 {
     string info = $"\nStudent Name: {name}\nGender: {gender}\nDate of Birth: {bday}\nProgram Course: {program}";
     string name2 = $"Student name: {textBox2.Text} {textBox3.Text} {textBox1.Text}" + $"\nProgram: {comboBox4.Text}";
     
     MessageBox.Show(info, " ", MessageBoxButtons.OK);
     MessageBox.Show(name2, " ", MessageBoxButtons.OK);
     this.Close();
 }
