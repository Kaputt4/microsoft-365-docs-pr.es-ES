---
title: Investigar entidades en dispositivos con respuesta en directo en Microsoft Defender para endpoint
description: Accede a un dispositivo mediante una conexión segura del shell remoto para realizar trabajos de investigación y realizar acciones de respuesta inmediatas en un dispositivo en tiempo real.
keywords: remoto, shell, conexión, live, response, en tiempo real, comando, script, remediate, hunt, export, log, drop, download, file,
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
ms.openlocfilehash: 07091dfaa997ff0415ecdb981b0b26f301cf0dce
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587178"
---
# <a name="investigate-entities-on-devices-using-live-response"></a>Investigar entidades en dispositivos con respuesta en directo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

La respuesta en directo proporciona a los equipos de operaciones de seguridad acceso instantáneo a un dispositivo (también denominado máquina) mediante una conexión remota del shell. Esto le da la capacidad de realizar un trabajo de investigación en profundidad y tomar acciones de respuesta inmediatas para contener rápidamente las amenazas identificadas en tiempo real.

La respuesta activa está diseñada para mejorar las investigaciones, ya que permite al equipo de operaciones de seguridad recopilar datos forenses, ejecutar scripts, enviar entidades sospechosas para su análisis, corregir amenazas y buscar proactivamente amenazas emergentes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

Con la respuesta en directo, los analistas pueden realizar todas las tareas siguientes:

- Ejecute comandos básicos y avanzados para realizar trabajos de investigación en un dispositivo.
- Descargue archivos como ejemplos de malware y resultados de scripts de PowerShell.
- Descargar archivos en segundo plano (¡nuevo!).
- Upload un script de PowerShell o ejecutable a la biblioteca y ejecutarlo en un dispositivo desde un nivel de inquilino.
- Realizar o deshacer acciones de corrección.

## <a name="before-you-begin"></a>Antes de empezar

Antes de iniciar una sesión en un dispositivo, asegúrate de cumplir los siguientes requisitos:

