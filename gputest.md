Clone yolov5 repo
Go to datasets/wheat.yaml
Copy python code and change yaml[“path”] to path
Conda env create -f xxx/yaml
Download models
 
https://github.com/ultralytics/yolov5/releases
 
 
https://docs.ultralytics.com/yolov5/tutorials/multi_gpu_training/ 
https://docs.ultralytics.com/datasets/detect/globalwheat2020/#dataset-yaml 
 
·         Manually Download both the images and the labels and put them in the right folder 
·         Manually download Arial.tff 
·         https://github.com/ultralytics/yolov5/issues/5643 
·         https://ultralytics.com/assets/Arial.ttf
·         conda env create –f myenv.yaml 
·         Go to yolov5 folder and run the below: 
o    mv Arial.ttf /home/user/.config/Ultralytics/Arial.ttf 
o    python -m torch.distributed.run --nproc_per_node 4 train.py --batch 128 --data GlobalWheat2020.yaml --weights ./yolov5x6.pt --device 0,1,2,3 --epochs 101 --img-size=1024 
-    python -m torch.distributed.run --nproc_per_node 1 train.py --batch 128 --data GlobalWheat2020.yaml --weights ./yolov5x6.pt --device 0 --epochs 101 --img-size=570
