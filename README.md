# Mokepon

Este es el juego que hice mientras avanzaba en el curso de **Programación Básica** de Platzi. Es un juego de mascotas que se pelean entre sí, y aunque parece simple, para hacerlo tuve que entender cosas como el HTML, el CSS, las funciones, los objetos y, al final, cómo conectar el navegador con un servidor en Node.

Lo dejo público por si a alguien le sirve para practicar o para compararlo con su propio código.

## Cómo funciona el juego

Mokepon tiene tres pantallas y todo pasa dentro del navegador:

1. **Eliges tu mascota.** Hay tres: Hipodoge (va fuerte con agua), Capipepo (tierra) y Ratigueya (fuego). Cada una tiene sus propios ataques.
2. **Apareces en un mapa.** Tu mascota se mueve con el teclado y el juego va enviando tu posición al servidor todo el tiempo.
3. **Te encuentras con otro jugador.** Cuando tu mascota choca con la de otra persona, el mapa se cierra y empieza la pelea.

En la pelea cada uno elige 5 ataques (fuego, agua o tierra). Cuando los dos ya eligieron, el juego compara ataque por ataque y cuenta quién gana cada ronda:

- El fuego le gana a la tierra
- La tierra le gana al agua
- El agua le gana al fuego
- Si eligen lo mismo, es empate

Al final gana quien haya ganado más rondas.

## Qué necesitas para correrlo

Solo Node.js instalado. Si no lo tienes, se descarga desde [nodejs.org](https://nodejs.org). Con eso basta, porque el servidor está hecho con Express y ya viene declarado en el `package.json`.

## Cómo iniciarlo

Abre una terminal dentro de la carpeta del proyecto y escribe:

```bash
npm install
```

Eso descarga las dos librerías que usa el servidor (Express y CORS). Solo hay que hacerlo la primera vez.

Después arrancas el servidor:

```bash
node index.js
```

Si todo salió bien vas a ver el mensaje `Servidor funcionando`. Ahora abre el navegador en:

```
http://localhost:8080
```

Y ya está, ahí aparece la pantalla para elegir mascota.

Para apagar el servidor puedes presionar `Ctrl + C` en la terminal.

## Cómo jugar

1. Elige una mascota y dale a **Seleccionar**.
2. Muévete por el mapa con las **flechas del teclado**, o con los botones que aparecen en pantalla debajo del mapa (esos sirven para el celular).
3. Busca a otro jugador y choca con su mascota para empezar la pelea.
4. Elige tus 5 ataques con los botones de fuego, agua y tierra.
5. Cuando los dos terminen, abajo ves qué ataque sacó cada uno y el resultado.
6. Al terminar aparece el botón **Reiniciar**, que recarga la página para empezar de cero (vuelves a elegir mascota y a recorrer el mapa).

## Para probar el multijugador

El juego está pensado para dos personas, así que en tu computador puedes abrir **dos pestañas** o dos ventanas del navegador y jugar contra ti mismo. Cada pestaña entra como un jugador distinto.

Ojo con una cosa: el código apunta a `localhost:8080`, así que funciona en la misma computadora donde está corriendo el servidor. Si quieres jugar desde un celular o desde otro equipo conectado al mismo wifi, hay que cambiar `localhost` por la IP local de la computadora (algo como `192.168.1.x`) en las rutas que están dentro de `public/js/mokepon.js`. Es un cambio pendiente que me gustaría dejar automático más adelante.

## Qué hay en cada archivo y carpeta

```
index.js              el servidor: guarda jugadores, posiciones y ataques
package.json          las dependencias y la configuración del proyecto
public/index.html     la estructura de las tres pantallas
public/styles.css     los estilos
public/js/mokepon.js  toda la lógica del juego en el navegador
public/assets         las imágenes de las mascotas y del mapa
```

## Sobre el curso

Hice este proyecto con el curso **Programación Básica 2022** de Platzi, en la parte donde se programa tu primer videojuego desde cero:

https://platzi.com/cursos/programacion-basica-2022/programa-tu-primer-videojuego-desde-cero/

Terminé el curso y aquí está mi certificado:

https://platzi.com/p/andersonflorez724/curso/3208-programacion-basica-2022/diploma/detalle/

Gracias a ese curso entendí las bases (variables, funciones, condicionales, ciclos, clases) y también me animé a conectar el juego con un servidor para que dos personas pudieran jugar al mismo tiempo.

## Cosas que quiero mejorar

- Corregir un error que sale cuando alguien está conectado pero todavía no eligió mascota: el otro jugador recibe un error al leer sus datos.
- Hacer que la dirección del servidor no esté escrita a mano, para que funcione desde cualquier dispositivo sin editar el archivo.
- Que el mapa sea más grande y tenga más de una mascota para buscar.

Si ves algo raro o tienes una idea mejor, siéntete libre de abrir un issue o mandarme un pull request. Todavía estoy aprendiendo, así que cualquier comentario me sirve.

— Anderson Florez
