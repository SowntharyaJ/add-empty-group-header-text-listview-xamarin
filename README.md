**[View document in Syncfusion Xamarin Knowledge base](https://www.syncfusion.com/kb/12095/how-to-update-empty-group-header-text-in-xamarin-forms-listview-sflistview)**

## Sample

```xaml
<syncfusion:SfListView x:Name="listView" ItemSize="60" ItemsSource="{Binding ContactsInfo}">
    <syncfusion:SfListView.ItemTemplate >
        <DataTemplate>
            <Grid x:Name="grid">
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="70" />
                    <ColumnDefinition Width="*" />
                </Grid.ColumnDefinitions>
                <Image Source="{Binding ContactImage}" VerticalOptions="Center" HorizontalOptions="Center" HeightRequest="50" WidthRequest="50"/>
                <Grid Grid.Column="1" RowSpacing="1" Padding="10,0,0,0" VerticalOptions="Center">
                    <Label LineBreakMode="NoWrap" TextColor="#474747" Text="{Binding ContactName}"/>
                    <Label Grid.Row="1" Grid.Column="0" TextColor="#474747" LineBreakMode="NoWrap" Text="{Binding ContactNumber}"/>
                </Grid>
            </Grid>
        </DataTemplate>
    </syncfusion:SfListView.ItemTemplate>
    <syncfusion:SfListView.GroupHeaderTemplate>
        <DataTemplate>
            <Grid BackgroundColor="Teal">
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="*"/>
                    <ColumnDefinition Width="*"/>
                </Grid.ColumnDefinitions>
                <Label Text="{Binding ., Converter={StaticResource GroupHeaderConverter}}" FontSize="22" TextColor="White" FontAttributes="Bold" VerticalOptions="Center" Margin="10,0,0,0" />
                <Grid Grid.Column="1" HorizontalOptions="End" VerticalOptions="End">
                    <Image x:Name="button" Source="Add.png" HeightRequest="50" WidthRequest="40" >
                        <Image.GestureRecognizers>
                            <TapGestureRecognizer Command="{Binding Path=BindingContext.ButtonTappedCommand, Source={x:Reference listView}}" CommandParameter="{Binding .}"/>
                        </Image.GestureRecognizers>
                    </Image>
                </Grid>
            </Grid>
        </DataTemplate>
    </syncfusion:SfListView.GroupHeaderTemplate>
</syncfusion:SfListView>
```

## Requirements to run the demo

* [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/) or [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)
* Xamarin add-ons for Visual Studio (available via the Visual Studio installer).

## Troubleshooting

### Path too long exception

If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.