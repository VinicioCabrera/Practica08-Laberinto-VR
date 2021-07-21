# Practica08-Laberinto-VR
Crear la GVR Camera Rig 
Durante este paso, crearemos la cámara VR incluyendo el GvrEditorEmulator en la escena y configurando la cámara. 
1.	Agregue el objeto prefab GvrEditorEmulator a la escena. 

![image](https://user-images.githubusercontent.com/49033433/126419950-3be74d39-0e86-4318-8912-df3d2ca7f1ba.png)

2.	Convierta el objeto Main Camera en un elemento hijo del objeto GvrEditorEmulator. 

![image](https://user-images.githubusercontent.com/49033433/126420030-b43ffd85-280a-4d72-a386-35276e5ccc42.png)

3.	Restablece el componente Transformar del objeto Main Camera 
4.	Mueva el objeto GvrEditorEmulator a una ubicación conveniente para el desarrollo, por ejemplo, Posición: 0, 3, 35 y Rotación: 0, 180, 0.

![image](https://user-images.githubusercontent.com/49033433/126420131-2a30dcb4-affa-4efb-9868-308d80e5d82f.png)

Preparando la escena para la interacción 
Durante este paso, prepararemos la escena para la interacción configurando el puntero, el emisor de rayos y el sistema de eventos, y luego probaremos el sistema de punto de referencia incluido (waypoint). 
1.	Agregue el objeto prefab GvrReticlePointer a la escena como elemento secundario del objeto del Main Camera. 

![image](https://user-images.githubusercontent.com/49033433/126420163-68bf04a3-d12f-4258-94aa-6725e0d912cc.png)

2.	Aumente el valor de Distancia máxima de retícula para el GvrReticlePointer del valor predeterminado de 10 a 20. 

![image](https://user-images.githubusercontent.com/49033433/126420196-b2a99e1c-ca25-4440-bbb8-1dc52cea5f02.png)


3.	Agregue el script GvrPointerPhysicsRaycaster como componente en el objeto Main Camera. 

![image](https://user-images.githubusercontent.com/49033433/126420232-9d6f5390-9b54-47eb-9f08-539c1c9d91e3.png)

4.	Agregue el objeto prefab GvrEventSystem a la escena. 

![image](https://user-images.githubusercontent.com/49033433/126420255-d1ca0a36-ef29-4952-b901-63aac48331b4.png)

5.	Ingrese al modo de juego y navegue por la escena haciendo clic en los puntos de referencia. 

![image](https://user-images.githubusercontent.com/49033433/126420279-058d97cb-5626-4345-82ec-ed6385f59350.png)

Hacer que los objetos del juego sean interactivos 
Durante este paso haremos que la Moneda, la Llave y la Puerta sean interactivas añadiéndoles componentes de disparadores y eventos. 

1.	Localiza y selecciona el objeto  Coin en la jerarquía. 

![image](https://user-images.githubusercontent.com/49033433/126420344-ade67de3-56e4-4048-985b-03d659cdceb0.png)

2.	Verifique que tenga un componente Collider. 

![image](https://user-images.githubusercontent.com/49033433/126420397-47a5f812-939b-44bc-89ba-67f6ba040d01.png)

3.	Agregue el script Coin proporcionado como componente. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126420446-5e0d952d-fc0e-47c0-934c-05ae6747bc5b.png)

4.	Agregue un dispardor de evento (Event Trigger) como componente. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126420459-d081a2af-8af7-4a39-a411-ddcf60bdd73c.png)

5.	Agregue el evento PointerClick al componente Event Trigger. 

![image](https://user-images.githubusercontent.com/49033433/126420479-a76b0c74-1eb5-4ee2-923b-5113e30be615.png)

6.	Asigne el componente del script Coin al campo de objeto del evento Pointer Click. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126420520-42a9241a-9685-4465-a2ae-ca0526adde7e.png)

7.	Asigne el método Coin.OnCoinClicked () como la función para el evento Pointer Click. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126420734-d5c0b9bc-457c-49e9-9b29-bb9a19e1781a.png)
 
8.	Ingrese al modo de juego, haga clic en la moneda y verifique que el mensaje 'Coin.OnCoinClicked ()' esté impreso en la ventana de la consola. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126420746-b9a4d850-824a-4da6-8cee-028d0ae381af.png)

9.	Repita el mismo proceso para el objeto del juego Key pero use el script Key y el método Key.OnKeyClicked (). 
 
![image](https://user-images.githubusercontent.com/49033433/126420767-0ea5c8dd-cfcb-4756-8491-97d141b80283.png)

10.	Repita el mismo proceso para el primer objeto principal del juego de Puerta, pero use el script de Puerta y el método Door.OnDoorClicked (). 
 
![image](https://user-images.githubusercontent.com/49033433/126420789-2a0e0510-ce04-42f2-a751-309a4f006d58.png)

Hacer la interfaz de usuario interactiva 
Durante este paso, haremos que el objeto SignPost sea interactivo al agregarle componentes de disparadores y eventos. El proceso es casi idéntico al que hicimos con la moneda, la llave y la puerta en el paso anterior, pero no necesitamos un colisionador para interactuar con los objetos del juego de la interfaz de usuario. En su lugar, debemos verificar que el objeto del juego Canvas tenga un componente Graphic Raycaster, y debido a que estamos usando GVR, reemplazaremos el Graphic Raycaster de Unity con el GvrPointerGraphicRaycaster de Google VR. 
1.	Localiza y selecciona el objeto del juego SignPost en la jerarquía. 
 
![image](https://user-images.githubusercontent.com/49033433/126420829-e5e8fb39-b4a2-4939-b67e-5f4f6740551a.png)

2.	Elimine el componente Graphic Raycaster que se agrega automáticamente al crear un nuevo objeto. 

![image](https://user-images.githubusercontent.com/49033433/126420879-62fc1d50-be4c-4ac9-b55c-98d83330da63.png)

3.	Agregue el script GvrPointerGraphicRaycaster como componente. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126421020-f2c91748-c1da-4529-876b-f87d81327136.png)

4.	Agregue el script SignPost proporcionado como componente. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126421039-c61f0a6f-3eb7-4b88-b3b0-a115e0fde2d6.png)

5.	Agregue un Event Trigger como componente. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126421053-0d35e325-10ce-4258-b514-3f189bde27b0.png)

6.	Agregue el evento PointerClick al componente Event Trigger. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126421070-2b3c559f-25e1-4a55-8630-458485b8ece3.png)

7.	Asigne el componente script SignPost al campo de objeto del evento Pointer Click.  

![image](https://user-images.githubusercontent.com/49033433/126421105-ead347d2-5f11-4b9e-bad7-621a0a44a9fe.png)

8.	Asigne el método SignPost.ResetScene () como la función para el evento Pointer Click. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126421162-72ff9ad5-c7b1-4d60-b6aa-90eb03eda7c8.png)

9.	Ingrese al modo de juego, haga clic en SignPost y verifique que el mensaje 'SignPost.ResetScene ()' esté impreso en la ventana de la consola. 
Programando el comportamiento de la moneda (coin) 
Durante este paso, programaremos el comportamiento de la moneda para que, cuando se haga clic en una moneda (coin), se reproduzca un sonido, muestre un efecto de "poof" y desaparezca. 
1.	Hay un mínimo de cinco monedas en el laberinto. Cuando se hace clic en una moneda, se reproduce un efecto de sonido en la ubicación de esa moneda.Cuando se hace clic en una moneda, esa moneda se elimina de la jerarquía de la escena. 
2.	Abra el script de Coin y lea todo el script, incluidos todos los comentarios. 
3.	Dedique un tiempo a comprender el comportamiento del objeto prefab CoinPoof proporcionado. Puede hacer esto, por ejemplo, ingresando al modo de juego y arrastrando un objeto prefab CoinPoof a la escena. 
4.	Programe el comportamiento de la moneda completando todos los comentarios TODO en el script. 

![image](https://user-images.githubusercontent.com/49033433/126421172-06f6b171-917e-4015-a124-a2b14e26e45b.png)
 
Programando el comportamiento de la llave (key) 
Durante este paso, programaremos el comportamiento de la llave (key) para que, cuando se haga clic en la llave, reproduzca un sonido, muestre un efecto de "poof" y desaparezca. 
1.	Hay un mínimo de una llave en el laberinto. Cuando se hace clic en la llave, se reproduce un efecto de sonido en la ubicación de la llave. Cuando se hace clic en la llave, la llave se elimina de la jerarquía de la escena. Cuando se hace clic en la llave, la puerta se desbloquea. 
2.	Abra el script key y lea completo, incluidos todos los comentarios. 
3.	Dedique un tiempo a comprender el comportamiento del objeto prefab KeyPoof proporcionado. Puede hacer esto, por ejemplo, ingresando al modo de juego y arrastrando un objeto prefab KeyPoof a la escena. 
4.	Programe el comportamiento key completando todos los comentarios TODO en el script.  

![image](https://user-images.githubusercontent.com/49033433/126421197-c6fa81d0-4961-409f-b3c5-1f92abba8c14.png)

Programando el comportamiento de la puerta (door) 
Durante este paso, programaremos el comportamiento de la puerta (door) para que cuando se haga clic en la llave (key), la Puerta se desbloquee y cuando se haga clic en la Puerta, se escuche un sonido y comience a girar a una posición de apertura. 
1.	La puerta evita que el usuario navegue al objeto SignPost hasta que se haya abierto. Cuando comienza el juego, la puerta está bloqueada y cerrada. La puerta no se puede abrir cuando está bloqueada. La puerta solo puede desbloquearse haciendo clic en la llave. Cuando se hace clic y se desbloquea la puerta, la puerta comienza a abrirse. Cuando la puerta comienza a abrirse, se reproduce un efecto de sonido en la ubicación de la puerta. La puerta se anima a una posición de abierta solo por código, es decir, no mediante el uso de animación y controlador de animador. 
2.	Abra el script Door y lea todo el script, incluidos todos los comentarios. 
3.	Agregue un componente AudioSource al primer objeto padre Door y desactive la propiedad Play On Awake. 
4.	Asigne el audio Door_Opening al campo AudioClip. 
5.	Programe el comportamiento de la puerta completando todos los comentarios TODO en el script. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126421279-5c10596c-2cd5-4534-818b-14c579a93c1e.png)

Programando el comportamiento del SignPost 
Durante este paso, programaremos el comportamiento de SignPost para que cuando se haga clic en SignPost se reinicie el juego. 
1.	El SignPost no se puede ver ni interactuar antes de que se abra la puerta. Cuando se hace clic en SignPost, la escena se restablece a su estado inicial para que el juego se pueda volver a jugar. 
2.	Abra el script SignPost y lea todo el script, incluidos todos los comentarios. 
3.	Programe el comportamiento SignPost completando todos los comentarios TODO en el script. 
 
 ![image](https://user-images.githubusercontent.com/49033433/126421256-aadb0f45-e3f2-498f-b996-94a81885ac10.png)

Crear la funcionalidad del juego 
Durante este paso, armaremos todo y convertiremos nuestro proyecto en un juego real. 
Waypoints 
• 	El laberinto está diseñado de tal manera que el usuario no puede identificar una ruta a la llave desde la posición de inicio.
 
![image](https://user-images.githubusercontent.com/49033433/126421237-205d1097-3a80-4d6f-b384-f38f385beb24.png)

