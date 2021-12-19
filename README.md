# Bladder-cancer-segmentation

## Problem Statement
Ki-67 index is a widely used proliferation index to predict the aggresiveness of cancer. Computing this value is time consuming as pathologists have to manually count the tumour nuclei.
We automate this process by using deep learning to segment immmonupositive (red) and immunonegative (blue) cells. 

## Architecture Details

## Implementation
### Data
- Ten non-overlapping images corresponding to 8 patients of resolution 1920 x 1440 pixels were cropped from the whole slide images.
- A total of 80 images of 1920 x 1440 pixels were available. Each image was divided into 60 patches of size 512 x 512 pixels. Horizontal shift: 128 pixels, Vertical shift: 232 pixels
- Hence, the dataset consisted of a total of 4800 images for training and testing out of which 1200 images were used for training, 200 images for validation and 3400 images for testing
- The ground truth images were prepared by manual annotations with the guidance of an expert pathologist. Ki-67 positive nuclei were marked red while negative tumor nuclei were marked blue and the background were marked white.
- All the data were collected from the Department of Pathology at Kasturba Medical College (KMC), Mangalore

### Mobile-Unet Model
![UNet](Unet.png)
We implemented the Mobile-Unet model which replaces the convolutional layers of the standard U-Net model with separable convolutions. This reduces the number of parameters as well as the required computations. The model performed a three class segmentation with a total parameters of 2.67M trainable parameters. The model was trained for a total of 50 epochs with categorical cross entropy as loss and Adam optimizer with initial learning rate set to 0.0001. The model was trained on a Tesla P100-PCIE-16GB GPU.

### Evaluation metrics
#### Dice score
The overall dice score and class averaged dice scores were evaluated for the model
#### IoU score
The overall IoU score and class averaged IoU scores were evaluated for the model
## Results

<table align="center">
  
  <p align="center"><b>Evaluation Metrics</b></p>
  <thead>
    <tr>
      <th>Dataset</th><th>Loss</th><th colspan=2>Overall Dice</th><th colspan=2>Overall IoU</th><th colspan=2>Class-averaged dice</th><th colspan=2>Class averaged IoU</th>
    </tr>
  </thead>
  <tbody>
    <tr align="center">
      <td></td><td></td><td>With <br/>background</td><td>Without <br/>background</td><td>With <br/>background</td><td>Without <br/>background</td>
      <td>With <br/>background</td><td>Without <br/>background</td><td>With <br/>background</td><td>Without <br/>background</td>
    </tr>
    <tr align="center">
      <td>Train</td>
      <td>0.1747</td> <td>0.9741</td> <td>0.9270</td> <td>0.9510</td> <td>0.8702</td>
      <td>0.8267</td> <td>0.7552</td> <td>0.7906</td> <td>0.7067</td>
    </tr>
    <tr align="center">
      <td>Val</td> <td>0.1806</td> <td>0.9717</td> <td>0.9218</td> <td>0.9461</td> <td>0.8614</td> 
      <td>0.8163</td> <td>0.7333</td> <td>0.7777</td> <td>0.6835</td>
    </tr>
    <tr align="center">
      <td>Test</td>
      <td>0.1881</td> <td>0.9733</td> <th>0.9203</th> <td>0.9494</td> <th>0.8618</th>
      <td>0.8266</t> <th>0.7481</th> <td>0.7896</td> <th>0.7001</th>
    </tr>
  </tbody>
</table>

<p align="center"><b>Segmented Result</b></p>

![Segmented Result](Segmented_result.png)  

## System requirements
- Python 3
- Keras >=2.0
- Tensorflow >=2.0
