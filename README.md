# derain_dehaze

## Installation

### Run these lines in a conda environment
- conda install pytorch==1.10.0 torchvision==0.11.0 torchaudio==0.10.0 cudatoolkit=11.3 -c pytorch -c conda-forge
- python -m pip install detectron2 -f https://dl.fbaipublicfiles.com/detectron2/wheels/cu113/torch1.10/index.html
     
## Inference

```shell
python inference.py --dir_path DIR_OF_TEST_IMAGES --checkpoint CHECKPOINT_PATH --save_dir RESULTS_WILL_BE_SAVED_HERE 
```
Example usage
```shell
abhishek@gvlab:~/abk/iddaw/Drdo_poc$ python derain_dehaze/inference.py --dir_path derain_dehaze/input/ --checkpoint derain_dehaze/ckp/Raindrop.pth --save_dir derain_dehaze/output/
```
