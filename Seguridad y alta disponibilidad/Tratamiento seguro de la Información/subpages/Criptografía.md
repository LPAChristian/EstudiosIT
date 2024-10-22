
> [!NOTE] Definición de RAE
> Arte de escribir con clave secreta o de un modo enigmático.

La criptografía es un **proceso en el que un mensaje se cifra, por lo tanto se protege, utilizando algoritmos y claves secretas o públicas que solamente deben conocer el emisor y el receptor del mensaje.**

Existen diferentes sistemas de cifrar la información, a estos sistemas se les denomina **criptosistemas**, que según la clave empleada se pueden clasificar en:
1. Sistemas simétricos
2. Sistemas asimétricos

---
## Sistemas simétricos

Los sistemas simétricos son aquellos en los que el emisor y el receptor utilizan la misma clave para cifrar y descifrar los mensajes.
Las dos partes que se comunican han de ponerse de acuerdo de antemano sobre la clave a usar, por tanto, la seguridad de este sistema reside en mantener en secreto la clave compartida.
![[Sistema simétrico.png]]
Este método tiene dos desventajas:
1. Dificultad para realizar el intercambio de llaves inicial de manera segura.
2. Cantidad de claves que las entidades que participan en la comunicación deben almacenar.
El beneficio clave de este método reside en **la rapidez del cifrado/descifrado.**

---
## Sistemas asimétricos

Los sistemas asimétricos utilizan dos claves, **una privada y otra pública**, para cifrar y descifrar la información.

En este método de criptografía, el emisor cifra el mensaje con una de las dos llaves y debe conseguir que el receptor utilice la otra para descifrarlo.

![[Sistema asimétrico.png]]

Estas dos llaves se crean al mismo tiempo utilizando algoritmos matemáticos particulares que hacen que su computación sea fácil, mientras que su inversión resulta extremadamente difícil. Gracias a esto, resulta imposible descubrir la clave privada a partir de la clave pública.

