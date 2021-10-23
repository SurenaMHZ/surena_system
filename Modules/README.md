# Modules:
For the evolution of Surena system and the ability of professional personalization, there is the ability to use codes, fonts, themes, etc. in the third person, which are called modules.
Modules are divided into four main categories
#### 1. Plugins
####2.Themes
####3. Languages
####4. Fonts
#### Plugins:
There are codes for the panel that are used to evolve the panel and provide more capabilities to the user.
Plugins in two categories:
1. **Object**: Plugins that do not have a user interface in the panel and can only be used in the api
2. **World**: Plugins that have both a user interface in the panel and can function in the api

#### themes:
There are modules that can be used to change and customize the user interface
#### languages:
There are modules that change the system language in the user interface and background
#### Fonts:
There are modules that change the font of the system interface surena panel

### Module structure:
 As you have read. Modules are divided into different categories and, as expected, have different structures, but some of these structures are the same.
 These “**Information.json**” All modules have a file called
This file introduces the module to the Surena system and has a Json structure
This file is present in all modules and its structure varies depending on the type of module, but some structures are the same, such as
```json
{
    "Module_Name": "test",
    "Module_Version": "1.0.0",
    "Module_Type": "object",
    "Module_Github":"http://",
    "Module_Description":"for test",
    "Module_Manufacturer_Name":"surena",
    "Module_Manufacturer_Web":"http://",
    "Module_Manufacturer_Gmail":"example@gmail.com"
}
```
**Module_Name***. is the name of the module, which must be carefully named to be unique and unique to install and work alongside other modules without causing problems.

**Module_Version***. is a module version that can be changed in various updates

**Module_Type***. is the type of module that we have already introduced and divided into four main categories, and for the type of module we can use the following parameters:

    Object  -or object
    World –or world
    Language –or language –or Lan –or lan
    Theme –or theme
    Font –or font
**Module_Github**. There is a module link in GitHub where documents or anything can be placed
**Module_Description**. Module description
**Module_Manufacturer_Name**. The name of the module builder
**Module_Manufacturer_Web**. The link to the site or blog is the builder of the module
**Module_Manufacturer_Gmail**. Electronic address of the module manufacturer
In the continuation of the file “**Information.json**” according to the type of module, it completes its structure
#### Plugins:
```json
{
"Module_Require_files":["test1.php","test2.php"]
}
```
Names of files used in the plugin and retrieved (does not include the default files that must be present for the module)

Plugins (**object** and **world**) both have a file called “**action.php**” this file has the things it can do in the background and the relevant codes are placed in this file as a class, and according to this file, the file structure evolves “**Information.json**”
Consider the following example:

“**action.php**”
```php
<?php
class Module_Name{
    public function action1($name,$f){
        echo $name." test1";
    }
    public function action2($name,$f){
        echo $name." test2";
    }
}
?>
```
“**Information.json**”
```json
    "Module_Actions":[
        {"name":"action1",
            "des":"for test1",
        "params":[
            {"name":"name","type":"string","des":"test"},
            {"name":"family","type":"string","des":"test"}
        ]},
        {"name":"action2",
            "des":"for test1",
        "params":[
            {"name":"name","type":"string","des":"test"},
            {"name":"family","type":"string","des":"test"}
        ]}
    ]
```
The “**Module_Actions**” is an array that contains the names of the actions and the description of the action function and the name of the action parameters and the description and type of the parameter.
For example, for Action 1, we do the following
```php
        {
		"name":"action1",
            "des":"for test1",
        "params":[
            {"name":"name","type":"string","des":"test"},
            {"name":"family","type":"string","des":"test"}
        ]
		}
```
**name**. There is an action name that must be the same as the action name in the file “action.php”
**des**. Action description
**params**. Action input parameters
**params**.**name**.Name the parameter
**params**.**type**.Parameter type
**params**.**des** Explain the parameter
Finally, our file structure “Information.json” is as follows:
```json
{
    "Module_Name": "test",
    "Module_Version": "1.0.0",
    "Module_Type": "object",
    "Module_Github":"http://",
    "Module_Description":"for test",
    "Module_Manufacturer_Name":"surena",
    "Module_Manufacturer_Web":"http://",
    "Module_Manufacturer_Gmail":"example@gmail.com",
    "Module_Require_files":["test1.php","test2.php"],
    "Module_Actions":[
        {"name":"action1",
            "des":"for test1",
        "params":[
            {"name":"name","type":"string","des":"test"},
            {"name":"family","type":"string","des":"test"}
        ]},
        {"name":"action2",
            "des":"for test1",
        "params":[
            {"name":"name","type":"string","des":"test"},
            {"name":"family","type":"string","des":"test"}
        ]}
    ]
}
```
And the file structure of our module is as follows
Information.json
```
action.php
test1.php
Test2.php
```
Above is an example for the plugin with explanations that this is the same structure between the two types of plugins (**object** and **world**), but if our plugin type was global, another file must be added to the plugin called “**index.php**” Module user interface codes are written for the panel, which should be referenced using CSS for beautification.

