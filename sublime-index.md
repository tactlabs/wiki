/ [Home](index.md)

# Sublime Index Commands

To achieve this, you can create a custom Sublime Text plugin that inserts the current date and time
when you press Cmd+K. Here's how to do it:

Step-by-Step Plugin Creation :

1.Open Sublime Text.

2.Go to Tools -> Developer -> New Plugin.

3.Replace the content with the following code:


```
import sublime
import sublime_plugin
from datetime import datetime

class InsertDateTimeCommand(sublime_plugin.TextCommand):
    def run(self, edit):
        # Get the current date and time
        now = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        # Insert the date and time at the current cursor position
        self.view.insert(edit, self.view.sel()[0].begin(), f"({now})")

```

4.Save the file with a  .py extension, for example, insert_date_time.py .




Key Binding :

1.Go to Preferences -> Key Bindings. This will open two files: the default key bindings on the
left and your custom key bindings on the right.

2.Add a new key binding to the right file. Here’s an example configuration:

```
[
    {
        "keys": ["super+k"],  // Cmd is referred to as "super"
        "command": "insert_date_time"
    }
]

```
Now, when you press Cmd+K, the current date and time will be inserted at your cursor's position in the format 
(2024-07-25 17:56:28).



```
-------------------------------------------------------------------------------------------------------------------
Day # 223 August 10 2024 - Saturday
2024-08-10 10:43:27
---------------------------------------



-------------/

```
To create a Sublime Text plugin that inserts the exact date and time format you provided, follow these steps:

Plugin Code :
1.Create the Plugin:
    
  - Go to Tools > Developer > New Plugin… in Sublime Text.
  - Replace the default content with the following Python code:

```
import sublime
import sublime_plugin
from datetime import datetime

class InsertFormattedDateCommand(sublime_plugin.TextCommand):
    def run(self, edit):
        # Get the current date and time
        now = datetime.now()
        day_of_year = now.strftime('%j')  # Day of the year
        formatted_date = now.strftime(
            f'-------------------------------------------------------------------------------------------------------------------\n'
            f'Day # {day_of_year} %B {now.day} {now.year} - %A\n'
            f'{now.strftime("%Y-%m-%d %H:%M:%S")}\n'
            f'---------------------------------------\n\n\n\n'
            f'-------------/'
        )
        
        # Insert the formatted date at the current cursor position
        for region in self.view.sel():
            if region.empty():
                self.view.insert(edit, region.begin(), formatted_date)
            else:
                self.view.replace(edit, region, formatted_date)

```


2.Save the Plugin:

 - Save this file in your Sublime Text Packages/User directory with a name like insert_formatted_date.py.

3.Create a Key Binding:

 - Go to Preferences > Key Bindings.

 - Add a new key binding entry to call this plugin, like this:


```
[
    { "keys": ["cmd+shift+d"], "command": "insert_formatted_date" }
]

```

How It Works
 
 - Day of Year Calculation: now.strftime('%j') is used to get the day number of the year.

 - Date and Time Formatting: The strftime function is used to format the date and time as specified in your example.

This setup will insert the exact format you need when you press cmd+shift+d in Sublime Text.


