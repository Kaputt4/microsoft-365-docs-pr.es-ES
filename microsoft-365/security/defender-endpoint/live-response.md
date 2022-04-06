---
title: Investigación de entidades en dispositivos mediante respuesta dinámica en Microsoft Defender para punto de conexión
description: Acceda a un dispositivo mediante una conexión de shell remoto segura para realizar un trabajo de investigación y realizar acciones de respuesta inmediatas en un dispositivo en tiempo real.
keywords: remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file,
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5e5d2b2bd47ba30aaf152171605947bb9a627480
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666358"
---
# <a name="investigate-entities-on-devices-using-live-response"></a>Investigación de entidades en dispositivos mediante respuesta dinámica

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

La respuesta dinámica proporciona a los equipos de operaciones de seguridad acceso instantáneo a un dispositivo (también conocido como máquina) mediante una conexión de shell remoto. Esto le ofrece la capacidad de realizar un trabajo de investigación en profundidad y tomar medidas de respuesta inmediatas para contener rápidamente amenazas identificadas en tiempo real.

La respuesta en vivo está diseñada para mejorar las investigaciones al permitir que el equipo de operaciones de seguridad recopile datos forenses, ejecute scripts, envíe entidades sospechosas para su análisis, corrija las amenazas y busque amenazas emergentes de forma proactiva.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

Con la respuesta en vivo, los analistas pueden realizar todas las tareas siguientes:

- Ejecute comandos básicos y avanzados para realizar un trabajo de investigación en un dispositivo.
- Descargue archivos como ejemplos de malware y resultados de scripts de PowerShell.
- Descargar archivos en segundo plano (¡nuevo!).
- Upload un script o ejecutable de PowerShell a la biblioteca y ejecútelo en un dispositivo desde un nivel de inquilino.
- Realizar o deshacer acciones de corrección.

## <a name="before-you-begin"></a>Antes de empezar

Antes de iniciar una sesión en un dispositivo, asegúrese de cumplir los siguientes requisitos:

