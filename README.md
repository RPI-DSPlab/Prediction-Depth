# Unofficial Implementation of Prediction Depth

This is a community script for [Deep Learning Through the Lens of Example Difficulty](https://arxiv.org/abs/2106.09647).

This implementation is adapted from https://github.com/pengbohua/AngularGap/tree/12dad1ec18d3c15a41835c3c342f82051d895ccc/standard_curriculum_learning/prediction_depth

## requirement
```shell script
pip3 install -r requirement.txt
```
Make a log directory for ResNet18 with Weight Standardization and Group Norm / original ResNet18 / VGG16
```shell script
mkdir ./cl_results_vgg
```
Changing number of random seeds allows you to train more models to get average PD (line 284 in get_pd_resnet.py).
Run training and plot the 2D histogram for train split and validation split afterwards.
```shell script
python3 get_pd_resnet_vgg.py --result_dir ./cl_results_vgg --train_ratio 0.5 --knn_k 30
python3 plot_pd_hist.py --result_dir ./cl_results_vgg
python3 get_pd_resnet.py --result_dir ./cl_results_resnet --train_ratio 0.5 --knn_k 30
python3 plot_pd_hist.py --result_dir ./cl_results_resnet
```

## Run PD in oneline
Alternatively, run the following code to get all previous results in one line
```shell script
sh run_pd.sh
```
