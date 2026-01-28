# Pose Classification (DeepStream 7.1) na Jetson Orin Nano

Ovaj repozitorij sadrži projekt u kojem sam pokušala pokrenuti Pose Classification Net model  
(https://docs.nvidia.com/tao/archive/5.3.0/text/pose_classification/pose_classification.html)  
koristeći NVIDIA DeepStream SDK 7.1 na Jetson Orin Nano uređaju. Većina koda je preuzeta iz službenog NVIDIA repozitorija, a napravljene su minimalne izmjene kako bi se primjer mogao pokrenuti u mom okruženju.

## Korišteno

- NVIDIA DeepStream SDK 7.1
- JetPack (Ubuntu za Jetson)
- CUDA (preko JetPack okruženja)
- TAO DeepStream aplikacije (`deepstream_tao_apps`)

## Instalacija DeepStream 7.1

DeepStream 7.1 je instaliran prema službenim uputama:

https://docs.nvidia.com/metropolis/deepstream/7.1/text/DS_Installation.html

Za instalaciju je korištena **Method 1 (Using SDK Manager)**, direktno na Jetson Orin Nano uređaju.

## Preuzeti kod

Korišten je službeni NVIDIA repozitorij:

https://github.com/NVIDIA-AI-IOT/deepstream_tao_apps

Grana/verzija: `release/tao_ds7.1ga`

Konkretno, praćene su upute iz:

https://github.com/NVIDIA-AI-IOT/deepstream_tao_apps/blob/release/tao_ds7.1ga/apps/tao_others/README.md

Nakon kloniranja repozitorija na Jetson, preuzeti su potrebni modeli i konfiguracijske datoteke prema navedenim uputama.

Uz službene upute bilo j epotrebno pokrenuti sljedeće naredbe:

`sudo apt-get install libeigen3-dev
sudo ln -s /usr/include/eigen3/Eigen /usr/include/Eigen
sudo CUDA_VER=12.6 make`

## Moje izmjene

U odnosu na originalni NVIDIA kod, promijenjene su samo dvije datoteke kako bi se primjer ispravno pokrenuo na uređaju. Ostatak projekta ostao je nepromijenjen.

### Detalji izmjena

U datoteci `deepstream_pose_classification_config.yaml` napravljene su sljedeće promjene:

- postavljen je `enc-type` na vrijednost `1`
- promijenjena je rezolucija u `streammux` dijelu konfiguracije (vrijednost `width` na `1920` i vrijednost `height` na `1080`

U datoteci `config_tracker_NvDCF_accuracy.yml` napravljena je sljedeća promjena:

- postavljen je `reidType` na vrijednost `0`

## Pokretanje

Pokretanje aplikacije rađeno je prema uputama iz NVIDIA README-a za `tao_others` aplikacije, uz navedene lokalne izmjene konfiguracije.

Napomena: potrebno je imati ispravno instaliran JetPack i DeepStream SDK 7.1 na Jetson Orin Nano uređaju.

## Reference

- NVIDIA DeepStream 7.1 dokumentacija:  
https://docs.nvidia.com/metropolis/deepstream/7.1/

- NVIDIA deepstream_tao_apps repozitorij:  
https://github.com/NVIDIA-AI-IOT/deepstream_tao_apps
