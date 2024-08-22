
# Práctica de Git en Equipo
# I INTEGRANTES: 
Diego Chicuazuque y Felipe Martinez

# II RESPUESTAS:
## Owner y Colaborador editan el archivo README.md al mismo tiempo e intentan subir los cambios al mismo tiempo.

### ¿Qué sucedió?
**Situación Inicial**  
-_Owner_: Es quien crea el repositorio y tiene control total sobre él.  
-_Collaborator_: Es quien recibe permisos de escritura sobre el repositorio para colaborar.

**Escenario de Conflicto:**  
-_Owner y Collaborator_ editamos el archivo _README.md_ al mismo tiempo y ambos intentamos hacer un push de los cambios que cada uno le hicimos.Nos fijamos que <u>Git no permite hacer un push directo si hay cambios en el repositorio remoto que no están sincronizados con tu versión local</u>. Esto causa un conflicto cuando ambas personas intentan subir los cambios simultáneamente.

**Cómo lo resolvimos:**  
-La persona que perdió la _"competencia"_ al intentar hacer el push primero tendrá que hacer un git pull para traer los cambios del repositorio remoto.Durante el pull, Git detectará los conflictos y añadirá marcas como `<<<`, `===`, y `>>>` en el archivo afectado. Estas marcas indican las diferencias entre las versiones del archivo.El colaborador tendrá que resolver estos conflictos manualmente, eligiendo qué líneas de código conservar y cuáles eliminar.

## ¿Hay una mejor forma de trabajar con Git para no tener conflictos?
Sí, usando ramas y Pull Requests, coordinando mejor el trabajo, y asegurando una buena comunicación entre los miembros del equipo.

## ¿Qué es y cómo funciona el Pull Request?
Es una solicitud para fusionar cambios de una rama a otra. Permite que otros miembros del equipo revisen y aprueben los cambios antes de ser fusionados, ayudando a prevenir errores y conflictos.

# III QUE COMANDOS SE UTILIZARON:
## Configuración Inicial
1. **Clonar un repositorio:**
   ```bash
   git clone <URL-del-repositorio>
   ```
   Clona el repositorio desde GitHub a tu máquina local.

2. **Configurar el usuario:**
   ```bash
   git config --global user.name "Tu Nombre"
   git config --global user.email "tuemail@example.com"
   ```
   Configura tu nombre y correo electrónico para que Git asocie los cambios con tu identidad.

## Trabajo con Archivos y Commit
3. **Verificar el estado del repositorio:**
   ```bash
   git status
   ```
   Muestra los cambios en el directorio de trabajo y la zona de preparación (staging).

4. **Agregar archivos al staging:**
   ```bash
   git add <archivo>
   ```
   Agrega un archivo específico al staging.
   ```bash
   git add .
   ```
   Agrega todos los cambios en el directorio de trabajo al staging.

5. **Realizar un commit:**
   ```bash
   git commit -m "Mensaje descriptivo del commit"
   ```
   Guarda los cambios en el historial de commits con un mensaje descriptivo.

## Sincronización con el Repositorio Remoto
6. **Hacer push de los cambios al repositorio remoto:**
   ```bash
   git push origin <nombre-de-la-rama>
   ```
   Sube los cambios de tu rama local al repositorio remoto.

7. **Traer los cambios del repositorio remoto (pull):**
   ```bash
   git pull origin <nombre-de-la-rama>
   ```
   Descarga los cambios del repositorio remoto y los fusiona con tu rama local.

## Resolución de Conflictos
8. **Resolver conflictos manualmente:**
   - Abre el archivo con conflicto, identifica las secciones marcadas con `<<<`, `===`, y `>>>`, y resuelve el conflicto manteniendo las líneas correctas.
   
   **Después de resolver el conflicto:**
   ```bash
   git add <archivo>
   ```
   Marca el conflicto como resuelto y agrega el archivo al staging.
   ```bash
   git commit -m "Resuelto conflicto en <archivo>"
   ```
   Realiza un commit para guardar la resolución del conflicto.

## Trabajo con Ramas y Pull Requests
9. **Crear una nueva rama:**
   ```bash
   git checkout -b <nombre-de-la-rama>
   ```
   Crea y cambia a una nueva rama basada en la rama actual.

10. **Cambiar a una rama existente:**
    ```bash
    git checkout <nombre-de-la-rama>
    ```
    Cambia a otra rama existente en tu repositorio local.

11. **Hacer un Pull Request:**
    - Este paso se realiza en GitHub, no en la terminal. Ve al repositorio en GitHub y crea un Pull Request (PR) para fusionar los cambios de tu rama en `main` o `master`.

12. **Fusionar una Pull Request en GitHub:**
    - Después de que otro miembro del equipo revise y apruebe el PR, realiza el merge en GitHub.

13. **Eliminar una rama después del merge:**
    ```bash
    git branch -d <nombre-de-la-rama>
    ```
    Elimina una rama local después de que se haya fusionado con `main` en GitHub.
    ```bash
    git push origin --delete <nombre-de-la-rama>
    ```
    Elimina una rama remota en GitHub.

## Extra (Si usas IntelliJ para Resolver Conflictos)
14. **Resolver conflictos en IntelliJ:**
    - IntelliJ proporciona una interfaz gráfica para resolver conflictos de merge cuando abres el archivo en conflicto o tambien en _VisualStudioCode_ tambien sale .


