python tools/resize_images_to_resolution.py --max_resolution 1024x1024 --save_as_png --interpolation lanczos4 --copy_associated_files /data/ebifly/orig /data/ebifly/train/

# 学習
accelerate launch --num_cpu_threads_per_process 8 sdxl_train_network.py --config_file=/data/ebifly/config.toml --dataset_config /data/ebifly/database.toml

# memo
```bash
# ファイル名をランダムにする
find . -type f -iname "*.png" -exec bash -c 'mv "$0" "${0%/*}/$(head /dev/urandom | tr -dc "0-9" | head -c 6).png"' {} \;
```

```
blonde hair, blonde eyes
```

```bash
for png_file in *.png; do
    # txtファイル名をpngの拡張子をtxtに置き換えて作成
    txt_file="${png_file%.png}.txt"
    
    # 指定された内容をtxtファイルに書き込む
    echo "ebifurai,no humans,black background,simple background,still life" > "$txt_file"
done
```

tempura,shrimp tempura,shrimp


# v2
タグ修正、画像ファイル変更

# v3
AdamW8bit

# v4
batch=4
