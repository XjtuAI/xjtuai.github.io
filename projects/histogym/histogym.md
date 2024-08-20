---
title: HistoGym
permalink: /histogym/
---

### HistoGym: A Reinforcement Learning Environment for Histopathological Image Analysis

<div style="text-align: center;">
    <a href="http://zhibo-liu.com">Zhi-Bo Liu</a>, 
    Xiaobo Pang, 
    <a href="https://xjtuai.com/jizhaowang">Jizhao Wang</a>,
    <a href="https://xjtuai.com/shuailiu">Shuai Liu</a>,
  <a href="https://chenli.group/people/Chen_Li/index.html">Chen Li</a>
</div>


<div style="text-align: center;">
    <a href="https://arxiv.org/abs/2408.08847">[paper]</a> &nbsp;
    <a href="https://github.com/xjtuai/histogym">[github]</a> &nbsp;
    <a href="http://zhibo-liu.com/doc/histogym/bibtex.txt">[cite]</a>
</div>
![demo](/images/histogym-demo.gif)

### Introduction

This paper addresses the question: ***Is the diagnostic process of doctors better modeled as a decision-making task rather than a classification task?*** We explore whether providing a reinforcement learning (RL) environment to simulate this diagnostic process is a worthwhile endeavor. The motivation for this work is straightforward: to create an RL environment that models the cancer diagnosis process using histopathological data.

<img src="/images/histogym-main.jpg" alt="histogym-main" style="zoom: 40%;" />

### Environment Complexity

We further investigate the impact of *Environment Complexity* on reinforcement learning (RL) performance by systematically analyzing three distinct levels of complexity: *Easy*, *Medium*, and *Hard* scenarios. This analysis provides insights into how varying degrees of environmental challenges influence the learning efficiency and robustness of RL algorithms.

<img src="/images/histogym-wsi.jpg" alt="histogym-wsi" style="zoom:33%;" />



### Code Example

```python
import numpy as np
from gym_histo import HistoEnv
# Initialize Arguments
img_path =’/path/to/wsi.tif’ xml_path = ’/path/to/annotaion.xml’ tile_size = 128
result_path = ’./results’
env = HistoEnv(img_path , xml_path , tile_size , result_path) obs = env.reset()
done = False while not done:
action = env.action_space.sample()
obs, reward, done, info = env.step(action)
print(’action=’, action, ’info=’, info, ’reward=’, reward, ’done=’, done) env.render(mode="human")
if done:
print("Episode Terminated", "reward=", reward) break
```

### Citation

If you use this code for your research, please cite our [paper](https://arxiv.org/abs/2408.08847).

```lat
@misc{histogym2024,
    title={HistoGym: A Reinforcement Learning Environment for Histopathological Image Analysis},
    author={Zhi-Bo Liu and Xiaobo Pang and Jizhao Wang and Shuai Liu and Chen Li},
    year={2024},
    eprint={2408.08847},
    archivePrefix={arXiv},
}
```




<div style="text-align: right;">
    <a href="http://zhibo-liu.com">back</a>
</div>