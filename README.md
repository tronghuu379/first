# first
using Caliburn.Micro;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using WpfApplication1.ViewModels;

namespace WpfApplication1
{
    public class Bootstrapper : BootstrapperBase
    {
        public Bootstrapper()
        {
            Initialize();
        }
        protected override void OnStartup(object sender, StartupEventArgs e)
        {
            DisplayRootViewFor<ShellViewModel>();
        }
    }
}

<Application x:Class="WpfApplication1.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:local="clr-namespace:WpfApplication1"
             >
    <Application.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary>
                    <local:Bootstrapper x:Key="bootstrapper"/>
                </ResourceDictionary>
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
    </Application.Resources>
</Application>

<UserControl x:Class="WpfApplication1.Views.ShellView"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" 
             xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 
             xmlns:cal="http://www.caliburnproject.org"
             xmlns:local="clr-namespace:WpfApplication1.Views"
             mc:Ignorable="d" 
             d:DesignHeight="300" d:DesignWidth="300" Height="300" Width="500">
    <Grid>
            <TextBlock x:Name="Title" FontSize="20"/>
        <Button Height="20" Width="40"
                Content="Show"
                cal:Message.Attach="[Event Click] = [Action Show()]"></Button>
    </Grid>
</UserControl>

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Caliburn.Micro;

namespace WpfApplication1.ViewModels
{
    public class ShellViewModel
    {
        public ShellViewModel()
        {
            Title = "Da len roi";
        }
        private string _title;
        public string Title
        {
            get { return _title; }
            set { _title = value;
                NotifyOfPropertyChange(()=>)}
        }
        public void Show()
        {
            Title = "Kiem tra button";
        }
    }
}
