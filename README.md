# ursim-docker

Simulador de robots de Universal Robots UR e-series. Inspirado en [Universal Robots simulator for e-Series
](https://hub.docker.com/r/universalrobots/ursim_e-series).

## Requisitos

- [Docker Desktop](https://www.docker.com/products/docker-desktop)

## Instrucciones

1. Clonar este repositorio de git

2. Crear una carpeta dentro de la carpeta de usuario con el nombre de .ursim

   ```bash
   mkdir .ursim
   ```

3. Entrar a la carpeta `📂.ursim` y crear las carpetas `📂programs` y `📂urcaps`

   ```bash
   cd .ursim
   mkdir programs
   mkdir urcaps
   ```

4. Editar el archivo `docker-compose.yml` y cambiar `NOMBRE_USUARIO` por el nombre de la carpeta de usuario

   ```yaml
   volumes:
     - "/c/Users/NOMBRE_USUARIO/.ursim/programs:/ursim/programs"
     - "/c/Users/NOMBRE_USUARIO/.ursim/urcaps:/urcaps"
   ```

5. Abrir una terminal y navegar a la carpeta donde se clonó el repositorio, ejecutar el siguiente comando

   ```bash
   docker-compose -p ursim up --build -d
   ```

6. Abrir un navegador y navegar a la dirección `http://http://localhost:6080/vnc.html?host=localhost&port=6080` para acceder al simulador

7. (Opcional) Para instalar el external control URCap copiar el archivo `external_control.jar` a la carpeta `📂urcaps` creada en el paso 3

8. (Opcional) Para instalar el gripper de Robotiq copiar el archivo `Robotiq_Grippers-3.17.0.105337.urcap` a la carpeta `programs` creada en el paso 3 y proceder a instalarlo desde el PolyScope en el menú hamburguesa, Settings, System, URCaps y darle en el +. Luego seleccionar el archivo `Robotiq_Grippers-3.17.0.105337.urcap` y seguir las instrucciones.
