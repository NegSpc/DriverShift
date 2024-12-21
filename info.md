public class Driver
{
    public string Name { get; set; }
    public string TimeZone { get; set; }
    public double AverageLapTime { get; set; }
    // Other properties...
}


public class DriverViewModel : INotifyPropertyChanged
{
    private Driver _driver;
    public Driver Driver
    {
        get => _driver;
        set
        {
            _driver = value;
            OnPropertyChanged(nameof(Driver));
            OnPropertyChanged(nameof(Name));
            OnPropertyChanged(nameof(TimeZone));
            OnPropertyChanged(nameof(AverageLapTime));
        }
    }

    public string Name
    {
        get => _driver.Name;
        set
        {
            _driver.Name = value;
            OnPropertyChanged(nameof(Name));
        }
    }

    public string TimeZone
    {
        get => _driver.TimeZone;
        set
        {
            _driver.TimeZone = value;
            OnPropertyChanged(nameof(TimeZone));
        }
    }

    public double AverageLapTime
    {
        get => _driver.AverageLapTime;
        set
        {
            _driver.AverageLapTime = value;
            OnPropertyChanged(nameof(AverageLapTime));
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;
    protected void OnPropertyChanged(string propertyName)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }
}


<Window x:Class="RaceScheduler.DriverView"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="DriverView" Height="300" Width="400">
    <Grid>
        <StackPanel>
            <TextBox Text="{Binding Name, Mode=TwoWay}" PlaceholderText="Driver Name"/>
            <TextBox Text="{Binding TimeZone, Mode=TwoWay}" PlaceholderText="Time Zone"/>
            <TextBox Text="{Binding AverageLapTime, Mode=TwoWay}" PlaceholderText="Average Lap Time"/>
            <!-- Other controls... -->
        </StackPanel>
    </Grid>
</Window>



public partial class DriverView : Window
{
    public DriverView()
    {
        InitializeComponent();
        this.DataContext = new DriverViewModel
        {
            Driver = new Driver
            {
                Name = "John Doe",
                TimeZone = "GMT+0",
                AverageLapTime = 123.45
                // Other properties...
            }
        };
    }
}
