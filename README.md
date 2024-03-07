# Steps to Run the Code

## For Installation, run these lines in a conda environment
- conda install pytorch==1.10.0 torchvision==0.11.0 torchaudio==0.10.0 cudatoolkit=11.3 -c pytorch -c conda-forge
- python -m pip install detectron2 -f https://dl.fbaipublicfiles.com/detectron2/wheels/cu113/torch1.10/index.html

## Folder Structure
> > The structure should be:
>
> ```
> .
> ├── Drdo_poc
> │   └── derain_dehaze
> │       ├── ckp (has two ckpoints given)
> │       ├── input & output img folders
> │       ├── models
> │       |   |── ...
> │       ├── utils
> │       |   ├── ...
> │       ├── inference.py
> │       ├── README.md
> │       └── train.py
> ├── detectron2_configs
> ├── app.py
> ├── maxim.py
> └── segmentation.py

## Detectron2
1. Clone the detectron2 repo to the scratch folder
```shell
git clone https://github.com/facebookresearch/detectron2.git
```
2. run segmentation.py
```shell
(detectron) abhishek@gvlab:~/abk/iddaw/Drdo_poc$ python segmentation.py 
```
## app.py
```shell
(detectron) abhishek@gvlab:~/abk/iddaw/Drdo_poc$ python app.py --dir_path derain_dehaze/rainfog/input/ --checkpoint derain_dehaze/ckp/Rainfog.pth --save_dir derain_dehaze/rainfog/output/  
```
Local Server 
![App Image 1](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/app/app%20window.jpeg)


## Inference
1. Include the Drdo_poc directory to the PYTHONPATH environment variable.
   (Update the path accordingly)
```shell
export PYTHONPATH="${PYTHONPATH}:/home/abhishek/abk/iddaw/Drdo_poc"
```
2. Command to run the inference.py
```shell
python inference.py --dir_path DIR_OF_TEST_IMAGES --checkpoint CHECKPOINT_PATH --save_dir RESULTS_WILL_BE_SAVED_HERE 
```
Example usage
```shell
abhishek@gvlab:~/abk/iddaw/Drdo_poc$ python derain_dehaze/inference.py --dir_path derain_dehaze/input/ --checkpoint derain_dehaze/ckp/Raindrop.pth --save_dir derain_dehaze/output/
```
![Terminal Image 1](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/rainfog/inferance%20terminal%20output.jpeg)

## Training
```shell
python train.py --teacher TEACHER_CHECKPOINT_PATH_0 TEACHER_CHECKPOINT_PATH_1 TEACHER_CHECKPOINT_PATH_2 --save-dir RESULTS_WILL_BE_SAVED_HERE
```
> For more info related to training, refer:
> [Two-stage-Knowledge-For-Multiple-Adverse-Weather-Removal](https://github.com/fingerk28/Two-stage-Knowledge-For-Multiple-Adverse-Weather-Removal)

## Inference Results

### using Raindrop.pth ckpt on Rain Images
![Raindrop Image 1](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/raindrop/0000037_rgb.png)
![Raindrop Image 2](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/raindrop/15_rain_mr_OCTOBER_1_rgb_leftImg8bit.png)
![Raindrop Image 3](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/raindrop/0000025_rgb.png)
![Raindrop Image 4](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/raindrop/0000021_rgb.png)
![Raindrop Image 5](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/raindrop/0000087_rgb.png)

### using Rainfog.pth ckpt on Fog Images
![Fog Image 1](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/rainfog/0000090_rgb.png)
![Fog Image 2](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/rainfog/0000094_rgb.png)
![Fog Image 3](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/rainfog/0000102_rgb.png)
![Fog Image 4](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/rainfog/0000171_rgb.png)
![Fog Image 5](https://github.com/abhishekredy18/derain_dehaze/blob/main/images/rainfog/0000173_rgb.png)
