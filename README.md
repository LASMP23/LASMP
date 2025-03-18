# LASMP highlights
### The workflow diagram of LASMP
![Workflow](Figures/workflow.png)

There are two key modules in LASMP
- Custom NER model
- Sample efficient path planner

## Custom NER Model
In this work, we used a Named Entity Recognition (NER) model to extract navigational entities, such as left, right, etc., and zone entities, such as bedroom, kitchen. The zone entities are associated with various indoor locations within a building. We employed a transformer-based language model, RoBERTa, for the custom NER task. The output of the NER task is either a combination of a turn-list and destination, or it could be just the destination. For the former, the coordinates of the identified destination are retrieved from a predefined lookup table. If only the destination is outputted by the NER model, the associated turns are obtained through a pre-trained feedforward network (the blue-shaded sub-module in the figure above). This network maps the concatenated vector, consisting of the robot's current position coordinates and the destination coordinates, to a class associated with a specific turn list.

The instruction can be provided in two modalities: text messages or voice commands. When the instruction is in the form of a text message, no additional processing is required. The text is directly input into the NER model for entity extraction. In contrast, if the instruction is provided as a voice command, an additional step is needed before it can be processed by the NER pipeline. In this case, the voice command is transcribed into text using the transformer-based model Whisper (as shown in section B of the figure above), which performs Automatic Speech Recognition (ASR) to convert the spoken input into text. This multi-modal system enables the processing of both textual and spoken instructions, allowing for flexible interaction depending on the input format.

## Sample efficient path planner
details about the planner.

## Simulation Results

## Experimental Results
