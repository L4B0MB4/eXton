# eXton
Editable eXtendable Text Object Notation --- Save your formatted texts in JSON 

## How it works

Write your code in the eXton-Code-Editor and save it as a .json-file. All your data will be formatted with json tags and will be compatible for every platform that implements the eXton-Standard

## Standard

#### Every eXton-Text section is saved into a json object. This object holds at least a "tag"-property and a "value"-property. The "value"-property is an array, that can contain strings (plain text) or objects. An Array with the length of n can hold n objects. Each of those objects again has to at least hold one "tag" and one "value" property. The tag property can be a string, an object or an array. 

### Example
```javascript 
{
    metadata: {
        name: "My-example-eXton-file",
        //...other data
    },
    tag: "main",
    value:[
        "This is how a string with a ",
        {
            tag: "b"
            value: ["bold "]
        },
        "word would be saved"
    ]
}
```

# Tags that are predefined

+ ## String tags
    + "b"  for bold text
    + "u" for underlined text
    + "i" for italic
    + "s" for striked through
    + "l" left aligned text
    + "c" center aligned text
    + "r" right aligned text

+ ## Object tags
    +   `{
            type:"fontSize",
            value:"21pt"
        }` for fontsize with 21 pt high characters

    +   `{
            type:"nrlist",
            value:"X.Y.Z..."
        }` for numbered list 
    
    +   `{
            type:"list",
            value:"...." // each point -> one tab
        }` for normal tab-list
    
    +   `{
            type:"image"
            value:"imagecontent-base64",
            x: Int,
            y: Int,
            //etc
        }` for images with certain coordinates on the document

    +   `{
            type:"lp",
            value: Int in pt
        }` // line distance in pt