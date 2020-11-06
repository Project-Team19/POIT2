public partial class cPlayForm : Form
    {
        int Balance, BetCount; //переменные баланса и ставки
        Random random = new Random();//генератор случайных чисел

        public void SaveGameResults()//ф-я сохранения результатов игры
        {
            if (BetCount == 1) return; ?
            if (MessageBox.Show("Сохранить историю игры?", "Игра Кости", MessageBoxButtons.YesNo, MessageBoxIcon.Question) == DialogResult.Yes)
            {
                using (System.IO.StreamWriter file = new System.IO.StreamWriter(AppDomain.CurrentDomain.BaseDirectory.ToString() + @"\History.txt",true)) ?
                {
                    int i;

                    for (i = 0; i < HistoryBox.Items.Count; i++) //просматриваем историю в цикле
                        file.WriteLine(HistoryBox.Items[i].ToString());
                    file.Close();//запись в листбокс значений каждого хода
                }
            }
            
        }
Детали на https://studlearn.com/works/details/igra-kosti-c-winforms-visual-studio-2010-761
