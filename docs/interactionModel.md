## Intent

```
{
    name: string,
    utterances: [string],
    slots: [slot]
    events: [string]
}
```

### Intent Field Descriptions

__name__ (string, required, cross-platform): The name of the intent, spelled as it is in the Ayva Registration (see: Configuring your application)

__utterances__ ([string], optional, cross-platform): Sample phrases that trigger this intent. Optional if one or more events are included. Utterances that contain slots should be formatted according to Utterance-Format-for-Slots_su7YS

__slots__ (Slot Reference, optional, cross-platform): Specifies custom slots used by an intent. See 

__events__ ([string, optional, Dialogflow) : Reference to Dialogflow events, like the default Welcome event triggered on application invocation.



## Utterance

## Slot

_Note: The slot model is an object whose keys are the names of slots referenced in the intent._

```
{
    slot_name : {
        dataType: string,
        isList: boolean,
        required: boolean
    }
    ...
}
```

### Slot Field Descriptions

__slot_name__ (string, required, cross-platform): The name of the slot. See also, Formatting Utterances With Slots

__dataType__ (string, required, cross platform): The entity type of the slot. Entities may be either predefined entity types (see Built in Entity Reference) or custom (see Custom Entity Reference) 

__isList__ (boolean, optional, Dialogflow): Dialogflow allows for slots to contain a list of items. Specifying this field allows Ayva to configure this option in Dialogflow. Defaults to false. Note that list slots fulfilled by Dialogflow will be provided as arrays of values. Other platforms that do not support this feature will provide single values.

__required__ (boolean, optional, cross-platform): 

## Built-in Entity


#### Dialogflow

#### Alexa

## Custom Entity

If your intent requires input that is custom to your application, you can create custom entity types and provide sample input. There are two formats for custom entity types

### List Entity

```
{
    name: string,
    values: [string]
}
```

For example, a custom entity to describe house pets might look like:

```
{
    name: "HousePets", 
    values: ["dog", "cat", "lizard"]
}
```
### List Entity Field Descriptions

__name__ (string, required, cross-platform) : The name of the Entity type
__values__ ([string], required, cross-platform): Sample values for the Entity.
 _Note that this list may be expanded automatically by the NLU provider._

### Complex Entity

```
{
    name: string,
    values: [{
        name: string,
        synonyms: [string]
    }]
}
```

For example, a custom entity to describe sports might look like:
```
{
    name: "Sports",
    values: [
        {
            name: 'Basketball',
            synonyms: ['hoops', 'baskets']
        },
        {
            name: 'Football',
            synonyms: ['American football', 'gridiron football']
        }
    ]
}
```
### Complex Entity Field Descriptions
__name__ (string, required, cross-platform) : The name of the Entity type
__values__ ([object], required): 
    __name__ (string, required, cross-platform): A value of the entity.
    __synonyms__ ([string], optional, cross-platform) : A list of synonyms that will match the value
