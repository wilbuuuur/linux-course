# h6 Real Internet(tm)

## x) [artikkeli](https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/)

Tero Karvisen artikkeli kertoo oman palvelimen luomisen alkuvaiheista.

- salasanojen pitää olla aina vahvoja vaikka niitä käyttäisi lyhyen ajan
- ennen palomuurin kytkemistä päälle on siihen tehtävä aukko ssh:lle
- pakettien päivittäminen on tärkeää tietoturvan kannalta

## a)

aloitus 7.2 / 16.50

Valitsin palveluntarjoajaksi [linoden](https://www.linode.com). Loin käyttäjä tunnuksen ja kirjauduin uudelle käyttäjälle. Kirjauduttuani aloitin palvelimen/linoden lumisen.

Valitsin Distribution kohtaan Debian11, sijainniksi Frankfurt, DE (eu-central) ja Linode Planiksi Shared CPU, nanode 1 GB

![image](https://user-images.githubusercontent.com/112497423/217285617-3df29965-e497-4ddc-971d-6a4a50545298.png)
 
näiden vaiheiden jälkeen valitsin linode palvelimelle haluamani labelin ja salasanan.
loin loin uuden avaimen komennolla:

       ssh-keygen
       
hain aviamen komennolla ` cat .ssh/id_rsa.pub ` kopioin avaimen avasin linodesta kohdan Add sn SHH Key ja sitten liitin avaimen SSH public key kohtaan ja laitoin avaimelle labelin.

Lopuksi painoin painiketta Create Linode tämän jälkeen palvelin on luotu.

## b)

aloitus 7.2 / 17.30

Aloitin käynnistämällä terminaalin ja ajamalla komennon 

    ssh root@172.104.240.183

palvelimella päivitin pakettitiedot ja asensin palomuurin komennoilla

    sudo apt-get update
    
    sudo apt-get install ufw
    
asennuksen jälkeen tein palomuuriin reiän shh:ta ja apachea varten

      sudo ufw allow 22/tcp
      
      sudo ufw allow 80/tcp
      
laitoin palomuurin päälle komennolla 

      sudo ufw enable
      
asensin apache2 komennoilla 
       
       sudo apt update 
       
       sudo apt install apache2
       
       sudo apt-get upgrade
       
seuraavaksi tein käyttäjän ja määritin sille salasanan komennoilla 

    sudo adduser hiiri
    sudo adduser hiiri sudo
    sudo adduser hiiri adm
    
Suljin root käyttäjän ja root ssh kirjautumisen komennolla: 

    sudo usermod --lock root
    sudoedit /etc/ssh/sshd_config
    
jälkimmäisen komennon jälkeen muokkasin kohtaa "PermitRootLogin"  arvoksi "no"
uudelleen käynnistys komennolla

    sudo service ssh restart


## c) 7.2 / 18.30

Muokkasin index.html tiedostoa komennolla

    sudo nano /var/www/html/index.html
    
kuva lopputuloksesta

![image](https://user-images.githubusercontent.com/112497423/217325901-9362e08e-4fc5-4712-8995-f0bf2f6c2d81.png)

## d) 

aloitus 9.2 / 10.00

Etsin virheitä komennolla 

      cat /var/log/auth.log | nl

tuloksia oli yli +5000. huomasin että joukossa oli virheellisellä salasanalla kirjautumis yrityksiä. etsin uudestaan komennolla joka näyttää vain tulokset jotka sisältää sanan "Failed" ja numeroi ne 

    cat /var/log/auth.log | grep Failed | nl

![image](https://user-images.githubusercontent.com/112497423/217772243-bb75d1e9-32bb-4caa-9097-06dcf662c93c.png)


## Lähteet

https://www.linode.com

https://terokarvinen.com/

https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/

