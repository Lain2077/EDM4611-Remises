Pour des projets futurs, je voulais me familiariser avec l'api automatic1111 dans TouchDesigner. Grâce au tox de Olegchomp, une grosse partie de la tâche se facilite.

L'idée était de faire un simulateur de planet aux allures futuristiques.

Le patch est divisé en 4 parties visuelles et 1 bloc api

En premier lieu, le prompt est formé avec un string permanent et le string variable, afin de préserver une ligne directrice et le lora dans le prompt

Une fois l'image de 512/1024 generée, celle-ci est appliquée en color map de la sphere, et est par la suite tranformé pour la normal map et la height map

J'en profite au passage pour parse la couleur maximum dans l'image afin de la configurer comme "emitment" 

La grille est quant à elle entierement mappé sur un noise et sa normal auquel j'ai ajouté un rectangle pour applatir les variations à un endroit donné

L'anneau tournant est simple, avec une rampe pour la scale du fractal qui donne un petit éffet. S'en suit un feedback loop pour en rajouter

Les étoiles sont ensuite ajoutée à la toute fin, et translated vers le haut pour matcher la perspective de la grille

Au final, le résultat est concret, efficace selon moi. Si les modèles utilisés étaient plus précis, la génération de texture pourrait vraiment être divertissante et originale.