# ツ Subject 
Creating Connect Points plugin.

# ツ Aim and objectives:
<p align="justify">Connects the dots between the two layers using a link field.</p>

# ツ Description:
<p align="justify">I create this plugin while searching for a solution to connect multiple points on the map to a single point. Thanks to this plugin, we can connect the point data we have to the single point data we want to connect, in the desired order. This binding process takes place as follows:</p>
  
<p align="justify">First, the point data to be connected is generated. Later, when we come to the stage of generating the data we want to connect to, we add an attribute such as "link" next to the "id" attribute. This "link" attribute contains the "id" information of the point data we want to connect to. In this way, the points we want are connected according to the "id" information of the point we want. Then, the layer name to be overwritten or created is entered. After the plugin runs, a layer is created if it does not exist and line data is generated. Thus, the dots are connected.</p>

<p align="justify">Another way to use it would be to connect point data with the same "id". This method is what I was trying to do.</p>

# ツ Code explanation:

![1](https://github.com/user-attachments/assets/d27f96f2-b69b-46d4-a82b-3d40d9e94484)

<p align="justify">Initializes the plugin by calling the constructor of the parent QgisPlugin class. Sets the plugin directory, initializes a translator, and initializes some attributes for point layer name, polygon layer name, and field name.</p>

---

![2](https://github.com/user-attachments/assets/3f79ee60-979a-4534-9959-f08bb7a49806)

<p align="justify">Initializes the plugin GUI components, including a toolbar with buttons for connecting points, accessing settings, and viewing information about the plugin.</p>

---

![3](https://github.com/user-attachments/assets/0ca824dc-e371-4137-86a2-a9cc69aa2c78)

<p align="justify">Opens an about dialog displaying information about the plugin.</p>

---

![4](https://github.com/user-attachments/assets/1f6d7855-c126-4c37-9707-84ebe2e23ae0)

<p align="justify">Unloads the plugin by removing toolbar icons and actions.</p>

---

![5](https://github.com/user-attachments/assets/298f8dc0-4e45-49db-a228-ae7974c90e0f)

<p align="justify">Displays a settings dialog to configure plugin parameters.</p>

---

![6](https://github.com/user-attachments/assets/c6423f94-8865-4b95-8167-0736b89b0789)

<p align="justify">Executes the main functionality of the plugin, connecting points based on specified settings. This code is part of the main execution logic of the plugin. It retrieves settings, checks for correctness, handles layers, sets up a worker thread for the main processing logic, and displays a progress dialog during the processing. This plugin is designed for connecting points between two layers and creating a result layer.</p>

---

![7](https://github.com/user-attachments/assets/200d3a1d-ec74-476b-ba95-6348742c95d5)

<p align="justify">Various helper methods for adding fields to a layer, applying styles, adding layers to the project, and showing error messages.</p>

---

![8](https://github.com/user-attachments/assets/467b6b5c-1018-41c9-a884-d0a0422b5310)

<p align="justify">Triggers a repaint to ensure that the changes are reflected in the user interface. The last line, which updates the overview map, is commented out and not executed in the current code.</p>

---

![9](https://github.com/user-attachments/assets/622d3530-0775-4827-8ebf-4d27855a8b1a)

<p align="justify">Initializes a translator for internationalization by loading a translation file based on the user's locale and installing it in the QGIS application. This is a common practice in Qt-based applications to support multiple languages.</p>

# ツ Output:

<p align="justify">Here, I first created the points to be connected. I symbolized the dots in "green". You can also see, I created second attribute that called "link". I created it to show which point it should be connected to.</p>

![10](https://github.com/user-attachments/assets/a080ec78-d60b-4d46-b90d-a3e2aff75a60)

---

<p align="justify">Then, I created the points to connect. I symbolized the dots in "red".</p>

![11](https://github.com/user-attachments/assets/0c501231-0288-4ce1-81c7-2ad535ea8633)

---

<p align="justify">Before the start, we must configure the settings of plugin. We must to set layers.</p>

![12](https://github.com/user-attachments/assets/1ab4f31d-21fc-42fb-83e6-a5dffc2148eb)

---

<p align="justify">Here is my layer names which is setted.</p>

![13](https://github.com/user-attachments/assets/3ea478ac-2d56-4a17-894c-8579ba51e628)

---

<p align="justify">That's it the layer which will be saved after the process. If we do not have the layer which is named we wrote, the plugin could be create instead of you.</p>

![14](https://github.com/user-attachments/assets/ec1840b1-2893-4d31-bf97-679d29a9b54b)

---

<p align="justify">Here is the output. The warning message is about "layer could not find". The plugin created layer for us.</p>

![15](https://github.com/user-attachments/assets/acdda45c-dd00-4d0b-9629-6a062460f087)




