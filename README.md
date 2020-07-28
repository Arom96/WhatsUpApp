# Examen Bimestral - Tópicos Especiales
## WhatsUpApp

# Integrantes

* Aarón Cruz
* Estefanía Aguilar

# Introducción

El presente proyecto simula una aplicación de chat interactivo entre dos o mas usuarios.desarrollada en Android Studio 4.0 conectada a una base de datos de Firebase.

# Funcionalidades.

La aplicación inicia en una pantalla con dos botones los cuales realizan las siguientes funciones:
* Botón para el Inicio de Sesión.- Valida que el usuario este registrado.
* Botón para Registrarse.- Registra usuarios que no tengan una cuenta.
Una pantalla de Inicio de Sesión que valida la autenticación de usuarios.
/n Una pantalla de registro que valida todos los campos y la contraseña que tenga una longitud de mínimo 6 caracteres.

# API utilizada.

La aplicación se desarrollo con una API 24 (Android Lollipop 7.0), esto quiere decir que la aplicación va a funcionar en dispositivos móviles con Android 7.0 en adelante.

# Modelos de celulares probados.

* Emulador Android Nexus 5 con versión 7.0
* Huawei P30 LITE con versión 9.0
* Huawei MATE 20 LITE con versión 9.0
* Xiaomi Redmi 8 versión 8.0
* Samsumg A20 con versión 9.0

# Explicación de código.

* Creamos la clase Users, para crear el objeto usuario.
* Creamos la clase Chats para el objeto chat.
* Creamos la Clase Chatlist para tener la referencia de la sala de chat.

Varibales que nos permiten leer y escribir datos en la base de Firebase:

    FirebaseUser fuser;
    DatabaseReference reference;
    FirebaseStorage storage;
    StorageReference storageReference;
    FirebaseAuth ------> Validar Autenticaciones de usuarios registrados.

En nuestra clase MessageActivity mapeamos como va se van a guardar los chats en Firebase con el siguiente código:

    DatabaseReference reference = FirebaseDatabase.getInstance().getReference();

        HashMap<String, Object> hashMap = new HashMap<>();
        hashMap.put("sender", sender); // Tomamos el id de quien envió el mensaje 
        hashMap.put("receiver", receiver); //Tomamos el id de quien recibe el mensaje
        hashMap.put("message", message); //Tomamos el mensaje que fue enviado
        hashMap.put("isseen", false); // Para comprobar si el mensaje fue leido

        reference.child("Chats").push().setValue(hashMap);

Para poder enviar imágenes de nuestra galeria debemos asignar dos atributos en el archivo AndroidManifest estos son de lectura y escritura como se muestra a continuación:

    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />


# Fuente de referencia.

KOD Dev
https://www.buymeacoffee.com/koddev
https://www.youtube.com/watch?v=fJWFeW09qeE&list=PLzLFqCABnRQftQQETzoVMuteXzNiXmnj8&index=1
