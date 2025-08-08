# PointFoot Gym 环境配置和使用指南

## 环境配置

### 1. 解决 libpython 错误

如果遇到 libpython 相关错误，请按以下步骤操作：

#### 检查 conda 环境路径
```bash
conda info -e
```

#### 设置环境变量
```bash
export LD_LIBRARY_PATH=/home/shenlan/anaconda3/envs/limx/lib:$LD_LIBRARY_PATH
export LD_PRELOAD=/shenlan/lib/x86_64-linux-gnu/libstdc++.so.6
```

### 2. 设置机器人类型
```bash
export ROBOT_TYPE=PF_TRON1A
```

## 使用命令

### 运行训练好的模型
```bash
python legged_gym/scripts/play.py --task=pointfoot_rough --load_run Aug07_16-23-38_ --checkpoint 13000
```

### 训练新模型
```bash
python legged_gym/scripts/train.py --task=pointfoot_rough --num_envs 8192 --max_iterations 15000 --headless

python legged_gym/scripts/train.py --task=pointfoot_rough --num_envs 16384 --max_iterations 15000 --headless

python legged_gym/scripts/train.py --task=pointfoot_rough --num_envs 32768 --max_iterations 15000 --headless
```

## 参数说明

- `--task=pointfoot_rough`: 指定任务类型为粗糙地形上的点足机器人
- `--num_envs 8192`: 设置并行环境数量为8192
- `--max_iterations 15000`: 最大训练迭代次数为15000
- `--headless`: 无头模式运行（不显示GUI）
- `--load_run`: 加载指定的训练运行
- `--checkpoint`: 指定检查点编号