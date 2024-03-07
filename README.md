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
