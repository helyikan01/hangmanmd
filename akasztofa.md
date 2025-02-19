#  Grid: Akasztofa

## Feladat : 
Projekt neve: **Akasztofa**

Projekt leírása: Hozz létre egy 2x2-es Grid-et ahol az első cellában a szó a másodikban a gratuláció és rossz tippek a harmadikban az ábécé gombjai a negyedikben pedig a játék állapotot mutató kép található.

Működés: Az Akasztófa játékban a felhasználó egy szó betűit próbálja kitalálni, és minden helytelen tipp után egy újabb részlet jelenik meg a képen. A játék akkor ér véget, ha a felhasználó teljesen kitalálja a szót vagy elfogy a hibás próbálkozások száma.

1. Hozz létre egy 2x2-es Grid-et: A Grid-ben két oszlopot és két sort definiálsz. Az első oszlop tartalmazza a szó megjelenítését és az ábécé gombjait, míg a második oszlopban a gratulációkat és a hibás tippek számát, valamint a hangman képet helyezed el.
2. Szó megjelenítése: Az első sor első cellájában egy TextBlock van, amely a WordDisplay néven jeleníti meg a kitalálandó szó betűit.
3. Ábécé gombok hozzáadása: Az első sor második cellájában egy ScrollViewer és egy WrapPanel található, amiben az összes betű (A-Z, ékezetekkel) gombként szerepel. Ezek a gombok kattintáskor elindítanak egy eseményt, amely a betűk tippelését kezeli.
4. Gratuláció és hibás tippek száma: A második sor első cellájában egy StackPanel található, amiben két TextBlock jeleníti meg a gratuláció szöveget és a hibás tippek számát.
5. Kép a hangman-ről: A második sor második cellájában egy Image található, amely az aktuális hibás tippek számának megfelelő képet jeleníti meg. A képek a hangman0.png-től a hangman10.png-ig terjednek, és a hibás próbálkozások számától függően változnak.

```c#

<Window x:Class="Akasztofa.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Akasztófa Játék" Height="600" Width="700">
    <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition/>
            <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
        </Grid.RowDefinitions>
        <Border Grid.Column="0" Grid.Row="0" BorderBrush="Black" BorderThickness="1" Margin="10">
            <TextBlock x:Name="WordDisplay" HorizontalAlignment="Center" VerticalAlignment="Center" FontSize="24"/>
        </Border>
        <Border Grid.Column="0" Grid.Row="1" BorderBrush="Black" BorderThickness="1" Margin="10">
            <ScrollViewer VerticalScrollBarVisibility="Auto">
                <WrapPanel x:Name="AlphabetPanel" HorizontalAlignment="Center" VerticalAlignment="Center" Margin="10">
                    <Button Content="A" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Á" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="B" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="C" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="D" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="E" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="É" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="F" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="G" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="H" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="I" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Í" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="J" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="K" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="L" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="M" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="N" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="O" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ó" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ö" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ő" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="P" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Q" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="R" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="S" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="T" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="U" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ú" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ü" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ű" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="V" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="W" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="X" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Y" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Z" Click="LetterButton_Click" Margin="2" Width="30"/>
                </WrapPanel>
            </ScrollViewer>
        </Border>
        <Border Grid.Column="1" Grid.Row="0" BorderBrush="Black" BorderThickness="1" Margin="10">
            <StackPanel VerticalAlignment="Center" HorizontalAlignment="Center">
                <TextBlock x:Name="CongratsText" Text="" FontSize="20" TextAlignment="Center" Margin="10"/>
                <TextBlock x:Name="WrongGuessesText" Text="Rossz tippek: 0" FontSize="16" TextAlignment="Center" Margin="10"/>
            </StackPanel>
        </Border>
        <Border Grid.Column="1" Grid.Row="1" BorderBrush="Black" BorderThickness="1" Margin="10">
            <Image x:Name="HangmanImage" Source="Images/hangman0.png" Stretch="Uniform" Margin="10"/>
        </Border>
    </Grid>
</Window>

```
6. Szavak betöltése fájlból: A játék elindításakor a szavakat egy szavak.txt fájlból töltjük be. Ha a fájl nem létezik vagy hiba történik a betöltés során, egy hibaüzenet jelenik meg és a program bezárul.

```c#

private void LoadWordsFromFile()
{
    try
    {
        string filePath = "szavak.txt";
        if (File.Exists(filePath))
        {
            words = File.ReadAllLines(filePath);
        }
        else
        {
            MessageBox.Show("A szavak nem találhatóak");
            this.Close();
        }
    }
    catch (Exception ex)
    {
        MessageBox.Show($"Hiba van {ex.Message}");
        this.Close();
    }
}

```

