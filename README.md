python tools/resize_images_to_resolution.py --max_resolution 1024x1024 --save_as_png --interpolation lanczos4 --copy_associated_files /data/asuken/orig /data/asuken/train/

# 学習
accelerate launch --num_cpu_threads_per_process 8 sdxl_train_network.py --config_file=/data/asuken/config.toml --dataset_config /data/asuken/database.toml

# memo
ファイル名をランダムにする
find . -type f -iname "*.png" -exec bash -c 'mv "$0" "${0%/*}/$(head /dev/urandom | tr -dc "0-9" | head -c 6).png"' {} \;

```
blonde hair, blonde eyes
```
