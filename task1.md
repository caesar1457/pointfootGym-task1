For libpython error:

- Check conda path:
    ```bash
    conda info -e
    ```
- Set LD_LIBRARY_PATH:
    ```bash
    export LD_LIBRARY_PATH=/home/shenlan/anaconda3/envs/limx/lib:$LD_LIBRARY_PATH
    export LD_PRELOAD=/shenlan/lib/x86_64-linux-gnu/libstdc++.so.6
    ```
export ROBOT_TYPE=PF_TRON1A

    python legged_gym/scripts/play.py --task=pointfoot_rough --load_run Aug06_11-04-03_ --checkpoint 5000


    python legged_gym/scripts/train.py --task=pointfoot_rough --num_envs 8192 --max_iterations 15000 --headless