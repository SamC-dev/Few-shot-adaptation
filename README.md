# Few-shot-adaptation
The study offers an implementation of both context optimization (CoOp) and conditional context optimization (CoCoOp) on top of OpenAI's Clip model. 
The focus was on improving the zero shot performance of Clip (Vit-B/16) on base classes while retaining or improving the accuracy on novel classes, working on the "OxfordFlowers102" dataset, containing a list of 102 classes of flowers.

The file "Report.ipynb" works as a self contained jupyer notebook, which is suggested to be run in colab. 
The file is divided into two parts, with the first containing the details of the implementations and the second the formalization and run of the experiments.

The experiments can be categorized as follows:
- Optimization algortihm choice (SGD vs. ADAM).
- CoOp with csc implementation.
- Augmentation strategy.
- Ensemble strategies.

The results outperformed the state of the art in both base and novel classes accuracy.

### Usage
1. Run the notebook in colab
2. All the experiments can be reproduced by modifying the parameters when calling the function:

```main(run_name="CoOP", use_cocoop=3, loaded_clip_model=model, precision="fp32", augmentation=True, optimizer = "ADAM")```

parameters setting:
- use_cocoop [1 = CoOp, 2 = CoCoOp, 3 = csc style CoOP]
- augmentation: bool
- optimizer [SGD, ADAM]
- ensemble: None by default [e, m]

some experiments in the ensemble section require you to change patience, batch size and weight decay.

You can find more details inside the report.
