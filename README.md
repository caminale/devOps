# devOps

###ssh tuto :[ici](https://doc.fedora-fr.org/wiki/SSH_:_Authentification_par_cl%C3%A9)

crée une clé ssh sur le host : ssh-keygen 
(par défaut clé rsa en 2048 bits)
mv notrecléssh.pub authorized_keys

pour les vm si on veut rester sur un seul coeur, et qu'on a pas assez de ram, il est préférable 
de créer du swap, suivre [ce tuto](https://www.digitalocean.com/community/tutorials/how-to-add-swap-on-ubuntu-14-04)