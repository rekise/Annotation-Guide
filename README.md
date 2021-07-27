# Annotation Instructions

- [Annotation Instructions](#annotation-instructions)
  - [Introduction](#introduction)
  - [Terminology](#terminology)
    - [Label](#label)
    - [Attribute](#attribute)

- [Jobs](#jobs)
  - [Container](#container)
    - [Size and Type](#size-and-type)
    - [Owner code](#owner-code)
    - [*challenging*](#challenging)
    - [*legible*](#legible)
    - [*value*](#value)
  - [Size and Type](#size-and-type-1)
    - [*challenging*](#challenging-1)
    - [*legible*](#legible-1)
    - [*value*](#value-1)
  - [Serial number and Check digit](#serial-number-and-check-digit)
    - [*challenging*](#challenging-2)
    - [*legible*](#legible-2)
    - [*value*](#value-2)
  - [Frame Issue](#frame-issue)
    - [Adverse Condition](#adverse-condition)
    - [*Dirty lens*](#dirty-lens)
    - [*Fog*](#fog)
    - [*Heavy Rain*](#heavy-rain)
    - [*Heavy Snow*](#heavy-snow)
- [Exceptions](#exceptions)

 Introduction
---

<table>
<tr>
<td>
 
The task is structured to generate **annotated dataset** by succesfully converting _raw image_ data into training dataset for **Rekise's** machine vision model inorder to implement shipping containers detection along with the specification labels associated with the container.

![images](Images/Screenshot (245).png)
<p align="right">
<sub>(Preview)</sub>
</p>

</td>
</tr>
</table>

Terminology
---
  ### Label
  - Labels assign defined category to different components in an image data set. 
  - It correctly identifies the shipment containers along with the associated parameters.

  

    ![images](https://drive.google.com/uc?export=view&id=1Hx3AQZCfdj5Xw0qHGe44u-ddnXJkgZHS)

  ### Attribute
  - Attributes are common quality or characteristics of a labeled category.
  - It consists of properties that define different aspects of the labeled category.
  - It could be the associated value, Size and Type, legibility etc.


  ![images](https://drive.google.com/uc?export=view&id=1E-IOlIXKl4xlAJ8QyOhYjzNV98OiLHSC)

Jobs
---
  ### Container

  - Start with creating bounding boxes around the container.
  - Label entirely around the object with maximum proximity.
    
    



|                            |        Image   |
| -------------------------- | :----------------: | 
| Label only those images where corner fits are clearly visible                                 |    | 
|Correct|![image](https://drive.google.com/uc?export=view&id=1AU8KsLsd0HtgFLUc8-r3qdWrAUD0d30V) |  |     
|Misleading|![image](https://drive.google.com/uc?export=view&id=1AvVvvw7GRVV-Wy_2sD4UPLfno9s1gnbJ)               |
|There should not be a significant gap between the Bounding Box edge and the container edge | |
|Correct|![image](https://drive.google.com/uc?export=view&id=1m4yvUbHYyNRlMK4W9LuU_zVPUwgkOM33)|  
|Misleading|![image](https://drive.google.com/uc?export=view&id=1rEp_YU4pUXtK9ur5M3wcsuxH0u60nX9o)        |
|The Box Shape is required to be a rectangle  |  |
|Correct| ![image](https://drive.google.com/uc?export=view&id=1sCO-TK7hX9dt8_OE6KcoVjB6tAcwQ2tP)|   
|Misleading| ![image](https://drive.google.com/uc?export=view&id=1slQnpEKEa1VbI_6G1pxYKQxHDiVPlXED)              |
| Overlap  | 
|Correct| ![image](https://drive.google.com/uc?export=view&id=1_eZBF0mbpZWWL1RDQceWb30H7DyQWVUo)                | 
|Misleading| ![image](https://drive.google.com/uc?export=view&id=19JB9FBr2CO4yx8s9Pu6WZpjDs66XcjdN)              |
| Container codes with blurring should not be labelled but can be included as a container attribute   | 
|Correct| ![image](https://drive.google.com/uc?export=view&id=1-LBe9lqxylmdgyl5xGDnHPiPKUhFV3tB)                | 
|Misleading| ![image](https://drive.google.com/uc?export=view&id=1DwLu6X_RkP6Eka0LXSHz8sX9ReGD5QGF)              |

|    |                  |                |

#### Size and Type

  - Input the value associated with size and type label to identify the shipment container.
 
    ![image](https://drive.google.com/uc?export=view&id=1DqP7uGYn7XWCi0EQIu2_75Gt1jW8PPo9)


<table>
<td>

 ### Owner code

    The container owner’s code consist of four capital letters, the first three character are the owner prefix and the last character identifies the equipment category.

Code                          |  description
----------------------------------|------------------------------------------------------------------------------------
The owner prefix (BIC code)  |  Three capital letters of the Latin alphabet to indicate the owner or principal operator of the container
The equipment category identifier: |  U for all freight containers,J for detachable freight container-related equipment, Z for trailers and chassis.

![image](https://drive.google.com/uc?export=view&id=1EqBUej8G_ufVOiJAHjy14zYllI3MA3jY)
<p align="left">
<sub>(Example )</sub>
</p>



#### *challenging*
  Mark true if you find it hard to interpret the bounding box associated with the label.
#### *legible*
  Mark true if the label is readable and the correct values can be extracted. 
#### *value*
  Input the value representing the label.

![image](https://drive.google.com/uc?export=view&id=1dEhf8NnGxgdcCqTWpg9fcbPjM-uH7Zdd)

</td>
</table>

<table>
<td>

### Size and Type


Code                         |  description 
----------------------------------|------------------------------------------------------------------------------------
Size  |  The container size is indicated by two alphanumeric characters defining length and height
Type |  The container type and main characteristics is indicated by two characters

![image](https://drive.google.com/uc?export=view&id=1jUN0x6lgQ9gSY_LWfZ970O0pCw2KpGO9)
<p align="left">
<sub>(Example )</sub>
</p>



#### *challenging*
  Mark true if you find it hard to interpret the bounding box associated with the label.
#### *legible*
  Mark true if the label is readable and the correct values can be extracted. 
#### *value*
  Input the value representing the label.

![image](https://drive.google.com/uc?export=view&id=18dnBuxLZ-uL71L_DnNpLyfzshprBT_HU)
   
</td>
</table>

### Serial number and Check digit


Code                         |  description 
----------------------------------|------------------------------------------------------------------------------------
The serial number  |  six Arabic numerals, left at owner‘s or operator‘s option.
The check digit |  one Arabic numeral providing a means of validating the recording and transmission accuracies of the owner code and serial number.

![image](https://drive.google.com/uc?export=view&id=1NaaYgcaS1j0pw0e6XxRKXmUWGkP2D_-s)
<p align="left">
<sub>(Example )</sub>
</p>



#### *challenging*
  Mark true if you find it hard to interpret the bounding box associated with the label.
#### *legible*
  Mark true if the label is readable and the correct values can be extracted. 
#### *value*
  Input the value representing the label.

![image](https://drive.google.com/uc?export=view&id=1fDROEw-gKmkghHGiMfoqwyeOk1MZjw_i)

   
</td>
</table>

### Frame Issue


### Adverse Condition
- Mark the label if any of the following attributes are present in the Image: 
  
  #### *Dirty lens*
  #### *Fog*
  #### *Heavy Rain*
  #### *Heavy Snow*


## Exceptions

- For occluded objects - label them entirely.
- label objects that are partially out of frame.
- Input partially distorted or erased value as * in the value attribute field.
  - Example:
  
  ![image](https://drive.google.com/uc?export=view&id=1-7E3a88jQ6i1yJ0UfrLFy7wNrgAf2xw9)

- Example :
  *The following label for size and type would be considered challenging as the contrast between background and character is too low.*

 ![image](https://drive.google.com/uc?export=view&id=17jMrgh7CXWdLKj_-0XRzlatAKF165Xif)

- The following case with an abundance of container need not be labelled.
  
 ![image](https://drive.google.com/uc?export=view&id=19iHUsuRCCcgWWMKOOg6K-s_GViEjxSgt)

- You can leave distorted and blurred images without marking for OCR labels :
  
  ![image](https://drive.google.com/uc?export=view&id=1tB0uR2gZ5124qduP--kLZEMm30GBuuxE)
