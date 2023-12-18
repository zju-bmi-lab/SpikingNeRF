# Spiking-NeRF

## Abstract
A crucial reason for the success of existing NeRF-based methods is to build a neural density field for the geometry representation via multiple perceptron layers (MLPs).
MLPs are continuous functions, however, real geometry or density field is frequently discontinuous at the interface between the air and the surface.
Such a contrary brings the problem of unfaithful geometry representation.
To this end, this paper proposes spiking NeRF, which leverages spiking neurons and a hybrid Artificial Neural Network (ANN)-Spiking Neural Network (SNN) framework to build a discontinuous density field for faithful geometry representation. Specifically, we first demonstrate the reason why continuous density fields will bring inaccuracy.
Then, we propose to use the spiking neurons to build a discontinuous density field.
We conduct a comprehensive analysis for the problem of existing spiking neuron models and then provide the numerical relationship between the parameter of the spiking neuron and the theoretical accuracy of geometry.
Based on this, we propose a bounded spiking neuron to build the discontinuous density field.
## Usage

#### Data Convention
The data is organized as follows:

```
<case_name>
|-- cameras_xxx.npz    # camera parameters
|-- image
    |-- 000.png        # target image for each view
    |-- 001.png
    ...
|-- mask
    |-- 000.png        # target mask each view (For unmasked setting, set all pixels as 255)
    |-- 001.png
    ...
```

### Setup

Clone this repository

```shell
pip install -r requirements.txt
```

### Running

- **Training DTU**

```shell 
python exp_runner.py --mode train --conf ./confs/womask.conf --case <case_name>
```

- **Training Blender**

```shell 
python nerf_vth2.py --config ./config/xx.txt 
```
