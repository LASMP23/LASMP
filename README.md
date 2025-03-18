# LASMP highlights
### The workflow diagram of LASMP
![Workflow](Figures/workflow.png)

There are two key modules in LASMP
- Custom NER model
- Sample efficient path planner

## Custom NER Model
In this work we used NER model for extracting the navigational entities, such as, left, right etc or zone entities such as, bedroom, kitchen. The zone entity associated with variaous indoor locations of building. We used transformer-based model RoBerta for the custom NER task. The output of the NER task is either the combination of turn-list and destination or it could be destination only. For the prior, the coordinates of the identified destination are retrieved from a predefined look-up table. If only the destination is outputted from the NER then the associated turns are obtained through a pre-trained feedforward network (blue-shaded sub-module in the above figure which maps the concatenated vector consisting of the coordinates of the robot's current position and coordinates of the destination to a class associated with a specific turn list. For our implementation, the network is trained for classifying a maximum of four turns which is sufficient for many indoor environments. However with appropriate data, the network can be easily trained to output turn-list with more turns.

## Sample efficient path planner
details about the planner.

## Simulation Results

## Experimental Results
