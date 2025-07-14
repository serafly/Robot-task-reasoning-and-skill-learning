# Robot Task Reasoning and Skill Learning

The implementation of the paper "**Enhancing Stability and Reliability in LLM-Driven Robotic Manipulation Through Human Skill Demonstration and Visual Tracking**".

(1) Demonstration of actual tasks

(2) Simulation Environment Configuration
<p align="center">
<img src="https://github.com/serafly/Robot-task-reasoning-and-skill-learning/blob/main/assets/simluation_00.png?raw=true" 
  alt="image" width="450" height="auto">
</p>

(3) HUMAN PREFERENCES
<p align="center">
<img src="https://github.com/serafly/Robot-task-reasoning-and-skill-learning/blob/main/assets/HUMAN PREFERENCES.png?raw=true" 
  alt="image" width="450" height="auto">
</p>

(4) Query-Expected-Object set for multi-objects picking-placing tasks
<p align="center">
<img src="https://github.com/serafly/Robot-task-reasoning-and-skill-learning/blob/main/assets/multi-objects.png?raw=true" 
  alt="image" width="450" height="auto">
</p>


- [ ] The prompt frameworks for SCoT

- [ ] The prompt frameworks for the Intent Analyzer and Behavior Self-Correction


## 0. Preparation

1. System: Ubuntu 20.04
2. CPU: Intel(R) Xeon(R) Silver 4214R CPU @ 2.40GHz
3. GPU: NVIDIA GeForce RTX 2080 Ti Rev. A
4. OpenAI API Key: [here](https://openai.com/blog/openai-api).

## 1. Installation

#### Create conda environment

Launch a new terminal.

```
conda activate
conda create -n pickplace python==3.10.0
conda activate pickplace
```

#### Install Coppeliasim

1. Go to the Coppeliasim downloading [website](https://www.coppeliarobotics.com/previousVersions).
2. Download `CoppeliaSim Player, Ubuntu 20.04` file. It should be a `.tar.xz` file.
3. Extract the `.tar.xz` file to `/home/your-account/`.

#### Clone the repository

Launch a new terminal to clone this repository.
```
cd ~
git clone https://github.com/serafly/Robot-task-reasoning-and-skill-learning.git
```

#### Download Coppeliasim scene

1. Download [this file](https://drive.google.com/file/d/1FxXkRcFUu9Og7UsbsiMjtfF2nxXHiBzY/view?usp=drive_link) (`PickPlaceScene.ttt`) from Google drive.
2. Move this file to `/home/your-account/Robot-task-reasoning-and-skill-learning/` directory.

#### Download the vision models

1. Download [this file](https://drive.google.com/file/d/1HPY5hxVC7AE3T9ZJIcK-gisoQOLEkyFf/view?usp=drive_link) (`used_owlvit_sam.tar.xz`) from Google drive.
2. Extract the `used_owlvit_sam.tar.xz` file to `/home/your-account/Robot-task-reasoning-and-skill-learning/` directory.

## 2. Configuration

#### Install required Python packages

```
conda activate pickplace
cd Robot-task-reasoning-and-skill-learning
pip install -r requirements.txt
```

#### Enter Coppeliasim and load PickAndPlace.ttt scene

Launch another terminal to enter Coppeliasim.

```
cd CoppeliaSim_Player_V4_1_0_Ubuntu20_04/
./coppeliasim.sh
```

`File` -- `Open scene...` -- `/home/your-account/Robot-task-reasoning-and-skill-learning/` -- select the `PickPlaceScene.ttt`.

#### Config parameters

Open the file `global_parameters.py`, select `OPENAI_API_KEY_for_Agent`, `OpenAI_chat_model`, `OpenAI_response_model`, `ROOT_PATH` and save this file.

## 3. Launch project

Open Coppeliasim window, and click `Start` bottom.
Then run `test_proposed_current.py` script.


