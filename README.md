# DockerMultiCaserez
Este repositorio contiene una aplicación web construida con SvelteKit, que ha sido dockerizada utilizando un Dockerfile multistage. A continuación, se describen los pasos para configurar, construir y ejecutar la aplicación en un entorno Docker.

# Prerrequisitos:
Docker instalado en tu máquina.
Node.js y npm instalados para la configuración inicial del proyecto SvelteKit.
Configuración del Proyecto SvelteKit
Crear un nuevo proyecto SvelteKit:

# Ejecuta el siguiente comando en tu terminal para crear un nuevo proyecto SvelteKit:

npm create svelte@latest my-svelte-app
Sigue las instrucciones interactivas para configurar el proyecto, eligiendo las opciones que mejor se adapten a tus necesidades (puedes optar por usar TypeScript, ESLint, Prettier, etc.).

# Instalar dependencias:

Una vez creado el proyecto, navega al directorio del proyecto e instala las dependencias necesarias:

cd my-svelte-app
npm install
#Verificar la instalación:

Para asegurarte de que todo está funcionando correctamente, ejecuta el servidor de desarrollo:

npm run dev


Se crea el Dockerfile que va a estar mejor especificado en el mismo.


Visita http://localhost:5173 en tu navegador para ver la aplicación en acción.

#Construcción de la Imagen Docker:
Para construir la imagen Docker de la aplicación, asegúrate de estar en el directorio raíz del proyecto donde se encuentra el Dockerfile, y luego ejecuta:

docker build -t sveltekit-app .

# Ejecución de la Imagen Docker:
Una vez construida la imagen, puedes ejecutar un contenedor utilizando el siguiente comando:

docker run -p 80:80 sveltekit-app
Esto ejecutará el contenedor y expondrá la aplicación en el puerto 80. Puedes acceder a la aplicación visitando http://localhost en tu navegador.
