## Learning to Color from Language
[Learning to Color from Language, NAACL, 2018 (short)](http://aclweb.org/anthology/N18-2120)


### Instructions : 
1. Setup a fresh environment,
```
conda create -n colors python=3.8
conda activate colors
conda install pytorch==1.7.1 torchvision==0.8.2 torchaudio==0.7.2 cudatoolkit=10.2 -c pytorch
pip install scikit-image scikit-learn pudb h5py opencv-python
mkdir trial models
```

2. Download data : https://obj.umiacs.umd.edu/learning_to_color/coco_colors.h5

3. Extract features from black-and-white images
`python extract_image_features.py --input_h5_file coco_colors.h5 --output_h5_file image_features.h5`

4. Then run : 
`python autocolorize_resnet.py --h5_file coco_colors.h5 --features_file ./image_features.h5 --vocab_file_name ./priors/coco_colors_vocab.p --image_save_folder ./trial/ --model_save_file ./models/`

#### Film Activations
![Film Activations](https://raw.githubusercontent.com/superhans/colorfromlanguage/master/images/Activations4.png)

If you use this work, please cite:

    @InProceedings{Manjunatha:Iyyer-ColorLanguage,
        Title = {Learning to Color from Language},
        Booktitle = {North American Chapter of the Association for Computational Linguistics},
        Author = {Varun Manjunatha and Mohit Iyyer and Jordan Boyd-Graber and Larry Davis},
        Year = {2018},
    }
