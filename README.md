## Self-supervised Structure-sensitive Learning (SSL)
Ke Gong, Xiaodan Liang, Xiaohui Shen, Liang Lin, "Look into Person: Self-supervised Structure-sensitive Learning and A New Benchmark for Human Parsing", CVPR 2017.

### Introduction

SSL is a state-of-art deep learning methord for human parsing built on top of [Caffe](http://caffe.berkeleyvision.org).
This novel self-supervised structure-sensitive learning approach can impose human pose structures into parsing results without resorting to extra supervision (i.e., no
need for specifically labeling human joints in model training). The self-supervised learning framework can be injected into any advanced neural networks to help incorporate rich high-level knowledge regarding human joints from a global perspective and improve the parsing results.

This distribution provides a publicly available implementation for the key model ingredients reported in our latest [paper](http://openaccess.thecvf.com/content_cvpr_2017/papers/Gong_Look_Into_Person_CVPR_2017_paper.pdf) which is accepted by CVPR2017.

Please consult and consider citing the following papers:

    @InProceedings{Gong_2017_CVPR,
      author = {Gong, Ke and Liang, Xiaodan and Zhang, Dongyu and Shen, Xiaohui and Lin, Liang},
      title = {Look Into Person: Self-Supervised Structure-Sensitive Learning and a New Benchmark for Human Parsing},
      booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
      month = {July},
      year = {2017}
    }
    @inproceedings{Co-CNN,
      title={Human Parsing with Contextualized Convolutional Neural Network},
      author={Xiaodan Liang and Chunyan Xu and Xiaohui Shen and Jianchao Yang and Si Liu and Jinhui Tang and Liang Lin and Shuicheng Yan},
      booktitle={ICCV},
      year={2015}
    }

### Look into People (LIP) Dataset

The SSL is trained and evaluated on our [LIP dataset](http://hcp.sysu.edu.cn/lip/) for human parsing, or [Alternate Address](http://222.200.181.224/lip).  Please check it for more model details.


### Pre-trained models

We have released our trained models with best performance [here](https://drive.google.com/open?id=0BzvH3bSnp3E9eHMyVS1RbUVDems).


### Train and test

1. Download LIP dataset or prepare your own data.
2. Put the images(*,jpg) and segmentations(*.png) into ssl/human/data/images and ssl/human/data/labels
3. Put the train, val, test lists into ssl/human/list. Each type contains a list for path and a list for id (e.g., train.txt and train_id.txt) 
4. Download the pre-trained model and put it into ssl/human/model/attention/. You can also refer [DeepLab](https://bitbucket.org/aquariusjay/deeplab-public-ver2) for more models. 
5. Set up your init.caffemodel before training and test.caffemodel before testing. You can simply use a soft link.
6. The prototxt files for network config are saved in ssl/human/config
7. In run_human.sh, you can set the value of RUN_TRAIN adn RUN_TEST to train or test the model.
8. After you run TEST, the computed features will be saved in ssl/human/features. You can run the provided MATLAB script, show.m to generate visualizable results. Then you can run the Python script, test_human.py to evaluate the performance.
