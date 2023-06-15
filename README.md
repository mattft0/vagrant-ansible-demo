# Utiliser Vagrant et Ansible pour créer une machine admin et une machine MySQL
Ce dépôt contient un ensemble de fichiers et d'instructions pour effectuer une démo avec Vagrant et Ansible afin de créer une machine administrateur (admin) et une machine MySQL, en utilisant Ansible pour configurer leur communication.

## Prérequis
Avant de commencer, assurez-vous d'avoir les éléments suivants installés sur votre système :

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)
- [Ansible](https://www.ansible.com/)

## Instructions
Clonez ce dépôt sur votre machine locale :

```bash
git clone https://github.com/mattft0/vagrant-ansible-demo.git
```
Démarrez les machines virtuelles à l'aide de Vagrant :

```bash
vagrant up
```
Cette commande va créer et provisionner les machines virtuelles admin et mysql en utilisant les fichiers de configuration Vagrant et Ansible fournis.


Vérifiez que les machines ont été créées avec succès :

```bash
vagrant status
```
Vous devriez voir les deux machines, admin et mysql, en état de fonctionnement.

Accédez à la machine admin :

```bash
vagrant ssh admin
```
Une fois connecté à la machine admin, vous pouvez vérifier la communication avec la machine MySQL :

```bash
ping mysql
```
Si la communication est établie, vous devriez recevoir une réponse du serveur MySQL.

Vous pouvez également vous connecter à la machine MySQL pour effectuer des opérations supplémentaires :

```bash
vagrant ssh mysql
```
Lorsque vous avez terminé le test, vous pouvez arrêter et supprimer les machines virtuelles :

```bash
vagrant destroy -f
```
Cette commande arrêtera et supprimera complètement les machines virtuelles créées lors du test.

## Structure du dépôt
Vagrantfile : Le fichier de configuration Vagrant qui spécifie les détails des machines virtuelles à créer.

inventory.ini : Le fichier d'inventaire Ansible qui définit les machines à provisionner.

playbook.yml : Le playbook Ansible qui configure la communication entre la machine admin et la machine MySQL.
Personnalisation

Si vous souhaitez personnaliser les machines ou ajouter des étapes de configuration supplémentaires, vous pouvez modifier les fichiers Vagrantfile et les fichiers de configuration Ansible en fonction de vos besoins.

> Note: Assurez-vous de disposer des droits et des autorisations appropriés pour créer des machines virtuelles et effectuer des opérations de provisionnement sur votre système.