- **Compruebe que está ejecutando una versión compatible de Windows**.

  Los dispositivos deben ejecutar una de las siguientes versiones de Windows

  - **Windows 10 & 11**
    - [Versión 1909](/windows/whats-new/whats-new-windows-10-version-1909) o posterior
    - [Versión 1903](/windows/whats-new/whats-new-windows-10-version-1903) con [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)
    - [Versión 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) con [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [Versión 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) con [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [Versión 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) con [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)

  - **macOS:** solo aplicable a public preview, versión mínima requerida: 101.43.84 
  
  - **Linux:** solo aplicable a public preview, versión mínima requerida: 101.45.13 
    
  - **Windows Server 2012 R2:** con [KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)
  
  - **Windows Server 2016:** con [KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)

  - **Windows Server 2019**
    - Versión 1903 o (con [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)) posterior
    - Versión 1809 (con [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818))
    
  - **Windows Server 2022**

       

- **Habilitar la respuesta en directo desde la página de configuración avanzada**.

  Tendrás que habilitar la funcionalidad de respuesta en directo en la [página Configuración de características avanzadas.](advanced-features.md)

  > [!NOTE]
  > Solo los usuarios con roles de administración global o de seguridad pueden editar esta configuración.

- **Habilitar la respuesta en directo para los servidores desde la página de configuración avanzada** (recomendado).

  > [!NOTE]
  > Solo los usuarios con roles de administración global o de seguridad pueden editar esta configuración.

- **Asegúrese de que el dispositivo tiene asignado un** nivel de corrección de automatización .

  Tendrás que habilitar, al menos, el nivel mínimo de corrección para un grupo de dispositivos determinado. De lo contrario, no podrá establecer una sesión de live response a un miembro de ese grupo.

  Recibirá el siguiente error:

  ![Imagen del mensaje de error.](images/live-response-error.png)

- **Habilitar la ejecución de script sin signo de respuesta** en directo (opcional).

  >[!IMPORTANT]
  >La comprobación de firmas solo se aplica a los scripts de PowerShell. 

  > [!WARNING]
  > Permitir el uso de scripts sin signo puede aumentar la exposición a amenazas.

  No se recomienda ejecutar scripts sin firma, ya que puede aumentar la exposición a amenazas. Sin embargo, si debe usarlos, deberá habilitar la configuración en la [página Configuración de características avanzadas.](advanced-features.md)

- **Asegúrese de que tiene los permisos adecuados**.

  Solo los usuarios que se han aprovisionado con los permisos adecuados pueden iniciar una sesión. Para obtener más información sobre las asignaciones de roles, vea [Create and manage roles](user-roles.md).

  > [!IMPORTANT]
  > La opción para cargar un archivo en la biblioteca solo está disponible para los usuarios con el permiso "Administrar seguridad Configuración".
  > El botón está gris para los usuarios con solo permisos delegados.

  Según el rol que se le haya concedido, puede ejecutar comandos de respuesta en directo básicos o avanzados. Los permisos de los usuarios están controlados por el rol personalizado RBAC.

## <a name="live-response-dashboard-overview"></a>Introducción al panel de respuestas en directo

Cuando inicias una sesión de respuesta en directo en un dispositivo, se abre un panel. El panel proporciona información sobre la sesión, como la siguiente:

- Quién la sesión
- Cuando se inició la sesión
- Duración de la sesión

El panel también le da acceso a:

- Desconectar sesión
- Upload archivos a la biblioteca
- Consola de comandos
- Registro de comandos

## <a name="initiate-a-live-response-session-on-a-device"></a>Iniciar una sesión de respuesta en directo en un dispositivo

1. Inicie sesión en Microsoft 365 Defender portal.

2. Vaya a **Endpoints > Inventario de dispositivos** y seleccione un dispositivo para investigar. Se abre la página dispositivos.

3. Inicie la sesión de respuesta activa seleccionando **Iniciar sesión de respuesta en directo**. Se muestra una consola de comandos. Espere mientras la sesión se conecta al dispositivo.

4. Use los comandos integrados para realizar trabajos de investigación. Para obtener más información, vea [Comandos de respuesta en directo](#live-response-commands).

5. Después de completar la investigación, seleccione **Desconectar sesión** y, a continuación, **seleccione Confirmar**.

## <a name="live-response-commands"></a>Comandos de respuesta en directo

Según el rol que se le haya concedido, puede ejecutar comandos de respuesta en directo básicos o avanzados. Los permisos de usuario se controlan mediante roles personalizados rbac. Para obtener más información sobre las asignaciones de roles, vea [Create and manage roles](user-roles.md).

> [!NOTE]
> La respuesta en directo es un shell interactivo basado en la nube, por lo que la experiencia de comandos específica puede variar en el tiempo de respuesta según la calidad de la red y la carga del sistema entre el usuario final y el dispositivo de destino.

### <a name="basic-commands"></a>Comandos básicos

Los siguientes comandos están disponibles para los roles de usuario a los que se les concede la capacidad de ejecutar **comandos** básicos de respuesta en directo. Para obtener más información sobre las asignaciones de roles, vea [Create and manage roles](user-roles.md).

<br>

****
| Comando  | Descripción  | Windows y Windows server  | macOS  | Linux  |
|---|---|---|---|---|
| cd  | Cambia el directorio actual.  | v  | v | v |
| cls  | Borra la pantalla de la consola.  | v  | v  | v  |
| connect  | Inicia una sesión de respuesta en directo al dispositivo.  | v  | v  | v  |
| conexiones  | Muestra todas las conexiones activas.  | v  | N | N |
| dir  | Muestra una lista de archivos y subdirectorios en un directorio.  | v  | v  |v  |
| controladores  | Muestra todos los controladores instalados en el dispositivo.  | v |  N | N  |
| fg `<command ID>`  | Coloque el trabajo especificado en primer plano en primer plano, lo que lo hace el trabajo actual.  NOTA: fg toma un "identificador de comando" disponible desde trabajos, no un PID  | v  | v  | v  |
| fileinfo  | Obtener información acerca de un archivo.  |v  | v  | v  |
| findfile  | Localiza los archivos por un nombre determinado en el dispositivo.  | v | v  | v  |
| getfile <file_path>  | Descarga un archivo.  | v  | v  | v  |
| Ayuda  | Proporciona información de ayuda para comandos de respuesta en directo.  |v  | v | v  |
| jobs  | Muestra trabajos en ejecución, su identificador y estado.  | v  | v | v |
| persistencia  | Muestra todos los métodos de persistencia conocidos en el dispositivo.  | v  | N | N |
| procesos  | Muestra todos los procesos que se ejecutan en el dispositivo.  | v  | v  | v  |
| registro  | Muestra los valores del Registro.  | v  | N | N |
| scheduledtasks  | Muestra todas las tareas programadas en el dispositivo.  | v | N | N |
| servicios  | Muestra todos los servicios del dispositivo.  | v  | N | N |
| seguimiento  | Establece el modo de registro del terminal en depuración.  | v  | v  |v  |

### <a name="advanced-commands"></a>Comandos avanzados

Los siguientes comandos están disponibles para los roles de usuario a los que se les concede la capacidad de ejecutar **comandos avanzados** de respuesta en directo. Para obtener más información sobre las asignaciones de roles, vea [Create and manage roles](user-roles.md).

<br>

****

| Comando  | Descripción  | Windows y Windows server  | macOS  | Linux  |
|---|---|---|---|---|
| analizar  | Analiza la entidad con varios motores de incriminación para llegar a un veredicto.  | v  | N  | N  |
| recopilar  | Recopila el paquete de análisis forense de la máquina  | N  | v  | v  |
| isolate  | Desconecta el dispositivo de la red mientras conserva la conectividad con el servicio Defender for Endpoint  | N  | v  | N  |
| release  | Libera un dispositivo del aislamiento de red  | N  | v  | N  |
| ejecutar  | Ejecuta un script de PowerShell desde la biblioteca en el dispositivo.  | v  | v  | v  |
| biblioteca  | Enumera los archivos que se cargaron en la biblioteca de respuestas en directo.  | v  | v  | v  |
| putfile  | Coloca un archivo de la biblioteca en el dispositivo. Los archivos se guardan en una carpeta de trabajo y se eliminan cuando el dispositivo se reinicia de forma predeterminada.  | v  | v  | v  |
| remediate  | Corrige una entidad en el dispositivo. La acción de corrección variará según el tipo de entidad: Archivo: eliminar Proceso: detener, eliminar archivo de imagen Servicio: detener, eliminar entrada del Registro del archivo de imagen: eliminar tarea programada: quitar elemento de carpeta inicio: eliminar archivo NOTA: Este comando tiene un comando de requisito previo. Puede usar el comando -auto junto con remediate para ejecutar automáticamente el comando de requisitos previos.  | v  | v  | v  |
| examen  | Desconecta el dispositivo de la red mientras conserva la conectividad con el servicio Defender for Endpoint  | N  | v  | v  |
| deshacer  | Restaura una entidad que se ha corregido.  | v  | v  | v  |


## <a name="use-live-response-commands"></a>Usar comandos de respuesta en directo

Los comandos que se pueden usar en la consola siguen principios similares a [Windows comandos](/windows-server/administration/windows-commands/windows-commands#BKMK_c).

Los comandos avanzados ofrecen un conjunto más sólido de acciones que te permiten realizar acciones más eficaces, como descargar y cargar un archivo, ejecutar scripts en el dispositivo y realizar acciones de corrección en una entidad.

### <a name="get-a-file-from-the-device"></a>Obtener un archivo del dispositivo

Para escenarios en los que quieras obtener un archivo de un dispositivo que estés investigando, puedes usar el `getfile` comando. Esto te permite guardar el archivo del dispositivo para una investigación posterior.

> [!NOTE]
> Se aplican los siguientes límites de tamaño de archivo:
>
> - `getfile` límite: 3 GB
> - `fileinfo` límite: 10 GB
> - `library` límite: 250 MB

### <a name="download-a-file-in-the-background"></a>Descargar un archivo en segundo plano

Para permitir que el equipo de operaciones de seguridad continúe investigando un dispositivo afectado, los archivos ahora se pueden descargar en segundo plano.

- Para descargar un archivo en segundo plano, en la consola de comandos de respuesta en directo, escriba `download <file_path> &` .
- Si está esperando a que se descargue un archivo, puede moverlo al fondo mediante Ctrl + Z.
- Para llevar una descarga de archivos al primer plano, en la consola de comandos de respuesta en directo, escriba `fg <command_id>` .

Estos son algunos ejemplos:

<br>

****

|Comando|Qué hace|
|---|---|
|`getfile "C:\windows\some_file.exe" &`|Inicia la descarga de un archivo *denominadosome_file.exe* en segundo plano.|
|`fg 1234`|Devuelve una descarga con el identificador de comando *1234* en primer plano.|
|

### <a name="put-a-file-in-the-library"></a>Colocar un archivo en la biblioteca

La respuesta en directo tiene una biblioteca en la que puede colocar archivos. La biblioteca almacena archivos (como scripts) que se pueden ejecutar en una sesión de respuesta activa en el nivel de inquilino.

La respuesta en directo permite ejecutar scripts de PowerShell, pero primero debe colocar los archivos en la biblioteca antes de poder ejecutarlos.

Puede tener una colección de scripts de PowerShell que se pueden ejecutar en dispositivos con los que inicie sesiones de respuesta en directo.

#### <a name="to-upload-a-file-in-the-library"></a>Para cargar un archivo en la biblioteca

1. Haga **clic Upload archivo en la biblioteca**.

2. Haga **clic en** Examinar y seleccione el archivo.

3. Proporcione una breve descripción.

4. Especifica si quieres sobrescribir un archivo con el mismo nombre.

5. Si desea serlo, sepa qué parámetros son necesarios para el script, active la casilla parámetros de script. En el campo de texto, escriba un ejemplo y una descripción.

6. Haga clic **en Confirmar**.

7. (Opcional) Para comprobar que el archivo se ha cargado en la biblioteca, ejecute el `library` comando.

### <a name="cancel-a-command"></a>Cancelar un comando

En cualquier momento durante una sesión, puede cancelar un comando presionando CTRL + C.

> [!WARNING]
> El uso de este acceso directo no detendrá el comando en el lado del agente. Solo cancelará el comando en el portal. Por lo tanto, el cambio de operaciones como "remediate" puede continuar, mientras que el comando se cancela.

## <a name="run-a-script"></a>Ejecutar un script

Antes de poder ejecutar scripts de PowerShell/Bash, primero debe cargarlo en la biblioteca.

Después de cargar el script en la biblioteca, use el `run` comando para ejecutar el script.

Si tiene previsto usar un script de PowerShell sin signo en la sesión, deberá habilitar la configuración en la [página Configuración de características avanzadas.](advanced-features.md)

> [!WARNING]
> Permitir el uso de scripts sin signo puede aumentar la exposición a amenazas.

## <a name="apply-command-parameters"></a>Aplicar parámetros de comando

- Vea la ayuda de la consola para obtener información sobre los parámetros de comandos. Para obtener información sobre un comando individual, ejecute:

  ```powershell
  help <command name>
  ```

- Al aplicar parámetros a comandos, tenga en cuenta que los parámetros se controlan en función de un orden fijo:

  ```powershell
  <command name> param1 param2
  ```

- Al especificar parámetros fuera del orden fijo, especifique el nombre del parámetro con un guión antes de proporcionar el valor:

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

## <a name="supported-output-types"></a>Tipos de salida compatibles

La respuesta en directo admite tipos de salida de formato JSON y tabla. Para cada comando, hay un comportamiento de salida predeterminado. Puede modificar el resultado en el formato de salida preferido mediante los siguientes comandos:

- `-output json`
- `-output table`

> [!NOTE]
> Se muestran menos campos en formato de tabla debido al espacio limitado. Para ver más detalles en el resultado, puede usar el comando de salida JSON para que se muestran más detalles.

## <a name="supported-output-pipes"></a>Canalizaciones de salida admitidas

La respuesta en directo admite la canalización de salida a la CLI y al archivo. CLI es el comportamiento de salida predeterminado. Puede canalizar el resultado a un archivo mediante el siguiente comando: [comando] > [filename].txt.

Ejemplo:

```console
processes > output.txt
```

## <a name="view-the-command-log"></a>Ver el registro de comandos

Selecciona la **pestaña Registro de** comandos para ver los comandos usados en el dispositivo durante una sesión. Cada comando se realiza un seguimiento con detalles completos como:

- Id.
- Línea de comandos
- Duración
- Estado y barra lateral de entrada o salida

## <a name="limitations"></a>Limitaciones

- Las sesiones de respuesta en directo están limitadas a 25 sesiones de respuesta en directo a la vez.
- El valor de tiempo de espera inactivo de la sesión de respuesta en directo es de 30 minutos.
- Un usuario puede iniciar hasta 10 sesiones simultáneas.
- Un dispositivo solo puede estar en una sesión a la vez.
- Se aplican los siguientes límites de tamaño de archivo:
  - `getfile` límite: 3 GB
  - `fileinfo` límite: 10 GB
  - `library` límite: 250 MB

## <a name="related-article"></a>Artículo relacionado

- [Ejemplos de comandos de respuesta en vivo](live-response-command-examples.md)