#### languages:
Has a file “**Language.php**”
Where is the reference and patterning of the reference language file. A new language is being written
Consider the following example:
```php
<?php
    /* 
    ***---------------------***
    ***| Language: English |***
    ***---------------------***
    */
    ///Language (Selected language)
    $lang['Language'] = "en";
    /// Login
    $lang['login_title'] = "Login to admin panel";
    $lang['email'] = "Email";
    $lang['email_or_username'] = "Email or UserName";
    $lang['password'] = "Password";
    $lang['login'] = "Login";
    $lang['lost_password'] = "Forget your password?";
    $lang['login_failed'] =  "Email or password incorrect";
?>
```
The example above is part of the structure of the reference language file, and we want to create a German language for the system, for example, so we do the following:
```php
<?php
    /* 
    ***---------------------***
    ***| Language: German language |***
    ***---------------------***
    */
    ///Language (Selected language)
    $lang['Language'] = "ger";
    /// Login
    $lang['login_title'] = " Melden Sie sich im Admin-Panel an";
    $lang['email'] = "Email";
    $lang['email_or_username'] = "E-Mail Adresse oder Benutzername";
    $lang['password'] = "Passwort";
    $lang['login'] = " Anmeldung ";
    $lang['lost_password'] = " Passwort vergessen?";
    $lang['login_failed'] =  " E-Mail oder Passwort falsch ";
?>
```
And finally the file structure “Information.json” we get as follows
```json
{
    "Module_Name": " German",
    "Module_Version": "1.0.0",
    "Module_Type": "lan",
    "Module_Github":"http://",
    "Module_Description":" German language  ",
    "Module_Manufacturer_Name":"surena",
    "Module_Manufacturer_Web":"http://",
    "Module_Manufacturer_Gmail":"example@gmail.com"
}
```
And the file structure of our module is as follows
```
    Information.json
     Language.php
```
#### themes:
Has a file called Theme.css
Are where the CSS codes are defined according to the pattern of the reference CSS file
And finally the file structure “**Information.json**” we get as follows
```json
{
    "Module_Name": "dark",
    "Module_Version": "1.0.0",
    "Module_Type": "theme",
    "Module_Github":"http://",
    "Module_Description":"dark theme",
    "Module_Manufacturer_Name":"surena",
    "Module_Manufacturer_Web":"http://",
    "Module_Manufacturer_Gmail":"example@gmail.com"
}
```
And the file structure of our module is as follows
   ```
   Information.json
    Theme.css	
	```
#### Fonts:
```json
{
"Font_Type":"OTF"
}
```
There is a type of font that has two categories
```
TTF
OTF```
And has a file
```font.ttf```
This is a font file

> Note that in the file“**Information.json**” the font type must be uppercase and the file extension must be lowercase

### Attention:
> ** The names of all system files that must be inside the module must be named as mentioned here (their names should not be uppercase and lowercase) **

##### Finally, to publish the module, we need to convert all the relevant files to a “zip” file, then the file extension to ”ssm”which stands for“surena system module”is converting.
