# SwinIR + PyramidBranch for Image Deblurring

This project is based on the [SwinIR](https://github.com/JingyunLiang/SwinIR) architecture, with modifications to support a **Pyramid Branch module** designed to enhance image deblurring performance.

##  Features
- Based on SwinIR architecture
- Added a multi-scale Pyramid Branch in the 2nd stage of the network
- Applied to image deblurring tasks (e.g., GoPro, HIDE,RealBlur-R)

### Training
python main_train_psnr.py --opt options/swinir/train_swinir_deblurring.json

#### Testing
python main_test_swinir.py --task swinir_deblurring --training_patch_size 64(96 for PBSwinIR) --model_path model_zoo/swinir/SwinIR_deblurring.pth --folder_lq testsets/GoPro/test/input --folder_gt testsets/GoPro/test/target

##### config
change H_size to 96, depths to [6, 7, 6, 6, 6, 6] , img_size to 96,  and net_type to swinir_modified when switching to PBSwinIR model