- **Compruebe que está ejecutando una versión compatible de Windows**.

  Los dispositivos deben ejecutar una de las siguientes versiones de Windows

  - **Windows 10 & 11**
    - [Versión 1909](/windows/whats-new/whats-new-windows-10-version-1909) o posterior
    - [Versión 1903](/windows/whats-new/whats-new-windows-10-version-1903) con [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)
    - [Versión 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) [con KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [Versión 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) con [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [Versión 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) con [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)

  - **macOS** : solo aplicable a la versión preliminar pública, versión mínima necesaria: 101.43.84

   > [!NOTE]
   > Actualmente solo se admiten sistemas macOS basados en Intel.

  - **Linux** : solo aplicable a la versión preliminar pública, versión mínima necesaria: 101.45.13

  - **Windows Server 2012 R2**: con [KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)

  - **Windows Server 2016**: con [KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)

  - **Windows Server 2019**
    - Versión 1903 o (con [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)) posterior
    - Versión 1809 (con [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818))

  - **Windows Server 2022**

- **Habilite la respuesta en directo desde la página de configuración avanzada**.

  Tendrá que habilitar la funcionalidad de respuesta en vivo en la página [Configuración de características avanzadas](advanced-features.md) .

  > [!NOTE]
  > Solo los usuarios con roles de administrador global o de seguridad pueden editar esta configuración.
  >
  > La investigación automatizada debe estar habilitada en la [configuración características avanzadas](advanced-features.md) antes de habilitar la respuesta en directo.

- **Habilite la respuesta en vivo para los servidores desde la página de configuración avanzada** (recomendado).

  > [!NOTE]
  > Solo los usuarios con roles de administrador global o de seguridad pueden editar esta configuración.

- **Asegúrese de que el dispositivo tiene asignado un nivel de corrección de Automation**.

  Tendrá que habilitar, al menos, el nivel de corrección mínimo para un grupo de dispositivos determinado. De lo contrario, no podrá establecer una sesión de respuesta dinámica a un miembro de ese grupo.

  Recibirá el siguiente error:

  :::image type="content" source="images/live-response-error.png" alt-text="Mensaje de error" lightbox="images/live-response-error.png":::

- **Habilitar la ejecución de scripts sin signo de respuesta activa** (opcional).

  >[!IMPORTANT]
  >La comprobación de firmas solo se aplica a los scripts de PowerShell.

  > [!WARNING]
  > Permitir el uso de scripts sin firmar puede aumentar la exposición a amenazas.

  No se recomienda ejecutar scripts sin firmar, ya que puede aumentar la exposición a amenazas. Sin embargo, si debe usarlos, deberá habilitar la configuración en la página [Configuración avanzada de características](advanced-features.md) .

- **Asegúrese de que tiene los permisos adecuados**.

  Solo los usuarios que se han aprovisionado con los permisos adecuados pueden iniciar una sesión. Para obtener más información sobre las asignaciones de roles, consulte [Creación y administración de roles](user-roles.md).

  > [!IMPORTANT]
  > La opción para cargar un archivo en la biblioteca solo está disponible para los usuarios con el permiso "Administrar seguridad Configuración".
  > El botón está atenuado para los usuarios con solo permisos delegados.

  En función del rol que se le haya concedido, puede ejecutar comandos de respuesta en directo básicos o avanzados. Los permisos de los usuarios se controlan mediante el rol personalizado de RBAC.

## <a name="live-response-dashboard-overview"></a>Introducción al panel de respuesta en directo

Al iniciar una sesión de respuesta dinámica en un dispositivo, se abre un panel. El panel proporciona información sobre la sesión como la siguiente:

- Quién ha creado la sesión
- Cuando se inició la sesión
- Duración de la sesión

El panel también le proporciona acceso a:

- Desconectar sesión
- Upload archivos a la biblioteca
- Consola de comandos
- Registro de comandos

## <a name="initiate-a-live-response-session-on-a-device"></a>Inicio de una sesión de respuesta en directo en un dispositivo

1. Inicie sesión en Microsoft 365 Defender portal.

2. Vaya a **Puntos de conexión > Inventario de** dispositivos y seleccione un dispositivo para investigar. Se abre la página dispositivos.

3. Inicie la sesión de respuesta en directo seleccionando **Iniciar sesión de respuesta activa**. Se muestra una consola de comandos. Espere mientras la sesión se conecta al dispositivo.

4. Use los comandos integrados para realizar un trabajo de investigación. Para obtener más información, vea [Comandos de respuesta dinámica](#live-response-commands).

5. Después de completar la investigación, seleccione **Desconectar sesión** y, a continuación, seleccione **Confirmar**.

## <a name="live-response-commands"></a>Comandos de respuesta dinámica

En función del rol que se le haya concedido, puede ejecutar comandos de respuesta en directo básicos o avanzados. Los permisos de usuario se controlan mediante roles personalizados de RBAC. Para obtener más información sobre las asignaciones de roles, consulte [Creación y administración de roles](user-roles.md).

> [!NOTE]
> La respuesta dinámica es un shell interactivo basado en la nube, por lo que la experiencia de comandos específica puede variar en el tiempo de respuesta en función de la calidad de red y la carga del sistema entre el usuario final y el dispositivo de destino.

### <a name="basic-commands"></a>Comandos básicos

Los siguientes comandos están disponibles para los roles de usuario a los que se les concede la capacidad de ejecutar comandos **básicos** de respuesta dinámica. Para obtener más información sobre las asignaciones de roles, consulte [Creación y administración de roles](user-roles.md).

| Comando  | Descripción  | Windows y Windows Server  | macOS  | Linux  |
|---|---|---|---|---|
| Cd  | Cambia el directorio actual.  | v  | v  | v  |
| Cls  | Borra la pantalla de la consola.  | v  | v  | v  |
| connect  | Inicia una sesión de respuesta activa en el dispositivo.  | v  | v  | v  |
| Conexiones  | Muestra todas las conexiones activas.  | v  | N  | N  |
| Dir  | Muestra una lista de archivos y subdirectorios en un directorio.  | v  | v  | v  |
| Controladores  | Muestra todos los controladores instalados en el dispositivo.  | v  | N  | N  |
| Fg `<command ID>`  | Coloque el trabajo especificado en primer plano en primer plano, lo que lo convierte en el trabajo actual.  NOTA: fg toma un "identificador de comando" disponible en los trabajos, no en un PID  | v  | v  | v  |
| Fileinfo  | Obtener información acerca de un archivo.  | v  | v  | v  |
| findfile  | Busca archivos por un nombre determinado en el dispositivo.  | v  | v  | v  |
| getfile <file_path>  | Descarga un archivo.  | v  | v  | v  |
| Ayuda  | Proporciona información de ayuda para los comandos de respuesta dinámica.  | v  | v  | v  |
| jobs  | Muestra los trabajos en ejecución, su identificador y estado.  | v  | v  | v  |
| Persistencia  | Muestra todos los métodos de persistencia conocidos en el dispositivo.  | v  | N  | N  |
| procesos  | Muestra todos los procesos que se ejecutan en el dispositivo.  | v  | v  | v  |
| registro  | Muestra los valores del Registro.  | v  | N  | N  |
| scheduledtasks  | Muestra todas las tareas programadas en el dispositivo.  | v  | N  | N  |
| Servicios  | Muestra todos los servicios del dispositivo.  | v  | N  | N  |
| startupfolders  | Muestra todos los archivos conocidos en las carpetas de inicio del dispositivo.  | v  | N  | N  |
| status  | Muestra el estado y la salida del comando específico.  | v  | N  | N  |
| Rastro  | Establece el modo de registro del terminal para depurar.  | v  | v  | v  |

### <a name="advanced-commands"></a>Comandos avanzados

Los siguientes comandos están disponibles para los roles de usuario a los que se les concede la capacidad de ejecutar comandos **avanzados** de respuesta dinámica. Para obtener más información sobre las asignaciones de roles, consulte [Creación y administración de roles](user-roles.md).

| Comando  | Descripción  | Windows y Windows Server  | macOS  | Linux  |
|---|---|---|---|---|
| Analizar  | Analiza la entidad con varios motores de incriminación para llegar a un veredicto.  | v  | N  | N  |
| Recoger  | Recopila el paquete forense de la máquina  | N  | v  | v  |
| Aislar  | Desconecta el dispositivo de la red mientras conserva la conectividad con el servicio Defender para punto de conexión.  | N  | v  | N  |
| Lanzamiento  | Libera un dispositivo del aislamiento de red  | N  | v  | N  |
| Ejecutar  | Ejecuta un script de PowerShell desde la biblioteca del dispositivo.  | v  | v  | v  |
| Biblioteca  | Enumera los archivos que se cargaron en la biblioteca de respuestas dinámicas.  | v  | v  | v  |
| putfile  | Coloca un archivo de la biblioteca en el dispositivo. Los archivos se guardan en una carpeta de trabajo y se eliminan cuando el dispositivo se reinicia de forma predeterminada.  | v  | v  | v  |
| Remediar  | Corrige una entidad en el dispositivo. La acción de corrección variará en función del tipo de entidad: Archivo: eliminar proceso: detener, eliminar archivo de imagen Servicio: detener, eliminar entrada del Registro de archivos de imagen: eliminar tarea programada: quitar elemento carpeta de inicio: eliminar archivo NOTA: Este comando tiene un comando de requisito previo. Puede usar el comando -auto junto con la corrección para ejecutar automáticamente el comando de requisitos previos.  | v  | v  | v  |
| escanear | Ejecuta un examen antivirus para ayudar a identificar y corregir el malware. | N | v | v |
| Deshacer  | Restaura una entidad que se ha corregido.  | v  | v  | v  |

## <a name="use-live-response-commands"></a>Uso de comandos de respuesta en directo

Los comandos que puede usar en la consola siguen principios similares a [Windows Comandos](/windows-server/administration/windows-commands/windows-commands#BKMK_c).

Los comandos avanzados ofrecen un conjunto más sólido de acciones que le permiten realizar acciones más eficaces, como descargar y cargar un archivo, ejecutar scripts en el dispositivo y realizar acciones de corrección en una entidad.

### <a name="get-a-file-from-the-device"></a>Obtener un archivo del dispositivo

Para escenarios en los que quiera obtener un archivo de un dispositivo que está investigando, puede usar el `getfile` comando . Esto le permite guardar el archivo desde el dispositivo para una investigación más detallada.

> [!NOTE]
> Se aplican los siguientes límites de tamaño de archivo:
>
> - `getfile` límite: 3 GB
> - `fileinfo` límite: 30 GB
> - `library` límite: 250 MB

### <a name="download-a-file-in-the-background"></a>Descarga de un archivo en segundo plano

Para permitir que el equipo de operaciones de seguridad continúe investigando un dispositivo afectado, ahora se pueden descargar archivos en segundo plano.

- Para descargar un archivo en segundo plano, en la consola de comandos de respuesta dinámica, escriba `download <file_path> &`.
- Si está esperando a que se descargue un archivo, puede moverlo al fondo mediante Ctrl + Z.
- Para llevar una descarga de archivos al primer plano, en la consola de comandos de respuesta activa, escriba `fg <command_id>`.

Estos son algunos ejemplos:

<br>

****

|Comando|Qué hace|
|---|---|
|`getfile "C:\windows\some_file.exe" &`|Comienza a descargar un archivo denominado *some_file.exe* en segundo plano.|
|`fg 1234`|Devuelve una descarga con el identificador *de comando 1234* en primer plano.|
|

### <a name="put-a-file-in-the-library"></a>Colocación de un archivo en la biblioteca

Respuesta dinámica tiene una biblioteca en la que puede colocar archivos. La biblioteca almacena archivos (como scripts) que se pueden ejecutar en una sesión de respuesta dinámica en el nivel de inquilino.

La respuesta dinámica permite ejecutar scripts de PowerShell, pero primero debe colocar los archivos en la biblioteca para poder ejecutarlos.

Puede tener una colección de scripts de PowerShell que se pueden ejecutar en dispositivos con los que inicie sesiones de respuesta en directo.

#### <a name="to-upload-a-file-in-the-library"></a>Para cargar un archivo en la biblioteca

1. Haga clic en **Upload archivo a la biblioteca**.

2. Haga clic en **Examinar** y seleccione el archivo.

3. Proporcione una breve descripción.

4. Especifique si desea sobrescribir un archivo con el mismo nombre.

5. Si quiere hacerlo, sepa qué parámetros se necesitan para el script, active la casilla parámetros de script. En el campo de texto, escriba un ejemplo y una descripción.

6. Haga clic en **Confirmar**.

7. (Opcional) Para comprobar que el archivo se cargó en la biblioteca, ejecute el `library` comando .

### <a name="cancel-a-command"></a>Cancelar un comando

En cualquier momento durante una sesión, puede cancelar un comando presionando CTRL + C.

> [!WARNING]
> El uso de este acceso directo no detendrá el comando en el lado del agente. Solo cancelará el comando en el portal. Por lo tanto, las operaciones de cambio, como "remediate", pueden continuar mientras se cancela el comando.

## <a name="run-a-script"></a>Ejecutar un script

Para poder ejecutar un script de PowerShell o Bash, primero debe cargarlo en la biblioteca.

Después de cargar el script en la biblioteca, use el `run` comando para ejecutar el script.

Si tiene previsto usar un script de PowerShell sin firmar en la sesión, deberá habilitar la configuración en la página [Configuración avanzada de características](advanced-features.md) .

> [!WARNING]
> Permitir el uso de scripts sin firmar puede aumentar la exposición a amenazas.

## <a name="apply-command-parameters"></a>Aplicar parámetros de comando

- Vea la ayuda de la consola para obtener información sobre los parámetros de comando. Para obtener información sobre un comando individual, ejecute:

  ```powershell
  help <command name>
  ```

- Al aplicar parámetros a comandos, tenga en cuenta que los parámetros se controlan en función de un orden fijo:

  ```powershell
  <command name> param1 param2
  ```

- Al especificar parámetros fuera del orden fijo, especifique el nombre del parámetro con un guion antes de proporcionar el valor:

  ```powershell
  <command name> -param2_name param2
  ```

- Al usar comandos que tienen comandos de requisitos previos, puede usar marcas:

  ```powershell
  <command name> -type file -id <file path> - auto
  ```

  o

  ```powershell
  remediate file <file path> - auto`
  ```

## <a name="supported-output-types"></a>Tipos de salida admitidos

La respuesta dinámica admite tipos de salida de formato JSON y tabla. Para cada comando, hay un comportamiento de salida predeterminado. Puede modificar la salida en el formato de salida que prefiera mediante los siguientes comandos:

- `-output json`
- `-output table`

> [!NOTE]
> Se muestran menos campos en formato de tabla debido al espacio limitado. Para ver más detalles en la salida, puede usar el comando de salida JSON para que se muestren más detalles.

## <a name="supported-output-pipes"></a>Canalizaciones de salida admitidas

La respuesta dinámica admite la canalización de salida a la CLI y al archivo. La CLI es el comportamiento de salida predeterminado. Puede canalizar la salida a un archivo mediante el siguiente comando: [command] > [filename].txt.

Ejemplo:

```console
processes > output.txt
```

## <a name="view-the-command-log"></a>Visualización del registro de comandos

Seleccione la pestaña **Registro de comandos** para ver los comandos usados en el dispositivo durante una sesión. Se realiza un seguimiento de cada comando con detalles completos, como:

- ID
- Línea de comandos
- Duración
- Estado y barra lateral de entrada o salida

## <a name="limitations"></a>Limitaciones

- Las sesiones de respuesta en directo están limitadas a 25 sesiones de respuesta en directo a la vez.
- El valor de tiempo de espera inactivo de la sesión de respuesta activa es de 30 minutos.
- Los comandos de respuesta dinámica individual tienen un límite de tiempo de 10 minutos, a excepción de `getfile`, `findfile`y `run`, que tienen un límite de 30 minutos.
- Un usuario puede iniciar hasta 10 sesiones simultáneas.
- Un dispositivo solo puede estar en una sesión a la vez.
- Se aplican los siguientes límites de tamaño de archivo:
  - `getfile` límite: 3 GB
  - `fileinfo` límite: 10 GB
  - `library` límite: 250 MB

## <a name="related-article"></a>Artículo relacionado

- [Ejemplos de comandos de respuesta en vivo](live-response-command-examples.md)
