## CLI Commmand Reference

### Overview
The Ayva CLI is a tool to help with cross platform development and deployment tasks when building an application on the Ayva Framework using Nodejs.

### Command Descriptions

Note: Commands should be run in the same directory as your project's ayva.json file, or you can supply an optional path parameter to direct the CLI to the project's ayva.json file.

* `ayva hello [path]`- Clones and initializes the Ayva Hello World project. Built to be used alongside the Ayva Hello World Tutorial. Takes an optional path argument to clone into a specific directory.
* `ayva create [path]` - Creates a skeleton Ayva application. Takes a required path argument, which is used as the default name of the project.
* `ayva deploy [path] [-d | ーdialogflow] [-a | ーalexa]` - Command to upload local Ayva Speech Model to voice platforms. By default, the command will attempt to upload to any platforms configured by the project, as definied in the ayva.json configuration file. This can be overridden by specifying a particular platform using `--dialogflow` for DialogflowV1 and `--alexa` for Alexa. Takes an optional path argument to your ayva.json directory.
* `ayva init [path]` - Creates the required Ayva config files - ayva.json and speechModel.js - in the current directory, or directory supplied by the optional path argument. This command will also configure a new NLU provider (like Alexa and Google) in an existing project.
