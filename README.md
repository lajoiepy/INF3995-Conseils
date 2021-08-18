# INF3995 - Informations utiles et conseils

# Crazyflie

- Lors de l'assemblage d'un Crazyflie, faites très attention d'installer les expansion decks (optical flow et ranging) du bon côté. Voir [indications](https://www.bitcraze.io/documentation/tutorials/getting-started-with-expansion-decks/).

- Pour changer la configuration persistente d'un Crazyflie (adresse radio, canal, etc.): Suivez ces [indications](https://github.com/bitcraze/crazyflie-lib-python/blob/master/docs/development/eeprom.md) en utilisant ce [script](https://github.com/bitcraze/crazyflie-lib-python/blob/master/examples/write-eeprom.py).

- Pour démarrer avec le Crazyfly et installer les outils de diagnostique suivez ce [tutoriel](https://www.bitcraze.io/documentation/tutorials/getting-started-with-crazyflie-2-x/)

- Il est conseillé de faire un premier test avec [app_push_demo](https://github.com/bitcraze/crazyflie-firmware/tree/master/examples/demos/app_push_demo) pour vérifier que le matériel fonctionne bien.

- Lorsque vous pensez qu'une pièce est défectueuse, commencez par faire des tests pour isoler cette pièce et confirmez cette hypothèse. Par exemple, retirez la pièce elle-même ou une autre et observez le comportement. [Autre conseils de déboggage](https://www.bitcraze.io/support/troubleshooting/).

- Pour un exemple de communication entre une station au sol et un Crazyflie à travers la Crazyradio, regardez cet [exemple](https://github.com/bitcraze/crazyflie-firmware/tree/master/examples/app_appchannel_test).

- Si le drone ne veut pas décoller ou que les données des capteurs de distance semblent erronées lorsqu'au sol: essayez de faire décoller le drone quelques centimètres au dessus du sol, à l'aide d'une petite boîte par exemple.

- Si vous souhaitez utiliser Buzz sur les Crazyflies, il vous faut utiliser la [version pour micro-controleur](https://github.com/MISTLab/BittyBuzz).

- Pour flash le drone par le biais de la radio, il vous sera utile de consulter [la documentation du bootloader](https://www.bitcraze.io/documentation/repository/crazyflie-clients-python/master/functional-areas/cfloader/).

# Simulation ARGoS

- Afin d'utiliser le modèle de Crazyflie dans le simulateur vous devez utiliser la version MISTLab du code source sur la branche [inf3995](https://github.com/MISTLab/argos3). Un exemple d'utilisation du modèle et des senseurs est disponible [ici](https://github.com/MISTLab/argos3-examples/blob/inf3995/experiments/crazyflie_sensing.argos).

- Voir cette [documentation pour installer Docker](https://docs.docker.com/get-docker/).

- Pour utiliser le simulateur dans Docker ainsi que l'exemple mentionné précédemment, il est recommendé de commencer à partir de l'[image Docker fournie ici](https://github.com/lajoiepy/argos3_docker_example).

- Pour le développement, il est conseillé d'utiliser [VSCode](https://code.visualstudio.com/) avec l'extension [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers). Des instructions pour débugger le code du simulateur dans Docker sont aussi diponibles [ici](https://github.com/lajoiepy/argos3_docker_example).

- Le code de votre contrôleur de robot (le cerveau) sera en C++, mais vous pouvez faire des hooks vers d'autres langages si vous voulez. Si [Buzz](https://github.com/MISTLab/Buzz) vous intéresse, c'est aussi compatible avec argos3. Une [extension minimale](https://github.com/samarseneault/buzz-vscode-extension) est disponible pour faciliter le développement Buzz. 

- Le simulateur a déjà [plusieurs modèles de robots disponibles](https://github.com/MISTLab/argos3/tree/inf3995/src/plugins/robots), mais vous pouvez fork/copier le repository et ensuite en ajouter d'autres ou modifer leurs attributs, pour ajouter un senseur au robot par exemple. Si vous modifiez le simulateur, n'oubliez pas de faire un mirroir ou une copie sur votre GitLab. Il y a aussi des exemples de simulation, de contrôleurs et de comportement de robots [ici](https://github.com/MISTLab/argos3-examples). Voir plus haut pour l'exemple du cours avec le Crazyflie.

- Il est déconseillé de travailler dans une VM compte tenu des fréquents problèmes d'IO et de partage de carte graphique. Il est préférable d'oeuvrer sur Linux natif. Voir tutoriel [dualboot Ubuntu/Windows](https://itsfoss.com/install-ubuntu-1404-dual-boot-mode-windows-8-81-uefi/)
