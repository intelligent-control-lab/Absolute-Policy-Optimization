# Absolute Policy Optimization

## Environment Installation

Install [mujoco_py](https://github.com/openai/mujoco-py), see the mujoco_py documentation for details. Note that mujoco_py **requires Python 3.6 or greater**.

Afterwards, simply install `rl_envs` by:

```
cd rl_envs
pip install -e .
```

Install environment:

```
conda create --name [your env name] --file requirements.txt
```

If you want to run Atari tasks, two additional commands are needed:

```
pip install "gymnasium[atari]
pip install "gymnasium[accept-rom-license]
```

---

## Policy Training

Take APO training for example:

- Continuous tasks:

  ```
  cd rl_lib/apo
  conda activate [your env name]
  python apo.py --task Push_Ant --seed 9 
  ```

  For other command line parameters, please refer to the code.

- Discrete tasks:

  ```
  cd rl_lib/apo
  conda activate [your env name]
  python apo.py --atari_name Riverraid --seed 9
  ```

  For other command line parameters, please refer to the code.

## APO Policy Video Production

After training finished:

```
python apo_video.py --model_path logs/<scpo log>/<scpo log specific seed>/pyt_save/model.pt --task <experiment name> --video_name <video name> --max_epoch <max epoch>           
```

## Plot the Training Curve 

```
cd rl_lib
mkdir comparison
(copy the log you want to visualize into the comparison/ folder)
python utils/plot.py comparison/ --title test --reward --value MinEpRet 
```
