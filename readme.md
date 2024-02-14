# Absolute Policy Optimization

## Environment  Installation

Install environment:
```
conda create --name venv python=3.8
conda activate venv
pip install -r requirements.txt
```

Then, install `safe_rl_envs` by:
```
cd safe_rl_envs
pip install -e .
```

If you want to run Atari tasks, two additional commands are needed:

```
pip install "gymnasium[atari]"
pip install "gymnasium[accept-rom-license]"
```

If you want to run [Mujoco](https://gymnasium.farama.org/environments/mujoco/) tasks, please run:

```
pip install gymnasium[mujoco]
```

if you want to run robotics [Gymnasium-Robotics](https://robotics.farama.org/index.html) tasks, please run:

```
pip install gymnasium-robotics
```

After building the environment, please put any algorithms that you want to run into the folder `safe_rl_lib` in GUARD repository.

---

## Parameters  Tuning

Two critical hyperparameters need to be chosen wisely which are `omega1` and `omega2`. `omega1` refers to $\mu$ and `omega2` refers to the $H_{max}$. For further explanation, please check our original paper.

We tune these two parameters by grid search in domain $[0.001, 0.003, 0.005, 0.007, 0.01]\times[0.001, 0.003, 0.005, 0.007, 0.01]$.

---

## Policy  Training

Take APO and PAPO training for example:

- GUARD Continuous tasks:

  ```
  cd apo
  conda activate [your env name]
  python apo.py --task Push_Ant --seed [seed]
  ```

  For other command line parameters, please refer to the code.

- Atari tasks:

  ```
  cd apo
  conda activate [your env name]
  python apo.py --atari_name Riverraid --seed [seed]
  ```

  For other command line parameters, please refer to the code.

- Mujoco tasks

  ```
  cd apo
  conda activate [your env name]
  python apo.py --mujoco_name HumanoidStandup --seed [seed]
  ```

- Gymnasium-Robotics tasks:

  ```
  cd papo
  conda activate [your env name]
  python papo.py --mujoco_name HandReachDense --seed [seed]
  ```

  

