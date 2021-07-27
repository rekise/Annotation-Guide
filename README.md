# Annotation Instructions

<p align="center">
  <a href="#about">About</a> •
  <a href="#labels">Labels</a> •
  <a href="#attributes">Attributes</a> •
  <a href="#exceptions">Exceptions</a> 

   
  
</p>

## About
---

<table>
<tr>
<td>
 
The task is structured to generate **annotated dataset** by succesfully converting _raw image_ data into training dataset for **Rekise's** machine vision model inorder to implement shipping containers detection along with the specification labels associated with the container.

![images](https://drive.google.com/uc?export=view&id=1lj4Wo7g8CzQLu7xDwk43bVOppJjcfrfu)
<p align="right">
<sub>(Preview)</sub>
</p>

</td>
</tr>
</table>

## Labels
<table>
<td>

### Container
---

- Start with creating bounding boxes around the container ships.
- Label entirely around the object with maximum proximity.
   
   
</td>
</table>


|                            |        Correct     |   Misleading    |
| -------------------------- | :----------------: | :-------------: |
| Label  | ![image](https://drive.google.com/uc?export=view&id=1AU8KsLsd0HtgFLUc8-r3qdWrAUD0d30V)                 | ![image](https://drive.google.com/uc?export=view&id=1AvVvvw7GRVV-Wy_2sD4UPLfno9s1gnbJ)               |
|Proximity to the bounding box | ![image](https://drive.google.com/uc?export=view&id=1m4yvUbHYyNRlMK4W9LuU_zVPUwgkOM33)|  ![image](https://drive.google.com/uc?export=view&id=1rEp_YU4pUXtK9ur5M3wcsuxH0u60nX9o)        |
| Box Shape       |   ![image](https://drive.google.com/uc?export=view&id=1sCO-TK7hX9dt8_OE6KcoVjB6tAcwQ2tP)       |    ![image](https://drive.google.com/uc?export=view&id=1slQnpEKEa1VbI_6G1pxYKQxHDiVPlXED)              |
| Overlap  |  ![image](https://drive.google.com/uc?export=view&id=1_eZBF0mbpZWWL1RDQceWb30H7DyQWVUo)                |  ![image](https://drive.google.com/uc?export=view&id=19JB9FBr2CO4yx8s9Pu6WZpjDs66XcjdN)              |
|    |                  |                |

#### Attributes

*Size and Type*

- Input the value associated with size and type label to identify the shipment container.
![image](https://drive.google.com/uc?export=view&id=1DqP7uGYn7XWCi0EQIu2_75Gt1jW8PPo9)


<table>
<td>

### Owner code
---
    The container owner’s code consist of four capital letters, the first three character are the owner prefix and the last character identifies the equipment category.

Code                          |  description
----------------------------------|------------------------------------------------------------------------------------
The owner prefix (BIC code)  |  Three capital letters of the Latin alphabet to indicate the owner or principal operator of the container
The equipment category identifier: |  U for all freight containers,J for detachable freight container-related equipment, Z for trailers and chassis.

![image](https://drive.google.com/uc?export=view&id=1EqBUej8G_ufVOiJAHjy14zYllI3MA3jY)
<p align="left">
<sub>(Example )</sub>
</p>

#### Attributes

- *challenging*
  Mark true if you find it hard to interpret the value associated with the label.
- *legible*
  Mark true if the label is readable and the correct values can be extracted. 
- *value*
  Input the value representing the label.

![image](https://drive.google.com/uc?export=view&id=1dEhf8NnGxgdcCqTWpg9fcbPjM-uH7Zdd)

</td>
</table>

<table>
<td>

### Size and Type
---

Code                         |  description 
----------------------------------|------------------------------------------------------------------------------------
Size  |  The container size is indicated by two alphanumeric characters defining length and height
Type |  The container type and main characteristics is indicated by two characters

![image](https://drive.google.com/uc?export=view&id=1jUN0x6lgQ9gSY_LWfZ970O0pCw2KpGO9)
<p align="left">
<sub>(Example )</sub>
</p>

#### Attributes

- *challenging*
  Mark true if you find it hard to interpret the value associated with the label.
- *legible*
  Mark true if the label is readable and the correct values can be extracted. 
- *value*
  Input the value representing the label.

![image](https://drive.google.com/uc?export=view&id=18dnBuxLZ-uL71L_DnNpLyfzshprBT_HU)
   
</td>
</table>

### Serial number and Check digit
---

Code                         |  description 
----------------------------------|------------------------------------------------------------------------------------
The serial number  |  six Arabic numerals, left at owner‘s or operator‘s option.
The check digit |  one Arabic numeral providing a means of validating the recording and transmission accuracies of the owner code and serial number.

![image](https://drive.google.com/uc?export=view&id=1NaaYgcaS1j0pw0e6XxRKXmUWGkP2D_-s)
<p align="left">
<sub>(Example )</sub>
</p>

#### Attributes

- *challenging*
  Mark true if you find it hard to interpret the value associated with the label.
- *legible*
  Mark true if the label is readable and the correct values can be extracted. 
- *value*
  Input the value representing the label.

![image](https://drive.google.com/uc?export=view&id=1fDROEw-gKmkghHGiMfoqwyeOk1MZjw_i)

   
</td>
</table>

## Exceptions

- For occluded objects - label them entirely.
- label objects that are partially out of frame.
- Input partially distorted or erased value as * in the value attribute field.
  - Example:
  ![image](https://drive.google.com/uc?export=view&id=1-7E3a88jQ6i1yJ0UfrLFy7wNrgAf2xw9)
- Example :
  *The following label for size and type would be considered challenging as the contrast between background and character is too low.*
 ![image](https://drive.google.com/uc?export=view&id=17jMrgh7CXWdLKj_-0XRzlatAKF165Xif)
