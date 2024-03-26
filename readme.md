# yolov8_cspdarknet-detection

## 训练模型
```shell
python trainer.py --device_id cuda \
--pretrained_pt_path /res/pvdetection_07fe2b.pt \
--batch_size 16 \
--max_epochs 300 \
--ema_enabled \
--wandb_enabled \
--early_stop \
--trainset_path /mypath/quaming_veh_dataset/images/train \
--valset_path /mypath/quaming_veh_dataset/images/val
```

## 运行demo
```shell
python demo.py --weight my_weight.pt --camera
```

## 导出模型
```shell
python export.py --weight my_weight.pt --input_shape 1 3 1280 1280 --input_names image --output_names box0 cls0 box1 cls1 box2 cls2 --opset_version 13 --enable_onnxsim
```
