# Cifrado asimétrico

### 🧑‍🏫Preguntas orientadoras

#### ¿Qué son las claves públicas y privadas?

Las claves públicas y privadas hacen parte del criptosistema asimétrico. En este criptosistema se crea un par de claves relacionadas matemáticamente (la clave pública y la clave privada). Este par de claves de usan para encriptar y desencriptar información o mensajes, permitiendo a los usuarios intercambiar información de forma segura (Paredes, G. G, 2006).

Si un usuario genera el par de claves, este puede compartir la clave pública para que los demás usuarios puedan intercambiar mensajes cifrados, esto ayuda a que la información no pueda ser leída o interpretada por terceros y se conserve su confidencialidad. Una vez el usuario recibe el mensaje cifrado, se hace uso de la clave privada para descifrarlo. Para realizar el proceso de cifrado o encriptación y desencriptación, se debe hacer uso o implementación de algoritmos de cifrado, uno de estos es RSA (Rivest-Shamir-Adleman). Este es un algoritmo usado en criptográfica de clave pública y se basa en la dificultad de factorizar grandes números primos, a través del uso de las dos claves mencionadas anteriormente (Hernández Encinas, L, 2005).

#### ¿Qué es la firma digital y cuál es su importancia?

La firma digital es otra funcionalidad que se puede realizar usando los criptosistemas de clave pública, como se mencionó en la pregunta anterior. Para crear una firma digital, el usuario debe contar con una clave pública y privada relacionadas matemáticamente. El usuario puede hacer uso de su clave privada para firmar documentos, contratos, mensajes, certificados digitales, archivos, entre otros. Cualquier usuario que tenga acceso a la clave pública, puede validar la autenticidad de la firma digital aplicada a los documentos, garantizado que la información o los documentos no han sido alterados (García, F. Y. H, 2018).

---

### 🔏Criptosistemas de clave pública

#### 1. ¿Qué es el criptosistema de clave pública?

Es también conocido como criptografía o cifrado asimétrico. Es un sistema criptográfico que hace uso de un par de claves (pública y privada) relacionadas matemáticamente, a diferencia que el sistema simétrico que solo usa una (Franchi, M. R, 2012).

Algunos usos que se le pueden dar con la implementación de este criptosistema son los siguientes:

- Cifrado y descifrado de mensajes
- Generación y validación de firmas digitales, para firmar documentos, archivos, certificados, etc.
- Autenticación para poder confirmar la identificación de una de las partes (o varias)

#### 2. ¿Cómo funciona y cuáles son sus algoritmos representativos?

##### 2.1 Funcionamiento

Primero se debe seleccionar un algoritmo de encriptación asimétrico como puede ser RSA (Rivest-Shamir-Adleman) o DSA (Digital Signature Algorithm) que son los más conocidos. Luego con el algoritmo seleccionado, se deben crear el par de claves (pública y privada) relacionadas matemáticamente. Esto permite que la información cifrada con una clave, puede ser descifrada con la otra (Hernández Encinas, L, 2005).

##### 2.2 Algoritmos

- RSA (Rivest-Shamir-Adleman): Este es un algoritmo usado en criptográfica de clave pública y se basa en la dificultad de factorizar grandes números primos, a través del uso de las dos claves mencionadas anteriormente.
- DSA (Digital Signature Algorithm): Es un algoritmo criptográfico usado principalmente en la generación y gestión de firmas digitales.
- ElGamal: Este es un algoritmo de cifrado y firma, basado en la dificultad de calcular logaritmos discretos en un cuerpo finito.
- ECC (Elliptic Curve Cryptography): Algoritmo para establecimiento de claves seguras. Ofrece la misma seguridad que RSA, pero lo realiza con claves más cortas, haciéndolo eficiente en términos de uso de recursos.

#### 3. Ventajas, desventajas y diferencias con el criptosistema simétrico

