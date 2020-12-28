# DeepImmuno
Deep-learning empowered prediction and generation of immunogenic epitopes for T cell immunity. 

We recommend to try out our web application for that: https://deepimmuno.herokuapp.com/

> Please refer to **DeepImmuno-CNN** if you want to predict immunogenicity

> Plase refer to **DeepImmuno-GAN** if you want to generate immunogenic peptide

Enjoy and don't hesitate to ask me questions (contact at the bottom), I will be responsive! Feel free to raise an issue on github page!

## Citation
If you find that tool useful in your research, please consider citing our preprint:
https://www.biorxiv.org/content/10.1101/2020.12.24.424262v1

## DeepImmuno-CNN

#### Dependencies

python = 3.6

tensorflow = 2.3.0

numpy = 1.18.5

pandas = 1.1.1

```
Note: This is the enviroment that I used for development and I also tested it. But as long as you use python > 3, tensorflow = 2.3, It should also work.
```

#### How to use?

If you want to query a single epitope (peptide + HLA), for example you want to query peptide _**HPPLMNVER**_ along with _**HLA-A*0201**_. You need to

```
python3 deepimmuno-cnn.py --mode "single" --epitope "HPPLMNVER" --hla "HLA-A*0201"
```

If you want to query multiple epitopes, you just need to prepare a csv file like this:

```
AAAAAAAAA,HLA-A*0201
CCCCCCCCC,HLA-B*5801
DDDDDDDDD,HLA-C*0702
```

Then you run:

```
python3 deepimmuno-cnn.py --mode "multiple" --intdir "/path/to/above/file" --outdir "/path/to/output/folder"
```

**1. Please note, when you specify the output dir, don't include the forward slash at the end, for example, use "~/Desktop" instead "~/Desktop/"**

**2. PLease note, if python3 doesn't work, you can replace python3 to python, it depends your installed python interpreter**

A full help prompt is as below:

```
usage: deepimmuno-cnn.py [-h] [--mode MODE] [--epitope EPITOPE] [--hla HLA]
                         [--intdir INTDIR] [--outdir OUTDIR]

DeepImmuno-CNN command line

optional arguments:
  -h, --help         show this help message and exit
  --mode MODE        single mode or multiple mode
  --epitope EPITOPE  if single mode, specifying your epitope
  --hla HLA          if single mode, specifying your HLA allele
  --intdir INTDIR    if multiple mode, specifying the path to your input file
  --outdir OUTDIR    if multiple mode, specifying the path to your output folder
```

## DeepImmuno-GAN

#### Dependencies

python = 3.6

pytorch = 1.4.0

numpy = 1.18.4

pandas = 1.0.5

```
Note: This is the enviroment that I used for development and I also tested it. But as long as you use python > 3, pytorch = 1.4, It should also work.
```

#### How to use

Pretty simple, just run like this

```
python3 deepimmuno-gan.py --outdir "/path/to/store/output"
```

It will automatically genearte one batch, which is **64** pseudo-immunogenic peptides of **HLA-A*0201** for your. It is worth noting that, because of the way I encode the peptide, there will be a placeholder "-". 

A full help prompt is as below
```
usage: deepimmuno-gan.py [-h] [--outdir OUTDIR]

DeepImmuno-GAN to generate immunogenic peptide

optional arguments:
  -h, --help       show this help message and exit
  --outdir OUTDIR  specifying your output folder
```

**1. Please note, when you specify the output dir, don't include the forward slash at the end, for example, use "~/Desktop" instead "~/Desktop/"**

**2. PLease note, if python3 doesn't work, you can replace python3 to python, it depends your installed python interpreter**

## Contact

Guangyuan(Frank) Li

li2g2@mail.uc.edu

PhD student, Biomedical Informatics

Cincinnati Children's Hospital Medical Center(CCHMC)

University of Cincinnati, College of Medicine