7. Új játék kezdése: Ha sikerült betölteni a szavakat, a UjJatekotKezd metódus véletlenszerűen választ ki egy szót a listából, és inicializálja a szükséges változókat, például a hibás tippek számát és az aktuális tippelt betűk listáját.

```c#

private void StartNewGame()
{
    if (words == null || words.Length == 0)
    {
        MessageBox.Show("Nincsenek szavak");
        return;
    }
    Random random = new Random();
    selectedWord = words[random.Next(words.Length)];
    guessedLetters = new string('_', selectedWord.Length).ToCharArray();
    incorrectGuesses = 0;
    UpdateDisplay();
    UpdateHangmanImage();
    EnableAllLetterButtons();
    CongratsText.Text = "";
    WrongGuessesText.Text = $"Rossz tippek: {incorrectGuesses}";
}

```

8. Betűgombok kezelése: A felhasználó rákattint egy betűgombra, és a rendszer ellenőrzi, hogy a kitalált szó tartalmazza-e a tippelt betűt. Ha igen, akkor a szó aktuális állapotát frissíti, ha nem, akkor növeli a hibás próbálkozások számát és frissíti a képet.

```c#

private void LetterButton_Click(object sender, RoutedEventArgs e)
{
    Button button = (Button)sender;
    char guessedChar = button.Content.ToString().ToLower()[0];
    button.IsEnabled = false;

    if (selectedWord.Contains(guessedChar))
    {
        for (int i = 0; i < selectedWord.Length; i++)
        {
            if (selectedWord[i] == guessedChar)
            {
                guessedLetters[i] = guessedChar;
            }
        }
    }
    else
    {
        incorrectGuesses++;
        WrongGuessesText.Text = $"Rossz tippek: {incorrectGuesses}";
        UpdateHangmanImage();
    }
    UpdateDisplay();
    CheckGameStatus();
}

```

9. Játék állapotának ellenőrzése: Minden tipp után a rendszer ellenőrzi, hogy a felhasználó kitalálta-e a teljes szót, vagy elérte-e a maximális próbálkozási számot. Ha a játék véget ért, letiltja az összes betűgombot és kiírja az eredményt.

```c#

private void CheckGameStatus()
{
    if (guessedLetters.SequenceEqual(selectedWord.ToCharArray()))
    {
        CongratsText.Text = "Gratulálok nyertél!";
        DisableAllLetterButtons();
    }
    else if (incorrectGuesses >= maxAttempts)
    {
        CongratsText.Text = $"Vesztettél. A szó: {selectedWord}";
        DisableAllLetterButtons();
    }
}

```

10. Kép frissítése és betűgombok letiltása: Minden hibás próbálkozás után a megfelelő akasztófa képet frissítjük. Ha a játék véget ért, letiltjuk az összes betűgombot, hogy ne lehessen több tippelés.

**Kép frissítése:**

```c#

private void UpdateHangmanImage()
{
    string imagePath = $"Images/hangman{incorrectGuesses}.png";

    if (File.Exists(imagePath))
    {
        HangmanImage.Source = new System.Windows.Media.Imaging.BitmapImage(new Uri(imagePath, UriKind.Relative));
    }
    else
    {
        MessageBox.Show($"A kép nem található: {imagePath}");
    }
}

```

**Betűgombok letiltása:**

```c#

 private void EnableAllLetterButtons()
 {
     foreach (var button in AlphabetPanel.Children.OfType<Button>())
     {
         button.IsEnabled = true;
     }
 }

```

<details>
<summary>Nyiss le az xaml.cs forrásért</summary>

