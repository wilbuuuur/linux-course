# linux-course
linux course assignments

## Linuxh1
### Install Debian on Virtualbox

### kone
-host OS: Windows 10
-cpu: intel i5-8400
-gpu: NVIDIA 1070i
-ram: 24Gb 


-lataa virtuaali kone (Oracle VM VirtualBox)
ja linux ( debian-live-11.6.0-amd64-xfce+nonfree.iso )

- käynnistä virtuaalikone 
- tee uusi virtuaalikone (new)
![image](https://user-images.githubusercontent.com/112497423/212957914-8bec750e-bff1-439d-8299-78ec113d1632.png)

#### Name and Operating System
- nimeä virtuaalikone
- valitse ISO image (ladattu debian)
- tyyppi linux

![image](https://user-images.githubusercontent.com/112497423/212957001-8a654252-bfaa-4459-ab54-081e42e9020e.png)

#### Unattended Install
-vaihda tunnukset


![image](https://user-images.githubusercontent.com/112497423/212957072-0d772f68-32d5-4323-b97c-753884d14dfa.png)

#### Hardware
-base memory: laitoin 6000MB
-processors: laitoin 4

![image](https://user-images.githubusercontent.com/112497423/212957115-85284ed2-64a7-4401-9ff1-9229773b2e30.png)

#### Hard Disk
-Hard Disk size: 60GB
-Hard Disk File: VDI VirtualBox Disk Image

![image](https://user-images.githubusercontent.com/112497423/212957260-3231c07f-df3e-40bb-8e30-0fce1625d029.png)

-Valitse Debian Installer

![image](https://user-images.githubusercontent.com/112497423/212958848-8dba1dd6-7dea-440c-89c9-288b61ca4cb8.png)

-valitse käyttökieli, sijainti ja näppäimistön tyyppi

-valitse Erase disk
![image](https://user-images.githubusercontent.com/112497423/212964773-96541698-aa2c-4e43-82fe-36be34af8298.png)

-täytä tiedot
![image](https://user-images.githubusercontent.com/112497423/212965319-08cb7e38-1cb8-4328-a100-a13e0f3e20de.png)

-install
![image](https://user-images.githubusercontent.com/112497423/212966030-7c6e2bb3-195e-45d9-bce0-de6edef85204.png)

Asennuksen jälkeen
suorita seuraavat komennot terminaalissa: sudo apt-get update, sudo apt-get -y dist-upgrade, sudo apt-get -y install ufw, sudo ufw enable