| Característica                  | Cifrado Simétrico                                   | Cifrado Asimétrico                                                                           |
| ------------------------------- | --------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| **Claves**                      | Usa una sola clave para cifrado y descifrado        | Par de claves relacionadas matemáticamente: pública y privada                                |
| **Distribución de Claves**      | Es más difícil de gestionar de manera segura        | La clave pública puede ser compartida abiertamente. La clave privada debe mantenerse secreta |
| **Seguridad**                   | Menos seguro si las claves son comprometidas        | Más seguro en términos de distribución de claves                                             |
| **Ejemplos de Algoritmos**      | DES, AES, Twofish, Chacha20                         | RSA, ElGamal, DSA, Diffie-Hellman, ECC, Lattice-based-cryptography                           |
| **Uso Común**                   | Transferencia segura de grandes cantidades de datos | Establecimiento seguro de conexiones y autenticación                                         |
| **Ejemplo de Aplicación**       | Encriptación de archivos locales                    | SSL/TLS para transacciones seguras en línea                                                  |
| **Eficiencia Energética**       | Más eficiente para grandes cantidades de datos      | Menos eficiente para grandes volúmenes de datos debido a la complejidad computacional        |
| **Ejemplo de Escenario de Uso** | Copias de seguridad de datos                        | Autenticación segura en comunicaciones en línea                                              |

#### 4. Caso práctico de aplicación (qué algoritmo, dónde y cómo usarlo)

A continuación, se realiza un caso práctico de criptográfica asimétrica, usando Python 3:

Primero se debe instalar la librería de **pycryptodome** en la carpeta donde se vaya a realizar el ejercicio.

```python
pip install pycryptodome
```

Luego, se procede a crear el archivo de Python:

🗃️**Archivo:** cifrado_asimetrico.py

```python
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# 1. Cifrado

# Generar una nueva clave RSA de 2048 bits
clave_privada = RSA.generate(2048)
clave_publica = clave_privada.publickey()

# Guardar la clave pública en un archivo PEM
clave_publica_path = "clave_publica.pem"
with open(clave_publica_path, "wb") as archivo_clave_publica:
    archivo_clave_publica.write(clave_publica.export_key())

# Guardar la clave privada en un archivo PEM (asegúrate de protegerlo adecuadamente)
clave_privada_path = "clave_privada.pem"
with open(clave_privada_path, "wb") as archivo_clave_privada:
    archivo_clave_privada.write(clave_privada .export_key())

# Cifrar un mensaje utilizando la clave pública
mensaje = "Esto es un mensaje cifrado con criptografía asimétrica y RSA"
mensaje_bytes = mensaje.encode("utf-8")

# Crear un cifrador con el algoritmo de cifrado PKCS1_OAEP y la clave pública
cifrador = PKCS1_OAEP.new(clave_publica)

# Aplicar el cifrado al mensaje
mensaje_cifrado = cifrador.encrypt(mensaje_bytes)

# Guardar el mensaje cifrado en un archivo text
mensaje_cifrado_path = "mensaje_cifrado.txt"
with open(mensaje_cifrado_path, "wb") as archivo_cifrado:
    archivo_cifrado.write(mensaje_cifrado)

# 2. Decifrado

# Cargar la clave privada desde un archivo PEM
clave_privada_path = "clave_privada.pem"
with open(clave_privada_path, "rb") as archivo_clave_privada:
    clave_privada = RSA.import_key(archivo_clave_privada.read())

# Descifrar el mensaje cifrado desde un archivo binario
mensaje_cifrado_path = "mensaje_cifrado.txt"
with open(mensaje_cifrado_path, "rb") as archivo_cifrado:
    mensaje_cifrado = archivo_cifrado.read()

# Crear un objeto descifrador utilizando la clave privada
cifrador = PKCS1_OAEP.new(clave_privada)

# Descifrar el mensaje cifrado
mensaje_descifrado_bytes = cifrador.decrypt(mensaje_cifrado)

# Decodificar el mensaje descifrado a una cadena de texto
mensaje_descifrado = mensaje_descifrado_bytes.decode("utf-8")

# Imprimir el mensaje descifrado
print("Mensaje descifrado:")
print(mensaje_descifrado)
```

---

### 📚Bibliofrafía

Paredes, G. G. (2006). Introducción a la criptografía. Obtenido de: https://dialnet.unirioja.es/servlet/articulo?codigo=5286657

Hernández Encinas, L. (2005). El criptosistema RSA. RA-MA Editorial. Obtenido de https://digital.csic.es/handle/10261/15961

García, F. Y. H. (2018). Análisis de la firma digital con base en la infraestructura de clave pública. Hamut´ ay, 5(2), 95-105. Obtenido de https://dialnet.unirioja.es/servlet/articulo?codigo=6801245

Franchi, M. R. (2012). Algortimos de encriptación de clave asimétrica (Doctoral dissertation, Universidad Nacional de La Plata). Obtenido de http://sedici.unlp.edu.ar/handle/10915/26137
