# StarGAN-Voice-Conversion
This is a pytorch implementation of the paper: StarGAN-VC: Non-parallel many-to-many voice conversion with star generative adversarial networks:  https://arxiv.org/abs/1806.02169 .
and I also used this paper:
[AUTOVC: Zero-Shot Voice Style Transfer with Only Autoencoder Loss (ICML2019)](https://arxiv.org/pdf/1905.05879v2.pdf)
Note that the model architecture is a little different from that of the original paper.


![image](https://user-images.githubusercontent.com/114937581/209695124-9f99eded-147c-460c-82a4-b5511ce68bdb.png)

This is a method that allows non-parallel manyto-many voice conversion (VC) by using a variant of a generative adversarial network (GAN) called StarGAN. Our method, which we call StarGAN-VC, is noteworthy in that it requires no parallel utterances, transcriptions, or time alignment procedures for speech generator training, simultaneously learns many-to-many mappings across different attribute domains using a single generator network, is able to generate converted speech signals quickly enough to allow real-time implementations and requires only several minutes of training examples to generate reasonably realistic sounding speech. Subjective evaluation experiments on a non-parallel many-to-many speaker identity conversion task revealed that the proposed method obtained higher sound
quality and speaker similarity than a state-of-the-art method based on variational autoencoding GANs.


# Dependencies
* Python 3.6 (or 3.5)
* Pytorch 0.4.0
* pyworld
* tqdm
* librosa
* tensorboardX and tensorboard

# Usage
## Download Dataset

please download and unzip [VCTK](https://homepages.inf.ed.ac.uk/jyamagis/page3/page58/page58.html) corpus to designated directories.

```bash
mkdir ./data
wget https://datashare.is.ed.ac.uk/bitstream/handle/10283/2651/VCTK-Corpus.zip?sequence=2&isAllowed=y
unzip VCTK-Corpus.zip -d ./data
```
If the downloaded VCTK is in tar.gz, run this:

```bash
tar -xzvf VCTK-Corpus.tar.gz -C ./data
```

Preprocess data

We will use Mel-cepstral coefficients(MCEPs) here.

```bash
python preprocess.py --sample_rate 16000 \
                    --origin_wavpath data/VCTK-Corpus/wav48 \
                    --target_wavpath data/VCTK-Corpus/wav16 \
                    --mc_dir_train data/mc/train \
                    --mc_dir_test data/mc/test
```

Train model

Note: you may need to early stop the training process if the training-time test samples sounds good or the you can also see the training loss curves to determine early stop or not.

```
python main.py
```

Convert

For example: restore model at step 200000 and specify the source speaker and target speaker to `p262` and `p272`, respectively.

```
convert.py --resume_iters 200000 --src_spk p262 --trg_spk p272
```

## To-Do list
- [x] Post some converted samples (Please find some converted samples in the `converted_samples` folder).


## These papers help to better understand STARGAN-VC
[1-STARGAN-VC2.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309519/3-STARGAN-VC2.pdf)

[2-STARGAN-one-shot.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309520/5-STARGAN-one-shot.pdf)

[3-STARGAN-japon.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309523/6-STARGAN-japon.pdf)

[4-STARGAN-toward.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309524/7-STARGAN-toward.pdf)

[5-STARGAN-ASR.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309525/8-STARGAN-ASR.pdf)

[6-STARGANv2-vc.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309517/2-STARGANv2-vc.pdf)

[7-STARGAN-ZSVC.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309551/9-STARGAN-ZSVC.pdf)

[8-stargan.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309552/10-stargan.pdf)



## Papers that use this repo: 
 [Blow: a single-scale hyperconditioned flow for non-parallel raw-audio voice conversion (NeurIPS 2019)](https://arxiv.org/pdf/1906.00794.pdf)
 [ADAGAN: ADAPTIVE GAN FOR MANY-TO-MANY NON-PARALLEL VOICE CONVERSION (under review for ICLR 2020)](https://openreview.net/pdf?id=HJlk-eHFwH)



## hannaneh faraji(40114140111016)
