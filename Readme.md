# Tool Tracking Dataset - Supplement Code

Dataset description: https://cmutschler.de/datasets/tool-tracking-dataset 

## In order to get things running:

1. Clone the repository

```
git clone https://github.com/crispchris/tool-tracking.git
# forked from mutschcr/tool-tracking.git
cd tool-tracking
```

2. Then you need to download the measurement data from an external host:
```
# updated link to mirror (Feb. 12, 2025)
wget https://christofferloeffler.com/tooltracking/tool-tracking-data.zip -O tool-tracking-data.zip
unzip tool-tracking-data.zip && rm tool-tracking-data.zip

# deprecated link: wget https://owncloud.fraunhofer.de/index.php/s/MQUpf2vhIghAtke/download -O tool-tracking-data.zip
```

3. Setup a virtual python environment (e.g. with [conda](https://www.anaconda.com/))
```
conda create --name tool-tracking_env python=3.12
conda activate tool-tracking_env
pip install -r requirements.txt
```

4. Get introduced on how to load and work with the data

Start [Jupyter](https://jupyter.org/) and run the both notebook `How-to-load-the-data.ipynb` and `plot_window_sizes.ipynb` with:
```
jupyter lab
```

Changelog:
- 2025-02-12: Fix deprecated functions (pd.append, np.object, np.array non-homogeneity); Update dataset link (mirror)
- 2020-08-31: Add <a href="https://htmlpreview.github.io/?https://github.com/mutschcr/tool-tracking/blob/master/html/index.html">HTML API-docs</a> and user guide
- 2020-08-14: Update dataset with enhanced rivetter labels
- 2020-08-12: Update dataset with twice the amount of labeled data; enhanced labels.
- 2020-07-29: Update data loader and notebooks

Known issues:
- 2020-08-12: Enforcing window lenghts when segmenting rivetter data lets two very short windows (label -1) slip through. These cause problems and need to be filtered out: 'filter_labels(..)'

License:
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.

# Use in Publications 

- Löffler et al. (2022) "Don't Get Me Wrong: How to Apply Deep Visual Interpretations to Time Series" https://arxiv.org/abs/2203.07861
- Redzepagic et al. (2020) "A Sense of Quality for Augmented Reality Assisted Process Guidance" https://doi.org/10.1109/ISMAR-Adjunct51615.2020.00046
- Mishra et al. (2020) "Recipes for Post-training Quantization
of Deep Neural Networks" https://www.emc2-ai.org/assets/docs/virtual-20/emc2-virtual20-paper-8.pdf
- Löffler et al. (2020) "Automated Quality Assurance for Hand-Held Tools via Embedded Classification and AutoML" https://doi.org/10.1007/978-3-030-67670-4_33 

## Cite as
```
@InProceedings{10.1007/978-3-030-67670-4_33,
author="L{\"o}ffler, Christoffer
and Nickel, Christian
and Sobel, Christopher
and Dzibela, Daniel
and Braat, Jonathan
and Gruhler, Benjamin
and Woller, Philipp
and Witt, Nicolas
and Mutschler, Christopher",
editor="Dong, Yuxiao
and Ifrim, Georgiana
and Mladeni{\'{c}}, Dunja
and Saunders, Craig
and Van Hoecke, Sofie",
title="Automated Quality Assurance for Hand-Held Tools via Embedded Classification and AutoML",
booktitle="Machine Learning and Knowledge Discovery in Databases. Applied Data Science and Demo Track",
year="2021",
publisher="Springer International Publishing",
address="Cham",
pages="532--535",
isbn="978-3-030-67670-4"
}


```