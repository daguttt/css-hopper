
# Configuraciones de Git: Local, Global y de Sistema

En Git, puedes configurar tus credenciales de usuario (`user.name` y `user.email`) en tres niveles diferentes: local, global y de sistema. Cada uno de estos niveles tiene un propósito específico y se aplica a distintos ámbitos de tus proyectos y la máquina en que trabajas.

## 1. Configuración Local

- **Ámbito**: Específico para un repositorio individual.
- **Uso**: Ideal cuando trabajas en un proyecto que requiere una identidad de usuario diferente de tus configuraciones globales o de sistema.
- **Comandos**:
  - Establecer el nombre de usuario local: `git config --local user.name "Tu Nombre"`
  - Establecer el correo electrónico local: `git config --local user.email "tu.email@example.com"`
  - Ver la configuración local: `git config --list --local`

## 2. Configuración Global

- **Ámbito**: Aplica a todos los repositorios en tu usuario actual.
- **Uso**: Utilizado para establecer tu identidad en todos los proyectos de tu usuario actual.
- **Comandos**:
  - Establecer el nombre de usuario global: `git config --global user.name "Tu Nombre"`
  - Establecer el correo electrónico global: `git config --global user.email "tu.email@example.com"`
  - Ver la configuración global: `git config --list --global`

## 3. Configuración de Sistema

- **Ámbito**: Aplica a todos los usuarios en la máquina actual.
- **Uso**: Para establecer políticas a nivel de sistema o en casos especiales como una máquina compartida.
- **Comandos**:
  - Establecer el nombre de usuario de sistema: `git config --system user.name "Tu Nombre"`
  - Establecer el correo electrónico de sistema: `git config --system user.email "tu.email@example.com"`
  - Ver la configuración de sistema: `git config --list --system`

## Notas Adicionales

- **Precedencia**: La configuración local tiene precedencia sobre la global, que a su vez tiene precedencia sobre la de sistema.
- **Verificar Configuraciones**: `git config --list --show-origin` te mostrará de dónde proviene cada configuración.
- **Permisos**: Para modificar la configuración de sistema, puedes necesitar privilegios de administrador.

