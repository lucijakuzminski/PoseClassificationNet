# Pose classification (DeepStream 7.1) na Jetson Orin Nano

Ovaj repozitorij sadrži projekt u kojem sam pokušala pokrenuti Pose Classification Net model (https://docs.nvidia.com/tao/archive/5.3.0/text/pose_classification/pose_classification.html) koristeći NVIDIA DeepStream SDK 7.1 na Jetson Orin Nano uređaju. Većina koda je preuzeta iz službenog NVIDIA repozitorija, a ja sam napravila minimalne izmjene kako bi se primjer mogao pokrenuti u mom okruženju.

## Korišteno

- NVIDIA DeepStream SDK 7.1
- JetPack (Ubuntu za Jetson)
- CUDA (preko JetPack okruženja)
- TAO DeepStream aplikacije (deepstream_tao_apps)

## Instalacija DeepStream 7.1

DeepStream 7.1 je instaliran prema službenim uputama:

https://docs.nvidia.com/metropolis/deepstream/7.1/text/DS_Installation.html

Za instalaciju je korištena metoda 1 ( Using SDK Manager )

## Preuzeti kod 

Korišten je službeni NVIDIA repozitorij:

https://github.com/NVIDIA-AI-IOT/deepstream_tao_apps

Grana/verzija: `release/tao_ds7.1ga`

Konkretno, pratila sam upute iz:

https://github.com/NVIDIA-AI-IOT/deepstream_tao_apps/blob/release/tao_ds7.1ga/apps/tao_others/README.md

Nakon kloniranja repozitorija na Jetson, preuzela sam potrebne modele i konfiguracije prema navedenim uputama.

## Moje izmjene

U odnosu na originalni NVIDIA kod, promijenila sam samo dvije datoteke kako bi se primjer ispravno pokrenuo na mom uređaju. Ostatak projekta je ostao isti kao u originalnom repozitoriju.

Detalji izmjena su vidljivi kroz commitove u ovom repozitoriju.

## Pokretanje

Pokretanje je rađeno prema uputama iz NVIDIA README-a za `tao_others` aplikacije, uz moje dvije lokalne izmjene konfiguracije/koda.

Napomena: potrebno je imati ispravno postavljen JetPack i instaliran DeepStream SDK 7.1 na Jetson uređaju.

## Reference

- NVIDIA DeepStream 7.1 dokumentacija:
  https://docs.nvidia.com/metropolis/deepstream/7.1/

- NVIDIA deepstream_tao_apps repo:
  https://github.com/NVIDIA-AI-IOT/deepstream_tao_apps
