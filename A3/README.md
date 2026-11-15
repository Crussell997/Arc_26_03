# A3: Revit to Blender (Bonsai) and back again.

## About the tutorial

This tutorial shows how to export a Revit model to IFC, open and inspect it in Blender with Bonsai, add classification information, save the edited IFC file, and link a model back into Revit.

The purpose is to introduce a simple OpenBIM workflow and show how IFC can be used as the connection between different BIM environments.

## Target role and learning level

The tutorial mainly targets **R1: OpenBIM Modeller – Level 2**.

The user works directly with an IFC model in Bonsai, inspects IFC information, edits model information, and works with classification information.

## Focus area and BIM use

- **Focus area:** Architecture
- **BIM use:** Design Authoring

The tutorial is designed for students and focuses on model elements such as walls, doors, windows, spaces, and their IFC information.


## Required software

Before starting the tutorial, make sure you have:

- **Revit**
- **Blender**
- **Bonsai extension**

You also need an architectural Revit model that can be exported to IFC.


---
# Instructions to run the tool

## 1. Export a Revit model to IFC

1. Open the architectural model in **Revit**.
2. Go to **File → Export → IFC**.

![Revit save as IFC](IMG\Revit_save_as_IFC_full_screen.jpeg)

3. Choose where the IFC file should be saved.
4. Give the file a name, for example: **Architecture_model.ifc**


5. Select the IFC export setup you want to use.
6. Click **Export**.

The Revit model is now saved as an IFC file that can be opened in other IFC-compatible BIM software. In this tutorial we will use Blender.


## 2. Install Bonsai in Blender

Before you can open the IFC model in Blender, you have to make sure Bonsai is installed.

1. Open Blender.
2. Go to **Edit → Preferences**.
3. Open **Get Extensions**.
4. Search for **Bonsai**.
5. Install the Bonsai extension.
![Install bonsai](IMG\Blender_get_Bonsai.jpeg)

When Bonsai is installed, Blender will contain IFC-specific tools such as **Open IFC Project**.



## 3. Open the IFC downloaded from Revit in Bonsai

1. Open Blender.
2. Go to **File → Open IFC Project**.
![Blender open IFC](IMG\Blender_open_IFC.jpeg)
3. Select the IFC file exported from Revit.

The Revit model should now be visible in the Blender viewport.

Before inspecting individual objects, first look at how the IFC model is structured.

Go to:

**Project Overview → Spatial Decomposition**

Here you can see how the model is organised into different IFC levels. A simplified structure may look like this:

```text
IfcProject
└── IfcSite
    └── IfcBuilding
        └── IfcBuildingStorey
            ├── IfcWall
            ├── IfcDoor
            ├── IfcWindow
            └── IfcSpace
```



Expand the hierarchy and locate one of the building storeys and select an element that belongs to that storey.

## 4. Inspect the IFC information of an object

Now that the overall IFC structure is clear, you can inspect the information connected to individual objects.

1. Select an element in the model, for example a door as shown below.
![IFC levels w door](IMG\Blender_IFC_levels_with_door.jpeg)
2. Open **Object Information** in the properties panel.
3. Check which IFC class the selected object belongs to.


The Object Information panel can also contain information such as:

- Name
- Global ID
- Object type
- Property sets
- Spatial container
- Classification references

This information can be read or edited.

## 5. Add classification information to the IFC object

An object already has an IFC class, such as **IfcWall** or **IfcDoor**. A classification reference can add another layer of information by connecting the object to an external classification system.

Examples of classification systems include:


- CCS
- Uniclass
- OmniClass


First, select an IFC object and return to **Object Information**.

Scroll down to:

**Classification References**

If no classification is assigned, a classification system must first be loaded into the IFC project.

To load a classification:

1. Go to **Project Overview → Project Setup → Classifications**.
2. Click **Add Classification**.
3. Select the classification library you want to use.
4. Load the classification into the project.

If you need to locate the classification files used by Bonsai, go to:

**Edit → Preferences → Add-ons → Bonsai → Schema Directory**

After the classification system has been loaded:

1. Select the IFC object again.
2. Open **Object Information → Classification References**.
3. Add a classification reference.
4. Choose the appropriate classification code for the object.

![Blender classification](IMG\Blender_classification.jpeg)


## 6. Save the edited IFC project

After adding or editing information in Bonsai, you can save the IFC project.

Go to:

**File → Save IFC Project**

Give the file an appropriate name, for example: **Architecture_model_classified.ifc**

## 7. Link the IFC back into Revit

The saved IFC project can now be linked back into Revit.

1. Open **Revit**.
2. Open the original Revit project.
3. Go to **Insert → Link IFC**.
![Link IFC](IMG\Revit_link_IFC.jpeg)
4. Select the IFC file.
5. Select the appropriate positioning method.
6. Open the IFC link.

The IFC file should now appear in Revit as a linked IFC model.

Check that:

- the model is positioned correctly.
- the model geometry is still visible.
- the linked IFC corresponds to the same model exported at the beginning.


# Summary

This tutorial shows how to export a Revit model to IFC, open and inspect it in Blender with Bonsai, add classification information, save the edited IFC file, and link a model back into Revit.