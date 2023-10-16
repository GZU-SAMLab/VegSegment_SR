# VegSegment_SR
*Phenotype segmentation method based on spectral reconstruction for UAV field vegetation*

Field phenotyping can show plant growth in real-time, and segmented vegetation data can facilitate the visualization and analysis of vegetation information by reducing the influence of background noise. Field phenotype segmentation is considered a difficult task due to the extremely complex environment. Currently, spectral-based methods with deep learning for field vegetation segmentation are developing to overcome complex environments and poor generalization, but there are still two limitations. 
One is that the equipment for real-field data collection is extremely expensive. The other is that the datasets in the field are scarce, which is time-consuming and laborious for data annotation. To solve these problems, this study aims to propose a weakly supervised field vegetation segmentation method by introducing multispectral images as a priori information and referring to the theory of vegetation index (VI). In detail, we first adopt the visible light images to reconstruct corresponding multispectral images and then perform feature fusion based on the reconstructed image. Furthermore, a VI-based threshold segmentation is achieved on the reconstructed multispectral images to obtain the field vegetation segmentation map. 
In addition, we provide an unmanned aerial vehicle (UAV) RGB-multispectral image dataset, including 2358 pairs of RGB-multispectral images. We introduce a variety of spectral reconstruction (SR) methods as the baseline model and train different SR methods on our dataset, which are applied to different crop vegetations and environments, showing satisfactory experimental results.

# Env

```shell
conda create --name rtm python=3.8 -y
conda activate rtm
conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch
conda install gdal=3.4.1
conda install scikit-image=0.19.2
conda install matplotlib=3.5.2

pip install opencv-python==4.6.0.66
pip install einops==0.4.1
```



# Data

- Data will be released soon.
- Download the dataset.
- Place the dataset folder to `/dataset/`.

```shell
├─dataset
        ├─data_split.py
        └─MSI&RGB
```



- Run `python data_split.py`.

```shell
├─dataset
        ├─data_split.py
        ├─MSI&RGB
        ├─split_txt
        │  		├─train_list.txt
        │  		└─val_list.txt
        ├─Train_MSI
        │  		├─xxx0001.tif
        │  		├─xxx0002.tif
        │  		:
        │  		└─xxx0009.tif
        ├─Train_RGB
        │  		├─xxx0001.jpg
        │  		├─xxx0002.jpg
        │  		:
        │  		└─xxx0009.jpg
        ├─Val_MSI
        │  		├─xxx1000.tif
        │  		├─xxx2000.tif
        │  		:
        │  		└─xxx9000.tif
        └─Val_RGB
           		├─xxx1000.jpg
           		├─xxx2000.jpg
           		:
           		└─xxx9000.jpg
```
