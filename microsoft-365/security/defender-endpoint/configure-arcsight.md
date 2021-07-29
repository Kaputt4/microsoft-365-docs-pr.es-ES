---
title: Configurar Micro Focus ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión
description: Configurar Micro Focus ArcSight para recibir y extraer detecciones de Centro de seguridad de Microsoft Defender
keywords: configurar Micro Focus ArcSight, herramientas de administración de eventos y información de seguridad, arcsight
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8397731941a3344638edb0b57e77272f4fae930
ms.sourcegitcommit: af575ade7b187af70f94db904b03f0471f56452a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2021
ms.locfileid: "53591000"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>Configurar Micro Focus ArcSight para extraer Defender para detecciones de puntos de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink)

Tendrás que instalar y configurar algunos archivos y herramientas para usar Micro Focus ArcSight para que pueda extraer Defender para detecciones de puntos de conexión.

> [!NOTE]
>
>- [Defender for Endpoint Alert](alerts.md) se compone de una o más detecciones
>- [Defender para la detección de](api-portal-mapping.md) puntos de conexión se compone del evento sospechoso que se produjo en el dispositivo y sus detalles de alerta relacionados.

## <a name="before-you-begin"></a>Antes de empezar

La configuración de la herramienta Micro Focus ArcSight Connector requiere varios archivos de configuración para que extraiga y analice las detecciones de la aplicación Azure Active Directory (AAD).

Esta sección le guía para obtener la información necesaria para establecer y usar correctamente los archivos de configuración necesarios.

- Asegúrese de que ha habilitado la característica de integración siem desde **el Configuración** menú. Para obtener más información, vea [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).

- Tenga listo el archivo guardado para habilitar la característica de integración siem. Deberá obtener los siguientes valores:
  - URL de actualización de tokens de OAuth 2.0
  - Id. de cliente de OAuth 2.0
  - Secreto de cliente de OAuth 2.0

- Tenga los siguientes archivos de configuración listos:
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    Habría guardado un archivo .zip que contiene estos dos archivos al elegir Micro Focus ArcSight como el tipo SIEM que usa en su organización.

- Asegúrese de generar los siguientes tokens y tenerlos listos:
  - Token de acceso
  - Token de actualización

  Puede generar estos tokens desde la sección de configuración **de integración siem** del portal.

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>Instalar y configurar Micro Focus ArcSight FlexConnector