```c#

using System;
using System.IO;
using System.Linq;
using System.Windows;
using System.Windows.Controls;

namespace Akasztofa
{
    public partial class MainWindow : Window
    {
        private string[] words;
        private string selectedWord;
        private char[] guessedLetters;
        private int incorrectGuesses;
        private const int maxAttempts = 11;

        public MainWindow()
        {
            InitializeComponent();
            LoadWordsFromFile();
            StartNewGame();
        }
        private void LoadWordsFromFile()
        {
            try
            {
                string filePath = "szavak.txt";
                if (File.Exists(filePath))
                {
                    words = File.ReadAllLines(filePath);
                }
                else
                {
                    MessageBox.Show("A szavak nem találhatóak");
                    this.Close();
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show($"Hiba van {ex.Message}");
                this.Close();
            }
        }
        private void StartNewGame()
        {
            if (words == null || words.Length == 0)
            {
                MessageBox.Show("Nincsenek szavak");
                return;
            }
            Random random = new Random();
            selectedWord = words[random.Next(words.Length)];
            guessedLetters = new string('_', selectedWord.Length).ToCharArray();
            incorrectGuesses = 0;
            UpdateDisplay();
            UpdateHangmanImage();
            EnableAllLetterButtons();
            CongratsText.Text = "";
            WrongGuessesText.Text = $"Rossz tippek: {incorrectGuesses}";
        }
        private void UpdateDisplay()
        {
            WordDisplay.Text = string.Join(" ", guessedLetters);
        }
        private void UpdateHangmanImage()
        {
            string imagePath = $"Images/hangman{incorrectGuesses}.png";

            if (File.Exists(imagePath))
            {
                HangmanImage.Source = new System.Windows.Media.Imaging.BitmapImage(new Uri(imagePath, UriKind.Relative));
            }
            else
            {
                MessageBox.Show($"A kép nem található: {imagePath}");
            }
        }
        private void EnableAllLetterButtons()
        {
            foreach (var button in AlphabetPanel.Children.OfType<Button>())
            {
                button.IsEnabled = true;
            }
        }
        private void LetterButton_Click(object sender, RoutedEventArgs e)
        {
            Button button = (Button)sender;
            char guessedChar = button.Content.ToString().ToLower()[0];
            button.IsEnabled = false;

            if (selectedWord.Contains(guessedChar))
            {
                for (int i = 0; i < selectedWord.Length; i++)
                {
                    if (selectedWord[i] == guessedChar)
                    {
                        guessedLetters[i] = guessedChar;
                    }
                }
            }
            else
            {
                incorrectGuesses++;
                WrongGuessesText.Text = $"Rossz tippek: {incorrectGuesses}";
                UpdateHangmanImage();
            }
            UpdateDisplay();
            CheckGameStatus();
        }
        private void CheckGameStatus()
        {
            if (guessedLetters.SequenceEqual(selectedWord.ToCharArray()))
            {
                CongratsText.Text = "Gratulálok nyertél!";
                DisableAllLetterButtons();
            }
            else if (incorrectGuesses >= maxAttempts)
            {
                CongratsText.Text = $"Vesztettél. A szó: {selectedWord}";
                DisableAllLetterButtons();
            }
        }
        private void DisableAllLetterButtons()
        {
            foreach (var button in AlphabetPanel.Children.OfType<Button>())
            {
                button.IsEnabled = false;
            }
        }
    }
}

```
</details>

<details>
<summary>Nyiss le az xaml forrásért</summary>

```c#

<Window x:Class="Akasztofa.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Akasztófa Játék" Height="600" Width="700">
    <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition/>
            <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
        </Grid.RowDefinitions>
        <Border Grid.Column="0" Grid.Row="0" BorderBrush="Black" BorderThickness="1" Margin="10">
            <TextBlock x:Name="WordDisplay" HorizontalAlignment="Center" VerticalAlignment="Center" FontSize="24"/>
        </Border>
        <Border Grid.Column="0" Grid.Row="1" BorderBrush="Black" BorderThickness="1" Margin="10">
            <ScrollViewer VerticalScrollBarVisibility="Auto">
                <WrapPanel x:Name="AlphabetPanel" HorizontalAlignment="Center" VerticalAlignment="Center" Margin="10">
                    <Button Content="A" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Á" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="B" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="C" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="D" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="E" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="É" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="F" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="G" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="H" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="I" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Í" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="J" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="K" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="L" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="M" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="N" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="O" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ó" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ö" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ő" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="P" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Q" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="R" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="S" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="T" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="U" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ú" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ü" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Ű" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="V" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="W" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="X" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Y" Click="LetterButton_Click" Margin="2" Width="30"/>
                    <Button Content="Z" Click="LetterButton_Click" Margin="2" Width="30"/>
                </WrapPanel>
            </ScrollViewer>
        </Border>
        <Border Grid.Column="1" Grid.Row="0" BorderBrush="Black" BorderThickness="1" Margin="10">
            <StackPanel VerticalAlignment="Center" HorizontalAlignment="Center">
                <TextBlock x:Name="CongratsText" Text="" FontSize="20" TextAlignment="Center" Margin="10"/>
                <TextBlock x:Name="WrongGuessesText" Text="Rossz tippek: 0" FontSize="16" TextAlignment="Center" Margin="10"/>
            </StackPanel>
        </Border>
        <Border Grid.Column="1" Grid.Row="1" BorderBrush="Black" BorderThickness="1" Margin="10">
            <Image x:Name="HangmanImage" Source="Images/hangman0.png" Stretch="Uniform" Margin="10"/>
        </Border>
    </Grid>
</Window>

```
</details>
