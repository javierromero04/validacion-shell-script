# Documentación del Rebase Interactivo

## Objetivo
Limpiar el historial de commits para mejorar la claridad y la estructura del proyecto. Esto se hizo modificando mensajes poco descriptivos y fusionando commits.

## Pasos Realizados

1. **Creación de Commits Iniciales:**
   - Se crearon commits con los mensajes:
     - "Arreglos"
     - "Cambios"
     - "Actualización de cosas"
     - "otra actualizacion de cosas"
2. **Inicio del Rebase Interactivo:**
   - Se ejecutó el comando:
     ```
     git rebase -i HEAD~3
     ```
   - Se abrió el editor mostrando:
     ```
     pick abcdef1 Arreglos
     pick bcdefa2 Cambios
     pick cdefab3 Actualización de cosas
     ```

3. **Edición de Commits:**
   - Se cambió `pick` a `reword` en el commit "Arreglos" para modificar su mensaje.
   - Se cambió `pick` a `squash` en el commit para fusionarlo.
   - Durante el proceso se editaron los mensajes para que fueran descriptivos y coherentes.

4. **Resolución de Conflictos:**
   - (En caso de que se produjeran conflictos) Se resolvieron los conflictos manualmente y se continuó el rebase con:
     ```
     git add <archivo-conflictivo>
     git rebase --continue
     ```

5. **Actualización del Repositorio Remoto:**
   - Al intentar hacer el push me daba error, he puesto git remote set-url origin git@github.com:javierromero04/validacion-shell-script para utilizar mi clave ssh.
   - Se realizó un push forzado para actualizar el repositorio remoto:
     ```
     git push --force
     ```

## Consideraciones
- **Uso del Rebase Interactivo:** Permite mejorar el historial de commits pero debe usarse con cuidado, especialmente si se colabora con otros.
- **Push Forzado:** Puede sobrescribir cambios en el repositorio remoto. Utilizarlo de manera coordinada en equipos.
