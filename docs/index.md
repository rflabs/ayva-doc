# Introduction

[Ayva](https://www.refreshlabs.co/ayva) is an open-source cross-platform developer framework used to build voice assistant apps. The features and tools provided in this framework are platform agnostic, allowing developers to build once and deploy on both Google Assistant and Alexa.

## The Voice Application Lifecycle

* A user speaks to a device, like an Alexa or Google Assistant
* The user's voice is converted into text using a speech-to-text
* The text is evaluated against a developer configured __Interaction Model__ by the Natural Languague Understanding (NLU) provider (ie. Alexa, Google, etc.).
  * The NLU provider extracts the user's __intent__
  * ...and possibly some additional input in the form of custom __slots__
* The intent and any additional parameters are passed to the voice application's Intent Execution execution logic. 
  * This is usually through an https webhook request (or direct execution in the case of a serverless architecture)
* The voice application's intent logic is executed with the supplied arguments
*  A response is  returned in SSML (Speech Synthesis Markup Language) format, which allows the device to speak the response to the user
The execution of the intent is largely determined by the specific application being built, but there are a number of common challenges when building voice applications.

## Why did we build Ayva

* NLU providers need the speech model of the application, but do not provide tools for versioning or sharing between developers. When you build on Ayva, your Speech Model is tracked by your version control system.
*  
* Every intent provider (platforms like Alexa and Dialogflow for Google) has a different input format that makes it difficult to manage intent fulfillment from a single codebase
* SSML is unfamiliar to most developers, and does not have tools to keep code clean and accessible.

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs help` - Print this help message.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
