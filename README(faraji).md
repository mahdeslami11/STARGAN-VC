# STARGAN-VC ✔
This is a pytorch implementation of the paper: StarGAN-VC: Non-parallel many-to-many voice conversion with star generative adversarial networks:  https://arxiv.org/abs/1806.02169 .
and I also used this paper: [AUTOVC: Zero-Shot Voice Style Transfer with Only Autoencoder Loss (ICML2019)](https://arxiv.org/pdf/1905.05879v2.pdf)
Note that the model architecture is a little different from that of the original paper.

![Untitled14114](https://user-images.githubusercontent.com/114937581/210011279-512e2985-2e7d-4528-9c79-58f26a893391.png)



## summery of repo ✔
Summary by hannaneh faraji:
This is a method that allows non-parallel manyto-many voice conversion (VC) by using a variant of a generative adversarial network (GAN) called StarGAN. Our method, which we call StarGAN-VC, is noteworthy in that it requires no parallel utterances, transcriptions, or time alignment procedures for speech generator training, simultaneously learns many-to-many mappings across different attribute domains using a single generator network, is able to generate converted speech signals quickly enough to allow real-time implementations and requires only several minutes of training examples to generate reasonably realistic sounding speech. Subjective evaluation experiments on a non-parallel many-to-many speaker identity conversion task revealed that the proposed method obtained higher sound
quality and speaker similarity than a state-of-the-art method based on variational autoencoding GANs.

summary (voice) ✔
https://drive.google.com/file/d/1RraBeVvB1oVcjoaM1jnJyVykSrMzQmJa/view?usp=share_link

## project explanation ✔
[project explanation.pdf](https://github.com/mahdeslami11/STARGAN-VC/files/10322080/project.explanation.pdf)
[project 6-faraji.pdf](https://github.com/mahdeslami11/STARGAN-VC/files/10322147/project.6-faraji.pdf)

video: ✔
https://drive.google.com/file/d/1Cv_nuiuctwSBLEwTamuwJghPB30n0n9A/view?usp=sharing
https://drive.google.com/file/d/1k8R2_uMVb2O1X-KaN4Qbv6kG-EBze-70/view?usp=share_link


# Dependencies
* Python 3.6 (or 3.5)
* Pytorch 0.4.0
* pyworld
* tqdm
* librosa
* tensorboardX and tensorboard



https://uupload.ir/view/rec_0020_qo5u.mp4/   ✔
# Usage
## Download Dataset

please download and unzip [VCTK](https://homepages.inf.ed.ac.uk/jyamagis/page3/page58/page58.html) corpus to designated directories.

```bash
mkdir ./data
wget https://datashare.is.ed.ac.uk/bitstream/handle/10283/2651/VCTK-Corpus.zip?sequence=2&isAllowed=y
unzip VCTK-Corpus.zip -d ./data

Note: you may need to early stop the training process if the training-time test samples sounds good or the you can also see the training loss curves to determine early stop or not.


## These papers help to better understand STARGAN-VC  ✔
[1-STARGAN-VC2.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309519/3-STARGAN-VC2.pdf)

[2-STARGAN-one-shot.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309520/5-STARGAN-one-shot.pdf)

[3-STARGAN-japon.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309523/6-STARGAN-japon.pdf)

[4-STARGAN-toward.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309524/7-STARGAN-toward.pdf)

[5-STARGAN-ASR.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309525/8-STARGAN-ASR.pdf)

[6-STARGANv2-vc.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309517/2-STARGANv2-vc.pdf)

[7-STARGAN-ZSVC.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309551/9-STARGAN-ZSVC.pdf)

[8-stargan.pdf](https://github.com/Hanafj/STARGAN-VC/files/10309552/10-stargan.pdf)

[10 repo.zip](https://github.com/mahdeslami11/STARGAN-VC/files/10322158/10.repo.zip)

## Papers that use this repo: 
 [Blow: a single-scale hyperconditioned flow for non-parallel raw-audio voice conversion (NeurIPS 2019)](https://arxiv.org/pdf/1906.00794.pdf)
 [ADAGAN: ADAPTIVE GAN FOR MANY-TO-MANY NON-PARALLEL VOICE CONVERSION (under review for ICLR 2020)](https://openreview.net/pdf?id=HJlk-eHFwH)



## hannaneh faraji(40114140111016)  ✔
I am a master's student at South Tehran University, in the field of medical engineering, bioelectrical orientation. This project is related to the course of digital signal processing .
email address: hanafj98@gmail.com


orginal project: https://github.com/liusongxiang/StarGAN-Voice-Conversion  ✔

