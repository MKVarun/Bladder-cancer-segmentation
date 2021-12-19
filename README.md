# Bladder-cancer-segmentation

## Problem Statement
Ki-67 index is a widely used proliferation index to predict the aggresiveness of cancer. Computing this value is time consuming as pathologists have to manually count the tumour nuclei.
We automate this process by using deep learning to segment immmonupositive (red) and immunonegative (blue) cells. 

## Architecture Details

## Implementation
## Data

## Results
![Result](Segmented_result.png)  

<table>
  <caption align="center">Overall dice and IoU score calculation</caption>
  <thead>
    <tr>
      <th>Dataset</th><th>Loss</th><th colspan=2>Dice</th><th colspan=2>IoU</th>
    </tr>
  </thead>
  <tbody>
    <tr align="center">
      <td></td><td></td><td>With <br/>background</td><td>Without <br/>background</td><td>With <br/>background</td><td>Without <br/>background</td>
    </tr>
    <tr align="center">
      <td>Train</td>
      <td>0.1747</td> <td>0.9741</td> <td>0.9270</td> <td>0.9510</td> <td>0.8702</td>
    </tr>
    <tr align="center">
      <td>Val</td> <td>0.1806</td> <td>0.9717</td> <td>0.9218</td> <td>0.9461</td> <td>0.8614</td>
    </tr>
    <tr align="center">
      <td>Test</td>
      <td>0.1881</td> <td>0.9733</td> <th>0.9203</th> <td>0.9494</td> <th>0.8618</th>
    </tr>
  </tbody>
</table>

<table>
  <caption align="center">Class-averaged dice and IoU score calculation</caption>
  <thead>
    <tr>
      <th>Dataset</th><th>Loss</th><th colspan=2>Dice</th><th colspan=2>IoU</th>
    </tr>
  </thead>
  <tbody>
    <tr align="center">
      <td></td><td></td><td>With <br/>background</td><td>Without <br/>background</td><td>With <br/>background</td><td>Without <br/>background</td>
    </tr>
    <tr align="center">
      <td>Train</td>
      <td>0.1747</td> <td>0.8267</td> <td>0.7552</td> <td>0.7906</td> <td>0.7067</td>
    </tr>
    <tr align="center">
      <td>Val</td> <td>0.1806</td> <td>0.8163</td> <td>0.7333</td> <td>0.7777</td> <td>0.6835</td>
    </tr>
    <tr align="center">
      <td>Test</td>
      <td>0.1881</td> <td>0.8266</t> <th>0.7481</th> <td>0.7896</td> <th>0.7001</th>
    </tr>
  </tbody>
</table>


## System requirements
- Python 3
- Keras >=2.0
- Tensorflow >=2.0
