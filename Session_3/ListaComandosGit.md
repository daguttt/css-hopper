
# Lista de Comandos de Git Ordenada

Una guía básica de los comandos de Git más utilizados, organizados según un flujo de trabajo típico de desarrollo de software.

## Configuración Inicial

1. **`git config`**: Configura las opciones de Git a nivel local, global, o de sistema.
   - `--global user.name "Nombre"`: Establece el nombre del usuario para todos los repositorios del usuario actual.
   - `--global user.email correo@example.com`: Establece el correo electrónico para todos los repositorios.

## Inicio de un Proyecto

2. **`git init`**: Inicializa un nuevo repositorio Git local.

3. **`git clone [url]`**: Crea una copia local de un repositorio remoto existente.

## Cambios y Commit

4. **`git status`**: Muestra el estado del repositorio (archivos modificados, preparados, etc.).

5. **`git add [archivo]`**: Añade un archivo al área de preparación (staging area).

6. **`git commit -m "Mensaje"`**: Guarda los cambios en el repositorio con un mensaje descriptivo.

## Ramas

7. **`git branch`**: Lista las ramas locales o crea una nueva.

8. **`git checkout [nombre-rama]`**: Cambia a la rama especificada.

9. **`git merge [nombre-rama]`**: Fusiona la rama especificada con la rama actual.

## Trabajo con Repositorios Remotos

10. **`git remote add [nombre-remoto] [url]`**: Agrega un nuevo repositorio remoto.

11. **`git fetch [nombre-remoto]`**: Descarga los cambios del repositorio remoto, pero no los integra.

12. **`git pull [nombre-remoto] [rama]`**: Descarga los cambios del repositorio remoto y los integra con la rama local.

13. **`git push [nombre-remoto] [rama]`**: Sube los cambios de la rama local al repositorio remoto.

## Historial y Diferencias

14. **`git log`**: Muestra el historial de commits.

15. **`git diff`**: Muestra las diferencias entre los archivos modificados.

## Herramientas Avanzadas

16. **`git rebase [rama]`**: Reorganiza los commits sobre otra base, útil para una historia de proyecto limpia.

17. **`git stash`**: Guarda temporalmente cambios no listos para commit, permitiendo cambiar de rama.

Esta lista cubre los comandos más fundamentales para el manejo de un flujo de trabajo básico en Git. Hay muchos más comandos y opciones avanzadas disponibles para situaciones específicas y optimización del trabajo en equipo y el manejo del código.
