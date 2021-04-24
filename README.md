# CD-GCN
PyTorch implementation of "Central Difference Graph Convolutional Networkfor Skeleton-Based Action Recognition".

## Prerequisite
 - g++ 5.4.0

## Compile cuda extensions
  ```
  cd ./model/Temporal_shift
  bash run.sh
  ```

## Data Preparation
 - Download the raw data of [NTU-RGBD](https://github.com/shahroudy/NTURGB-D) and [NTU-RGBD120](https://github.com/shahroudy/NTURGB-D).
 
 - For NTU-RGBD, preprocess data with `python data_gen/ntu_gendata.py`. For NTU-RGBD120, preprocess data with `python data_gen/ntu120_gendata.py`. 
  
 - Generate the bone data with `python data_gen/gen_bone_data.py`.

 - Generate the motion data with `python data_gen/gen_motion_data.py`.

## Training & Testing

  - The general training template command:

    `python main.py --config ./config/nturgbd-cross-view/train_joint.yaml`

    `python main.py --config ./config/nturgbd-cross-view/train_bone.yaml`

    `python main.py --config ./config/nturgbd-cross-view/train_joint_motion.yaml`

    `python main.py --config ./config/nturgbd-cross-view/train_bone_motion.yaml`

  - The general testing template command:

    `python main.py --config ./config/nturgbd-cross-subject/test_joint.yaml`

    `python main.py --config ./config/nturgbd-cross-subject/test_bone.yaml`

    `python main.py --config ./config/nturgbd-cross-subject/test_joint_motion.yaml`

    `python main.py --config ./config/nturgbd-cross-subject/test_bone_motion.yaml`
    
  - Use the corresponding config files from ./config to train/test different datasets

## Multi-stream ensemble

To ensemble the results of 4 streams. Change models name in `ensemble.py` depending on your experiment setting. Then run `python ensemble.py`.

## Trained models

We release several trained models:














































