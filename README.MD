# UHC: Universal Humanoid Controller

> Repo under construction.  

<div float="center">
  <img src="assets/gif/teaser.gif" />
</div>

## Introduction 

In this project, we develop the Universal Humanoid Controller used in our projects: [embodiedpose](https://zhengyiluo.github.io/projects/embodied_pose/), [kin_poly](https://zhengyiluo.github.io/projects/kin_poly/), and [agent_design](https://zhengyiluo.github.io/projects/agent_design/). It is a humanoid controller is task-agnostic and only takes reference frames as input. We uses the MuJoCo simulator for this repository. It relives heavily on [residual force control](https://github.com/Khrylx/RFC) for keeping the humanoid stable, and we are actively working on relying less on this dependency. Here are a few highlights of the controller:

- Supports controlling humanoids constructed from SMPL, SMPL-H, and SMPL-X models, of all genders and body shapes.
- Causal and takes in one-frame of reference frame as input.
- Supports optimizing the humanoid's body shape paramters based on [Transform2Act](https://github.com/Khrylx/Transform2Act) and [agent_design](https://zhengyiluo.github.io/projects/agent_design/).
- Can support simulating mulitple humanoids in the same scene, though only as a proof of concept. 

## Dependencies

To create the environment, follow the following instructions: 

1. Create new conda environment and install pytroch:
```
conda create -n uhc python=3.8
conda install pytorch torchvision torchaudio pytorch-cuda=11.6 -c pytorch -c nvidia
```

2. Download and setup mujoco: [Mujoco](http://www.mujoco.org/)
```
wget https://github.com/deepmind/mujoco/releases/download/2.1.0/mujoco210-linux-x86_64.tar.gz
tar -xzf mujoco210-linux-x86_64.tar.gz
mkdir ~/.mujoco
mv mujoco210 ~/.mujoco/
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:~/.mujoco/mujoco210/bin
```




## Citation
If you find our work useful in your research, please cite our papers [embodiedpose](https://zhengyiluo.github.io/projects/embodied_pose/),  [kin_poly](https://zhengyiluo.github.io/projects/kin_poly/), and [agent_design](https://zhengyiluo.github.io/projects/agent_design/).
```
@inproceedings{Luo2022EmbodiedSH,
  title={Embodied Scene-aware Human Pose Estimation},
  author={Zhengyi Luo and Shun Iwase and Ye Yuan and Kris Kitani},
  booktitle={Advances in Neural Information Processing Systems},
  year={2022}
}

@inproceedings{Luo2021DynamicsRegulatedKP,
  title={Dynamics-Regulated Kinematic Policy for Egocentric Pose Estimation},
  author={Zhengyi Luo and Ryo Hachiuma and Ye Yuan and Kris Kitani},
  booktitle={Advances in Neural Information Processing Systems},
  year={2021}
}

@article{Luo2022FromUH,
  title={From Universal Humanoid Control to Automatic Physically Valid Character Creation},
  author={Zhengyi Luo and Ye Yuan and Kris M. Kitani},
  journal={ArXiv},
  year={2022},
  volume={abs/2206.09286}
}
``` 

