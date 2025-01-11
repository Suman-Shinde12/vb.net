NOTEPAD CLONE
using System;
using System.Windows.Forms;
class NotepadClone : Form
{
    TextBox textBox;
    public NotepadClone()
    {
        textBox = new TextBox
        {
            Multiline = true,
            Dock = DockStyle.Fill,
            Font = new System.Drawing.Font("Consolas", 12)
        };
        MenuStrip menuStrip = new MenuStrip();
        ToolStripMenuItem fileMenu = new ToolStripMenuItem("File");
        fileMenu.DropDownItems.Add("Open", null, OpenFile);
        fileMenu.DropDownItems.Add("Save", null, SaveFile);
        fileMenu.DropDownItems.Add("Exit", null, (s, e) => Close());
        menuStrip.Items.Add(fileMenu);
        Controls.Add(menuStrip);
        Controls.Add(textBox);
        MainMenuStrip = menuStrip;
    }
    private void OpenFile(object sender, EventArgs e)
    {
        OpenFileDialog ofd = new OpenFileDialog();
        if (ofd.ShowDialog() == DialogResult.OK)
        {
            textBox.Text = System.IO.File.ReadAllText(ofd.FileName);
        }
    }
    private void SaveFile(object sender, EventArgs e)
    {
        SaveFileDialog sfd = new SaveFileDialog();
        if (sfd.ShowDialog() == DialogResult.OK)
        {
            System.IO.File.WriteAllText(sfd.FileName, textBox.Text);
        }
    }
    [STAThread]
    static void Main()
    {
        Application.Run(new NotepadClone());
    }
}
