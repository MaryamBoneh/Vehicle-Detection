# VehicleDetection
Vehicle Detection Using Deep Learning and YOLO Algorithm

![a1](https://user-images.githubusercontent.com/72157067/132953532-d7aba17a-2ca8-4703-a9e2-7c314e20f669.png)

![test_res_1](https://user-images.githubusercontent.com/72157067/132954150-720b0c16-586a-4683-b60c-7dc9b4e55e9f.jpg)


## Dataset

take or find vehicle images for create a special dataset for fine-tuning.

Train : 70%

Validition : 20%

Test : 10%


## dataset.yaml

config dataset.yaml for the address and information of your dataset.

```
path: Dataset/dataset-vehicles  # dataset root dir
train: images/train  # train images (relative to 'path')
val: images/val  # val images (relative to 'path')
test:  # test images (optional)

# Classes
nc: 5  # number of classes
names: [ 'Car', 'Motorcycle', 'Truck', 'Bus', 'Bicycle']  # class names

```

## Clone Vehicle-Detection Repository
```
git clone https://github.com/MaryamBoneh/Vehicle-Detection
cd Vehicle-Detection
pip install -r requirements.txt
```

## wandb

to have mAP, loss, confusion matrix, and other metrics, sign in www.wandb.ai.

```
pip install wandb
```

## Train

fine-tuning on a pre-trained model of yolov5.

```
python train.py --img 640 --batch 16 --epochs 50 --data dataset.yaml --weights yolov5m.pt
```

## Test

after train, gives you weights of train and you should use them for test.

```
python detect.py --weights runs/train/exp12/weights/best.pt --source test_images/imtest13.JPG
```


you can also use the weight file in path 'runs/train/exp12/weights/best.pt' without the train.
this weight is the result of 128 epoch train on the following dataset.

## My Vehicle Dataset
```
https://b2n.ir/vehicleDataset
```
