# Bladder-cancer-segmentation

## Problem Statement
Ki-67 index is a widely used proliferation index to predict the aggresiveness of cancer. Computing this value is time consuming as pathologists have to manually count the tumour nuclei.
We automate this process by using deep learning to segment immmonupositive (red) and immunonegative (blue) cells. 

## Architecture Details

## Implementation
## Data

## Results
![Result](Segmented_result.png)  

|Dataset|Loss|Dice<colspan=2>||IoU<colspan=2>||
|-----|-----|-----|-----|-----|-----|
|||With background|Without background|With background|Without background|
|Train	|0.1747	|0.9741	|0.9270	|0.9510	|0.8702|
|Val	|0.1806	|0.9717	|0.9218	|0.9461	|0.8614|
|Test	|0.1881	|0.9733	|0.9203	|0.9494	|0.8618|

## System requirements
- Python 3
- Keras >=2.0
- Tensorflow >=2.0
