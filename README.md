# Tools-2
 
Name: Jarrod Hasnain
Student ID: jhasnain
Student Number: 251094944

Class: COMPSCI 4482
Assignment: Tools 2

The Demo:
 - Run the game
 - Click "Load Content" in order to load all the localization content into the game
 - Double click the desired language to switch to that language
 - Click the "Next" button to continue reading the story
 - The bottom text displays the current language
 - Teaser for App 3 project :)

The Tool:
 - Uses Unity's Editor Window and scriptable objects to create language settings
 - 2 windows: One for adding and editing languages, one for adding and editing text and translations
 - Store's all data in scriptable objects automatically

How to use:
 - In order to use the tool, select the "Tools" tab at the top of the window, then follow the dropdown to select the "LocalizationTool"
 - There will be 2 options, one for editing the data and another for loading/unloading the data.
    - The loading and unloading option is more for debugging purposes in order to refresh the data and view it in the editor
 - To edit the languages, select "Data Editor" > "Languages List"
    - This will present the user with an Editor Window where they can select a language, change it's name, tag, add languages and/or delete them. All very user friendly
 - To edit the localization data, select "Data Editor" > "Localization Data"
    - This will present the user with an Editor Window where they can select a text option, change that options data for all languages available. They can also choose to add a new text, delete a text option and/or edit an existing option they select from a dropdown list.

How it works:
 - Scriptable Objects:
    - 2 C# scripts were made, one for the languages and another for the data.
    - Within the languages script, there are 2 objects, one for the list of all languages, and another for the language itself. This script contains 2 sets of linked scriptable objects.
    - Within the data script, it simply stores a list of fields for each language. All languages will have the same number of fields, and each field will have it's correct corresponding index.
 - Editors:
    - 3 C# scripts made, one for a parent class that inherits all the properties of Unity's Editor Window, and 2 children of that class, one for the languages window, and another for the data window.
    - The LocalizationEditor script contains all the functions that will be used in the editor windows to create, edit and store data.
    - The other 2 scripts specify the data for their specific uses.
    - Essentially, the editors contain the data for what will happen when each button is clicked. Most of these functions involves accessing the resources folder where the scriptable objects are stored and either creating new objects, deleting objects and/or their data, and editing data (done through deleting current data and replacing it with the updated data).
    - The LocalizationEditor script also contains functions for when the tabs are selected from the Unity window's Tools tab.
 - The text and language:
    - The text stores values pertaining to the field index, the text object and set properties for updating the values of the text when the language is changed.
    - The important part is the field index. This will call the same index and read from whichever language is currently the active language (set with the LocalizationSettings object).
    - This index can also be updated to change a text from one thing to another (this is how the story advances by clicking the next button).
    - The "LanguageToggle" script will update the current language the system is in. This object is also referenced by all localized text as it stores the system's current language state. This is how the language is known by all the text objects.
 - The rest:
    - The rest of the scripts are mostly for the functionality of the demo itself.