
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using System.Collections;

namespace List_Çalışma
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        List<object> ülkeler = new List<object>();
        private void listBox1_SelectedIndexChanged(object sender, EventArgs e)
        {

        }

        private void button1_Click(object sender, EventArgs e)
        {
            ülkeler.Add(textBox1.Text);
        }

        private void button2_Click(object sender, EventArgs e)
        {
            ülkeler.Insert(Convert.ToInt32(textBox2.Text),textBox1.Text);
        }

        private void button3_Click(object sender, EventArgs e)
        {
            int artmak = listBox1.SelectedIndex;
            ülkeler.Insert(artmak + 1, textBox1.Text);
        }

        private void button5_Click(object sender, EventArgs e)
        {
            if (ülkeler.Contains(textBox4.Text))
            {
                label8.Text = "Bulundu";
                label8.ForeColor = Color.Green;
            }
            else
            {
                label8.Text = "Bulunamadı";
                label8.ForeColor = Color.Red;
            }
        }

        private void button6_Click(object sender, EventArgs e)
        {
            ülkeler.Remove(textBox5.Text);
        }

        private void button7_Click(object sender, EventArgs e)
        {
            ülkeler.Clear();
        }

        private void button9_Click(object sender, EventArgs e)
        {
            listBox1.Items.Clear();
            
        }

        private void button10_Click(object sender, EventArgs e)
        {
            ülkeler.Remove(listBox1.SelectedItem);
        }

        private void button4_Click(object sender, EventArgs e)
        {
            int deger = Convert.ToInt32(textBox3.Text);
            label4.Text = ülkeler[deger].ToString();
        }

        private void button8_Click(object sender, EventArgs e)
        {
            for(int i = 0; i < ülkeler.Count; i++)
            {
                listBox1.Items.Add(ülkeler[i]);
            }
        }
    }
}
