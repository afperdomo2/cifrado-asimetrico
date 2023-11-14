# Cifrado asimétrico

### 🧑‍🏫Preguntas orientadoras

#### ¿Qué son las claves públicas y privadas?

Las claves publicas y privadas hacen parte del criptosistema asimétrico. En este criptosistema se crea un par de claves relacionadas matemáticamente (la clave publica y la clave privada). Este par de claves de usan para encriptar y desencriptar información o mensajes, permitiendo a los usuarios intercambiar información de forma segura (Paredes, G. G, 2006).

Si un usuario genera el par de claves, este puede compartir la clave publica para que los demás usuarios puedan intercambiar mensajes cifrados, esto ayuda a que la información no pueda ser leída o interpretada por terceros y se conserve su confidencialidad. Una vez el usuario recibe el mensaje cifrado, se hace uso de la clave privada para descifrarlo. Para realizar el proceso de cifrado o encriptación y desencriptación, se debe hacer uso o implementación de algoritmos de cifrado, uno de estos es RSA  9Rivest-Shamir-Adleman). Este es un algoritmo usado en criptográfica de clave publica y se basa en la dificultad de factorizar grandes números primos, a través del uso de las dos claves mencionadas anteriormente (Hernández Encinas, L, 2005).


#### ¿Qué es la firma digital y cuál es su importancia?

La firma digital es otra funcionalidad que se puede realizar usando los criptosistemas de clave pública, como se mencionó en la pregunta anterior. Para crear una firma digital, el usuario debe contar con una clave publica y privada relacionadas matemáticamente. El usuario puede hacer uso de su clave privada para firmar documentos, contratos, mensajes, certificados digitales, archivos, entre otros. Cualquier usuario que tenga acceso a la clave publica, puede validar la autenticidad de la firma digital aplicada a los documentos, garantizado que la información o los documentos no han sido alterados (García, F. Y. H, 2018).

---

### 🔏Criptosistemas de clave pública

#### 1.	¿Qué es el criptosistema de clave pública?

Es también conocido como criptografía o cifrado asimétrico. Es un sistema criptográfico que hace uso de un par de claves (publica y privada) relacionadas matemáticamente, a diferencia que el sistema simétrico que solo usa una (Franchi, M. R, 2012).

Algunos usos que se le pueden dar con la implementación de este criptosistema son los siguientes:

- Cifrado y descifrado de mensajes
- Generación y validación de firmas digitales, para firmar documentos, archivos, certificados, etc
- Autenticación para poder confirmar la identificación de una de las partes (o varias)


#### 2.	¿Cómo funciona y cuáles son sus algoritmos representativos?

#### 3.	Ventajas, desventajas y diferencias con el criptosistema simétrico

| Característica                  | Cifrado Simétrico                                   | Cifrado Asimétrico                                                                           |
| ------------------------------- | --------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| **Claves**                      | Usa una sola clave para cifrado y descifrado        | Par de claves relacionadas matemáticamente: pública y privada                                |
| **Distribución de Claves**      | Es más difícil de gestionar de manera segura        | La clave pública puede ser compartida abiertamente. La clave privada debe mantenerse secreta |
| **Seguridad**                   | Menos seguro si las claves son comprometidas        | Más seguro en términos de distribución de claves                                             |
| **Ejemplos de Algoritmos**      | DES, AES                                            | RSA, ECC                                                                                     |
| **Uso Común**                   | Transferencia segura de grandes cantidades de datos | Establecimiento seguro de conexiones y autenticación                                         |
| **Ejemplo de Aplicación**       | Encriptación de archivos locales                    | SSL/TLS para transacciones seguras en línea                                                  |
| **Eficiencia Energética**       | Más eficiente para grandes cantidades de datos      | Menos eficiente para grandes volúmenes de datos debido a la complejidad computacional        |
| **Ejemplo de Escenario de Uso** | Copias de seguridad de datos                        | Autenticación segura en comunicaciones en línea                                              |

#### 4.	Caso práctico de aplicación (qué algoritmo, dónde y cómo usarlo)

#### 5.	Observaciones y recomendaciones para implementar el criptosistema

---

### 📚Bibliofrafía

Paredes, G. G. (2006). Introducción a la criptografía. Obtenido de: https://dialnet.unirioja.es/servlet/articulo?codigo=5286657

Hernández Encinas, L. (2005). El criptosistema RSA. RA-MA Editorial. Obtenido de https://digital.csic.es/handle/10261/15961

García, F. Y. H. (2018). Análisis de la firma digital con base en la infraestructura de clave pública. Hamut´ ay, 5(2), 95-105. Obtenido de https://dialnet.unirioja.es/servlet/articulo?codigo=6801245

Franchi, M. R. (2012). Algortimos de encriptación de clave asimétrica (Doctoral dissertation, Universidad Nacional de La Plata). Obtenido de http://sedici.unlp.edu.ar/handle/10915/26137
