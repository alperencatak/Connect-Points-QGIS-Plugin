# ツ Subject 
Creating Connect Points plugin.

# ツ Aim and objectives:
<p align="justify">Connects the dots between the two layers using a link field.</p>

# ツ Description:
<p align="justify">I create this plugin while searching for a solution to connect multiple points on the map to a single point. Thanks to this plugin, we can connect the point data we have to the single point data we want to connect, in the desired order. This binding process takes place as follows:</p>
  
<p align="justify">First, the point data to be connected is generated. Later, when we come to the stage of generating the data we want to connect to, we add an attribute such as "link" next to the "id" attribute. This "link" attribute contains the "id" information of the point data we want to connect to. In this way, the points we want are connected according to the "id" information of the point we want. Then, the layer name to be overwritten or created is entered. After the plugin runs, a layer is created if it does not exist and line data is generated. Thus, the dots are connected.</p>

<p align="justify">Another way to use it would be to connect point data with the same "id". This method is what I was trying to do.</p>

# ツ Code explanation:

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/83612291-b8ac-4eaa-ae7e-87f68a9f4ec7)

<p align="justify">Initializes the plugin by calling the constructor of the parent QgisPlugin class. Sets the plugin directory, initializes a translator, and initializes some attributes for point layer name, polygon layer name, and field name.</p>

---

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/14bf7d71-7c9e-4561-8d91-b34256c40cf7)

<p align="justify">Initializes the plugin GUI components, including a toolbar with buttons for connecting points, accessing settings, and viewing information about the plugin.</p>

---

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/39ef63ee-9e5a-4b94-a4ae-81fcdf86f08c)

<p align="justify">Opens an about dialog displaying information about the plugin.</p>

---

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/2711b60a-f4e6-47f1-bd23-4bcf57076b7a)

<p align="justify">Unloads the plugin by removing toolbar icons and actions.</p>

---

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/c64a0ea2-e269-42c3-a027-c271a4d1ec0a)

<p align="justify">Displays a settings dialog to configure plugin parameters.</p>

---

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/b75a4d85-ef55-475c-bd0e-1e1b7e68c074)

<p align="justify">Executes the main functionality of the plugin, connecting points based on specified settings. This code is part of the main execution logic of the plugin. It retrieves settings, checks for correctness, handles layers, sets up a worker thread for the main processing logic, and displays a progress dialog during the processing. This plugin is designed for connecting points between two layers and creating a result layer.</p>

---

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/c4d425ec-c7ef-42e3-97d6-d965e8bee846)

<p align="justify">Various helper methods for adding fields to a layer, applying styles, adding layers to the project, and showing error messages.</p>

---

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/3bd46178-69fd-48e8-8ff5-307ba0a2d242)

<p align="justify">Triggers a repaint to ensure that the changes are reflected in the user interface. The last line, which updates the overview map, is commented out and not executed in the current code.</p>

---

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/c45262a0-8f3c-4cc4-9a7c-5ac65d94d203)

<p align="justify">Initializes a translator for internationalization by loading a translation file based on the user's locale and installing it in the QGIS application. This is a common practice in Qt-based applications to support multiple languages.</p>

# ツ Output:

<p align="justify">Here, I first created the points to be connected. I symbolized the dots in "green". You can also see, I created second attribute that called "link". I created it to show which point it should be connected to.</p>

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/c7d79ae9-9cca-4a1c-bf39-e0cad25943e4)

---

<p align="justify">Then, I created the points to connect. I symbolized the dots in "red".</p>

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/23e2d961-2559-49da-b512-5ec60d9a9729)

---

<p align="justify">Before the start, we must configure the settings of plugin. We must to set layers.</p>

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/fe3080e1-9de3-482a-8192-2cb87989eaed)

---

<p align="justify">Here is my layer names which is setted.</p>

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/179fe665-f72e-4542-8be5-cca3121ad4b0)

---

<p align="justify">That's it the layer which will be saved after the process. If we do not have the layer which is named we wrote, the plugin could be create instead of you.</p>

![Adsız](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/2999342e-89a5-4e1b-a561-10b66cc26bcc)

---

<p align="justify">Here is the output. The warning message is about "layer could not find". The plugin created layer for us.</p>

![image](https://github.com/GMT-456-GIS-Programming/final-project-alperencatak/assets/118128475/cb6eb479-f455-4c62-a610-348becac5a8b)




