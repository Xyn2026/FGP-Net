FGP-Net:  Rotation-Invariant 3D Point Cloud Learning via Fine-Grained Geometric Perception

## Requirements

* Python 3.7
* Pytorch 1.10
* CUDA 10.2
* Packages: pytorch3d, tqdm, sklearn, visualdl, opencv-python

## Data

The ModelNet40 and ShapeNetPart dataset will be automatically downloaded. For [ScanObjectNN](https://hkust-vgd.github.io/scanobjectnn/), you need to fill out an agreement to get the download link.

## Performance
* Accuracy on **ModelNet40** under rotation: 
* Accuracy on **ScanObjectNN** OBJ_BG classification under rotation:

| z/z | z/SO(3)  | SO(3)/SO(3) |
| :---: | :---: | :---: |
| 91.2% | 89.9% | 91.3% |

* Averaged mIoU on **ShapeNetPart segmentation** under rotation: 
 
|  z/SO(3)  |
| :--- |
| Class mIOU  | 81.2% | 


```
## Training Command

* For ModelNet40 model train (1024 points)
  ```
  python main_cls.py --exp_name=modelnet40_cls --train_rot=z --test_rot=so3
  ```

* For ShapeNetPart segmentation model train (2048 points)
  ```
  python main_seg.py --exp_name=shapenet_seg --train_rot=z --test_rot=so3
  ```

## Acknowledgement

Our code borrows a lot from:

- [Pointnet_Pointnet2_pytorch](https://github.com/yanx27/Pointnet_Pointnet2_pytorch)
- [DGCNN](https://github.com/WangYueFt/dgcnn)
- [DGCNN.pytorch](https://github.com/AnTao97/dgcnn.pytorch)
- [vnn-pc](https://github.com/FlyingGiraffe/vnn-pc/)
