# A1

**Group number:** 3  
**Focus area:** Architecture 

## Identified issues
### 1:
**Area:** Architecture / Indoor & energy.  
**Issue type:** Design / Model issue.  
**Affected systems:** Space, Service and Build systems.  
**IFC classification:** IfcDistributionElement (5.4.3.16).  
**Source:** Client report 26-01-A, page 15 (16/22 in the PDF available on Learn).

The group is proposing a renovation where multiple walls and spaces are demolished and reconstructed (even bathrooms are repositioned) but at the same time they say MEP elements are to be reused and kept in the same position as they were in originally. No information is given on where the MEP elements are currently positioned, which makes it impossible to validate whether or not the construction of this new room layout is possible.


### 2:
**Area:** Architecture  
**Issue type:** Design issue  
**Affected systems:** Space, Structure and Build systems.  
**IFC classification:** IfcSpace (5.4.3.64)  
**Source:** Client report 26-02-A, pages 5-8.

The report does not provide drawings or models showing anything from the existing building, only the proposed new floorplan. Without knowing what the original floorplan looks like it's difficult to understand exactly which elements are kept and which are changed. This ultimately makes it more difficult to determine what departments are affected by the renovations, and the overall extent of the project.



### 3:
**Area:** Materials / LCA  
**Issue type:** Tool issue  
**Affected systems:** Materials  
**IFC classification:** The group starts by selecting *IfcSlab (6.1.3.35)* in their script, but it concerns *IfcMaterial (8.10.3.1)*.  
**Source:** [2434: How to identify co2 emissions from flooring in a building](https://github.com/Emiliefoged/analyst34/blob/main/A3/README.md)

The tool is using fixed CO2 emission factors that are written directly into the script. These emission factors are subjected to change seeing as they are dependant on environmental data, production methods, transport assumptions etc. which all can experience changes over time due to new procedures or findings. If the emission factors are updated in the LCA database the tool does not automatically update as well. This increases the risk of using outdated values without the user knowing, or increases the amount of work needed to keep the tool up to date.



### 4: 
**Area:** Architecture / Build-Cost.
**Issue type:**   Tool issue.
**Affected systems:**  Build.
**IFC classification:**  IfcCostItem.
**Source:** 
[2542: Rapid IFC-Based Architectural Cost Estimator].
The tool is used to estimate costs by a given price in m², this issue requires constant update of the user, it could be leveraged more if it were to access real time data from internet, allowing interoperability between various locations by a web scrapping tool..


### 5: FILL OUT
**Area:** 
**Issue type:**   
**Affected systems:**  
**IFC classification:**  
**Source:** 



## Possible solutions
### 1:
A drawing over the existing MEP systems should be taken into use, and compared to the current and proposed layouts of the building. Depending on the results, and the client's wishes, a new approach would be either:
- adjusting the new floorplan to accomodate the existing MEP systems.
- repositioning the existing MEP systems to accomodate the new floorplan.

A way of doing this could be by updating the IFC model with the new floorplan, while keeping the MEP systems where they are currently situated. Possible clashes or problems could then easily be identified and taken care of.


### 2:
A drawing or model showing the existing building should be included, and more information should be given on what changes are proposed to make it easier to understand the overall scale of the renovation. Items to help this would include:
- all existing elements that will be retained, demolished, or removed
- Existing and proposed room function
- areas that are included and/or exclude from the renovation scope

### 3:
The CO2 emission factors should be separated from the main script and connected directly to an LCA database, so that the emission factors can be updated automatically. Alternativaly, they could be stored in a separate database, making a manual update less complicated.


### 4:
Inputting a manual value every time the tool is needed, can lead to misinformation of costs and also limiting the Ifc file possibilities. By a web scrapping tool, it can be used to actually foresee different costs and also allow relocation of project into anywhere the local web data is available. Our suggestion would be using the space separation system of using capitals in between words to actually separate them and doing web search of these key words on the internet by a web scrapping tool and a zip code of the construction site, allowing to use real life suppliers and cost estimation.

### 5:
