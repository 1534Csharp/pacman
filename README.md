Pacman 2024/12/10


碰到牆壁後停下

![image](https://github.com/user-attachments/assets/718f7925-fc98-4d69-b902-230913fdcb8e)



private void Form1_KeyDown(object sender, KeyEventArgs e)
{

    up = down = left = right = false;
    switch (e.KeyCode)
    {

        case Keys.Up:
            up = true;
            pacman.Image = Image.FromFile("pacmanup.png");
            break;
        case Keys.Down:
            down = true;
            pacman.Image = Image.FromFile("pacmandown.png");
            break;
        case Keys.Left:
            left = true;
            pacman.Image = Image.FromFile("pacmanleft.png");
            break;
        case Keys.Right:
            right = true;
            pacman.Image = Image.FromFile("pacman.png");
            break;
    }
吃金幣 每吃一個金幣+1分
        private void timer1_Tick(object sender, EventArgs e)
    {
        if (up && pacman.Location.Y > 78)
        {
            pacman.Top -= 1;
        }
        else
        {
            up = false;
        }
        if (down && pacman.Location.Y < 755)
        {
            pacman.Top += 1;
        }
        else
        {
            down = false;
        }
        if (left && pacman.Location.X > 49)
        {
            pacman.Left -= 1;
        }
        else
        {
            left = false;
        }
        if (right && pacman.Location.X < 1102)
        {
            pacman.Left += 1;
        }
        else
        {
            right = false;
        }
        if(pacman.Bounds.IntersectsWith(coin1.Bounds))
        {
            coin1.Visible = false;
            coin1.Enabled = false;
            if (!iscoin[0])
                score = score + 1;
            iscoin[0] = true;
        }
        if (pacman.Bounds.IntersectsWith(coin2.Bounds))
        {
            coin2.Visible = false;
            coin2.Enabled = false;
            if (!iscoin[1])
                score = score + 1;
            iscoin[1] = true;
        }
        if (pacman.Bounds.IntersectsWith(coin3.Bounds))
        {
            coin3.Visible = false;
            coin3.Enabled = false;
            if (!iscoin[2])
                score = score + 1;
            iscoin[2] = true;
        }
        if (pacman.Bounds.IntersectsWith(coin4.Bounds))
        {
            coin4.Visible = false;
            coin4.Enabled = false;
            if (!iscoin[3])
                score = score + 1;
            iscoin[3] = true;
        }
        label1.Text = "Score : " + score;
    }

   ![image](https://github.com/user-attachments/assets/5c1c219f-a2c6-4852-9ead-47fe2ee309a6)

   總結
   namespace PacMan
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        bool up = false;
        bool down = false;
        bool left = false;
        bool right = false;
       
        bool[] iscoin = { false, false, false, false };
        private void Form1_KeyDown(object sender, KeyEventArgs e)
        {

            up = down = left = right = false;
            switch (e.KeyCode)
            {

                case Keys.Up:
                    up = true;
                    pacman.Image = Image.FromFile("pacmanup.png");
                    break;
                case Keys.Down:
                    down = true;
                    pacman.Image = Image.FromFile("pacmandown.png");
                    break;
                case Keys.Left:
                    left = true;
                    pacman.Image = Image.FromFile("pacmanleft.png");
                    break;
                case Keys.Right:
                    right = true;
                    pacman.Image = Image.FromFile("pacman.png");
                    break;
            }



        }
        int score = 0;
        private void timer1_Tick(object sender, EventArgs e)
        {
            if (up && pacman.Location.Y > 78)
            {
                pacman.Top -= 1;
            }
            else
            {
                up = false;
            }
            if (down && pacman.Location.Y < 755)
            {
                pacman.Top += 1;
            }
            else
            {
                down = false;
            }
            if (left && pacman.Location.X > 49)
            {
                pacman.Left -= 1;
            }
            else
            {
                left = false;
            }
            if (right && pacman.Location.X < 1102)
            {
                pacman.Left += 1;
            }
            else
            {
                right = false;
            }
            if(pacman.Bounds.IntersectsWith(coin1.Bounds))
            {
                coin1.Visible = false;
                coin1.Enabled = false;
                if (!iscoin[0])
                    score = score + 1;
                iscoin[0] = true;
            }
            if (pacman.Bounds.IntersectsWith(coin2.Bounds))
            {
                coin2.Visible = false;
                coin2.Enabled = false;
                if (!iscoin[1])
                    score = score + 1;
                iscoin[1] = true;
            }
            if (pacman.Bounds.IntersectsWith(coin3.Bounds))
            {
                coin3.Visible = false;
                coin3.Enabled = false;
                if (!iscoin[2])
                    score = score + 1;
                iscoin[2] = true;
            }
            if (pacman.Bounds.IntersectsWith(coin4.Bounds))
            {
                coin4.Visible = false;
                coin4.Enabled = false;
                if (!iscoin[3])
                    score = score + 1;
                iscoin[3] = true;
            }
            label1.Text = "Score : " + score;
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            timer1.Interval = 5;
            timer1.Enabled = true;

        }
    }
}
![image](https://github.com/user-attachments/assets/2159532a-d624-4446-a176-90a659410fb0)

   
