preDicTable
------------
README

Easy Install:
-------------
In a Unix terminal and inside the preDicTable Directory: 

>>> python3 -m venv preDic

>>> source preDic/bin/activate 

>>> pip3 install -r requirements.txt 

>>> python3 preDicTable.py


Contents of preDicTable.zip
---------------------------

i.        README.txt
- Basic overview and use instructions
ii.        SRS.pdf
                        - System Requirements Specifications
iii.         SDS.pdf
- System Design Specifications
iv.         Project_Plan.pdf
- Task and Assignment Breakdown of each member, sorted by time
v.         Installation_Documentation.pdf
- Programmer Documentation and Installation Instructions and User Documentation has been condensed down into this document.
vi.         preDicTable/
- Directory containing the 5 python modules: modeling.py, operations.py, preprocessing.py, transformation.py, visualization.py
and the main python file preDicTable.py
vii.        preDictTable/Tree/
- Contains the 2 transformation tree modules, node.py, tree.py


preDicTable
------------
Transformation Tree program to process and study time series


Environment Requirement
-----------------------
        Python3


Overview
---------
preDicTable simply asks users to pick functionalities from the transformation module. Because this program is still a prototype, users must enter exact numbers or variables for each function. As long as users type the right inputs, this program will not fail.

Rules
-----
Preprocessing operators are expected to be used before modeling and visualization operators, however this is not enforced.


IMPORTANT : The “split_models” operator should be used before the “create_train” operator which should be used before any forecast operators are used. 
The “test_forecast” operator should always be used before the “test_plot” operator.


Make sure that Time Series do not contain any NaN or Infinite Values


Getting Started
---------------
To begin, open preDicTable.py in the terminal.


preDicTable will ask the user to enter ‘0’ to create a new tree or ‘1’ to load an a previously created tree


If ‘0’ is selected, a tree will be initialized after the user enters the file path for the .csv file
NOTE: csv file header should be 1 row in length, and contain no more rows than the data itself.


Main Calls
Once the user has a tree, they will be given actions that can be used by entering their respective number
* 0: Quit - quits the program
* 1: Add - add an operator (see below), or a subtree
* 2: Remove Operator - removes an operator and all its children
* 3: Replace Process - replaces a node
* 4: Execute - executes a pipeline or a tree based on which leaf you choose
* 5: Save/Load - save or load a tree


Operators you can add:
* split_models: splits the time series into 3 sets, and creates a neural network model.
* create_train: creates matrices from the training set and trains the model.
* test_forecast: creates a forecast with the model on the test set
* forecast: creates a forecast with the model at the end of the time series
* test_plot: plots the test_forecast and the test set
* plot: plots the time series and the forecast
for a full list of operators, or more information, check the SDS


Example
--------
        Once you have a tree:
                Enter ‘1’ to add
                Enter ‘0’ to add an operator node (this node will be called ‘2’)
                Enter ‘1’ to add node to the root
                Enter ‘split_models’ to choose it as your operator
                Enter ‘.8, then ‘0’, then ‘.2’ to split the time series into a training and test set
                Enter ‘10 10 10’ to create a model with 3 layers of hidden nodes
                Enter ‘1’ to add
                Enter ‘0’ to add an operator node (this node will be called ‘3’)
                Enter ‘2’ to add node to the previously made node
                Enter ‘create_train’ to choose it as your operator
                Enter ‘10’ for 10 inputs
                Enter ‘10’ for input spacing of 10 (indices)
                Enter ‘1’ for one-step-ahead forecasting
                Enter ‘1’ for one-step-ahead forecasting
                Enter ‘1’ to add 
                Enter ‘0’ to add an operator node (this node will be called ‘4’)
                Enter ‘3’ to add node to the previously made node
                Enter ‘forecast’ to choose it as your operator
                Enter ‘10’ to create 10 sequential forecasts
                Enter ‘1’ to add
                Enter ‘0’ to add an operator node
                Enter ‘4’ to add node to the previous node
                Enter  ‘plot’ to choose it as your operator
                Enter ‘4’ to execute
                Enter ‘1’ to execute a pipeline
                Enter ‘5’ to choose the leaf of the pipeline you want to execute
                -wait for the program to run (may take a while) and you will get a plot-


Result
------
Users must add a visualization node to visualize the result. Because preDicTable is still a beta, its forecast may not be accurate.