En los pasos siguientes se supone que ha completado todos los pasos necesarios en [Antes de comenzar](#before-you-begin).

1. Instale el último instalador de FlexConnector Windows de 32 bits. Puedes encontrarlo en el Centro de software de HPE. La herramienta suele instalarse en la siguiente ubicación predeterminada: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</br></br>Puede elegir dónde guardar la herramienta, por ejemplo C: folder_location \\ \current\bin donde *folder_location* representa la ubicación de instalación.

2. Siga el asistente de instalación a través de las siguientes tareas:
   - Introducción
   - Elegir instalar carpeta
   - Elegir instalar conjunto
   - Elegir carpeta de acceso directo
   - Resumen previo a la instalación
   - Instalación...

   Puede mantener los valores predeterminados para cada una de estas tareas o modificar la selección para que se adapte a sus requisitos.

3. Abra el Explorador de archivos y busque los dos archivos de configuración que guardó al habilitar la característica de integración siem. Ponga los dos archivos en la ubicación de instalación de FlexConnector, por ejemplo:

   - WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   - WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   > [!NOTE]
   > Debe colocar los archivos de configuración en esta ubicación, donde *folder_location* representa la ubicación donde instaló la herramienta.

4. Una vez completada la instalación del conector principal, se abrirá la ventana Configuración del conector. En la ventana Configuración del conector, seleccione **Agregar un conector**.

5. Seleccione Tipo: **ArcSight FlexConnector REST** y haga clic **en Siguiente**.

6. Escriba la siguiente información en el formulario de detalles del parámetro. Todos los demás valores del formulario son opcionales y se pueden dejar en blanco.

   <br>

   ****

   |Campo|Valor|
   |---|---|
   |Archivo de configuración|Escriba el nombre del archivo de propiedad de cliente. El nombre debe coincidir con el archivo proporcionado en el .zip que descargó. <p> Por ejemplo, si el archivo de configuración del directorio "flexagent" se denomina "WDATP-Connector.jsonparser.properties", debe escribir "WDATP-Connector" como el nombre del archivo de propiedad del cliente.|
   |Dirección URL de eventos|En función de la ubicación del centro de datos, seleccione la dirección URL de la UE o estados unidos: <ul><li>**Para la UE**:  `https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li><li>**Para EE. UU.**: `https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li><li>**Para Reino Unido**: `https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME`</li></ul>|
   |Tipo de autenticación|OAuth 2|
   |Archivo de propiedades de cliente de OAuth 2|Vaya a la ubicación del *archivo wdatp-connector.properties.* El nombre debe coincidir con el archivo proporcionado en el .zip que descargó.|
   |Token de actualización|Puede obtener un token de actualización de dos maneras: generando un token de actualización desde la página de configuración de **SIEM** o usando la herramienta restutil. <p> Para obtener más información sobre cómo  generar un token de actualización desde la configuración de preferencias, vea [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md). <p> **Obtenga el token de actualización con la herramienta restutil**: <ol><li>Abra un símbolo del sistema. Vaya a C: \\ *ubicación de \_ carpeta*\current\bin donde *la \_* ubicación de la carpeta representa la ubicación donde instaló la herramienta.</li><li>Tipo: `arcsight restutil token -config` desde el directorio bin. Por ejemplo: **arcsight restutil boxtoken -proxy proxy.location.hp.com:8080**. Se abrirá una ventana del explorador web.</li><li>Escriba sus credenciales y, a continuación, haga clic en el campo de contraseña para permitir que la página redirija. En el símbolo del sistema de inicio de sesión, escriba sus credenciales.</li><li>Se muestra un token de actualización en el símbolo del sistema.</li><li>Cópielo y péguelo en el **campo Actualizar token.**|
   |

7. El conector abre una ventana del explorador. Inicie sesión con las credenciales de la aplicación. Después de iniciar sesión, se le pedirá que le dé permiso a su cliente de OAuth2. Debe conceder permiso al cliente de OAuth 2 para que la configuración del conector pueda autenticarse.

   Si la <code>redirect_uri</code> dirección URL es https, se le redirigirá a una dirección URL en el host local. Verá una página que solicita que confíe en el certificado proporcionado por el conector que se ejecuta en el host local. Deberá confiar en este certificado si el redirect_uri es https.

   Sin embargo, si especifica una dirección URL http para el redirect_uri, no es necesario proporcionar consentimiento para confiar en el certificado.

8. Continúe con la configuración del conector volviendo a la ventana Configuración del conector de Micro Focus ArcSight.

9. Seleccione el **Administrador de ArcSight (cifrado)** como destino y haga clic en **Siguiente**.

10. Escriba el IP/nombre de host de destino en **Nombre de host** del administrador y sus credenciales en el formulario de parámetros. Todos los demás valores del formulario deben conservarse con los valores predeterminados. Haga clic en **Siguiente**.

11. Escriba un nombre para el conector en el formulario de detalles del conector. Todos los demás valores del formulario son opcionales y se pueden dejar en blanco. Haga clic en **Siguiente**.

12. Se muestra la ventana de certificado de importación del Administrador de ESM. Seleccione **Importar el certificado al conector del destino y** haga clic en **Siguiente**. Se **muestra la ventana Agregar resumen** del conector y se importa el certificado.

13. Compruebe que los detalles de la **ventana Agregar resumen** del conector son correctos y, a continuación, haga clic en **Siguiente**.

14. Seleccione **Instalar como servicio y** haga clic en **Siguiente**.

15. Escriba un nombre en el **campo Nombre interno del** servicio. Todos los demás valores del formulario se pueden conservar con los valores predeterminados o dejar en blanco . Haga clic en **Siguiente**.

16. Escriba los parámetros de servicio y haga clic en **Siguiente**. Se muestra una ventana **con el Resumen del** servicio de instalación. Haga clic en **Siguiente**.

17. Para finalizar la instalación, seleccione **Salir** y **Siguiente**.

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>Instalar y configurar la consola de Micro Focus ArcSight

1. Siga el asistente de instalación a través de las siguientes tareas:
   - Introducción
   - Contrato de licencia
   - Aviso especial
   - Elegir directorio de instalación de ArcSight
   - Elegir carpeta de acceso directo
   - Resumen previo a la instalación

2. Haga clic en **Instalar**. Una vez completada la instalación, se abrirá el Asistente para configuración de consola de ArcSight.

3. Escriba localhost en **Nombre de host del administrador** y 8443 en Puerto **del** administrador y, a continuación, haga clic **en Siguiente**.

4. Seleccione **Usar conexión directa y,** a continuación, haga clic en **Siguiente**.

5. Seleccione **Autenticación basada en contraseña** y, a continuación, haga clic en **Siguiente**.

6. Seleccione **Esta es una instalación de un solo usuario. (Recomendado)** y, a continuación, haga clic **en Siguiente**.

7. Haga **clic en** Listo para salir del instalador.

8. Inicie sesión en la consola de Micro Focus ArcSight.

9. Vaya a **Active channel set** New  >  **Condition**  >  **Device**  >  **Device Product**.

10. Establecer **producto de dispositivo = ATP de Microsoft Defender**. Cuando haya comprobado que los eventos fluyen a la herramienta, detenga el proceso de nuevo y vaya a Windows Services e inicie el REST de ArcSight FlexConnector.

Ahora puede ejecutar consultas en la consola de Micro Focus ArcSight.

Defender para detecciones de puntos de conexión aparecerá como eventos discretos, con "Microsoft" como proveedor y "Windows Defender ATP" como el nombre del dispositivo.

## <a name="troubleshooting-micro-focus-arcsight-connection"></a>Solución de problemas de conexión de Micro Focus ArcSight

**Problema:** No se pudo actualizar el token. Puede encontrar el registro ubicado en C: \\ *folder_location*\current\logs donde *folder_location* representa la ubicación donde instaló la herramienta. Abra _agent.log_ y busque `ERROR/FATAL/WARN` .

**Síntoma:** Obtiene el siguiente mensaje de error:

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**Solución:**

1. Detenga el proceso haciendo clic en Ctrl + C en la ventana Conector. Haga **clic en Y** cuando se le pregunte "¿Finalizar el trabajo por lotes Y/N?".

2. Navegue hasta la carpeta donde ha almacenado el archivo WDATP-connector.properties y edúzcalo para agregar el siguiente valor: `reauthenticate=true` .

3. Reinicie el conector ejecutando el siguiente comando: `arcsight.bat connectors` .

   Aparece una ventana del explorador. Permitir que se ejecute, debe desaparecer y el conector debería estar en ejecución.

> [!NOTE]
> Compruebe que el conector se está ejecutando deteniendo el proceso de nuevo. A continuación, vuelva a iniciar el conector y no debería aparecer ninguna ventana del explorador.

## <a name="related-topics"></a>Temas relacionados

- [Habilitar la integración de SIEM en Defender for Endpoint](enable-siem-integration.md)
- [Extraer detecciones a las herramientas SIEM](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [Pull Defender for Endpoint detections using REST API](pull-alerts-using-rest-api.md)
- [Solucionar problemas de integración de la herramienta SIEM](troubleshoot-siem.md)
