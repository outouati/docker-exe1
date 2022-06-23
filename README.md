# docker-exo01do
#####
# Creer un repo github nommé **docker-exo01**
## *** public, le fichiers (README.md , .gitignore valable pour le langage Python, une License MIT
# Faire un git clone dans votre directory project local
git clone https://github.com/outouati/docker-exo01.git
# repertoire de travail
cd docker-exo01
# commande docker run etre en interactif et avec un tty pour le display le container nommé **myalpes**
# creer un volume /MountPoint image doit etre alpine passer la commande /bin/ash
docker run -it --name myalpes -v /MountPoint alpine /bin/ash
## creer un fichier test.py inserez le texte *WARNING: ret pointer is null*
vi test.py
# créer une image docker nommée  myalpine:v12.
docker commit myalpes myalpine:v12
# afficher les images
docker images
# Verifier aavec docker history
docker history myalpine:v12
# * Supprimer les metadata de cette image avec docker export et docker import
docker export myalpes > docker6exo01.tar
cat docker6exo01.tar | docker import - alpine:v1
docker history myalpine:v12
# mettez cette image dans docker hub sous votre compte docker hub
# authentification login et password
docker login -u outouati -p m@yate12CPI16
# taguer l'image 
docker image tag myalpine:v12 outouati/myalpine:v12
# pousser l'image sur mon compte socker
docker push outouati/myalpine:v12

