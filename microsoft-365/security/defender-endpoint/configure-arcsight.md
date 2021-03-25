---
title: Configurar Micro Focus ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión
description: Configurar Micro Focus ArcSight para recibir y extraer detecciones del Centro de seguridad de Microsoft Defender
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
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166190"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>Configurar Micro Focus ArcSight para extraer Defender para detecciones de puntos de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

Tendrás que instalar y configurar algunos archivos y herramientas para usar Micro Focus ArcSight para que pueda extraer Defender para detecciones de puntos de conexión.

>[!Note]
>- [Defender for Endpoint Alert](alerts.md) se compone de una o más detecciones
>- [Defender para la detección de](api-portal-mapping.md) puntos de conexión se compone del evento sospechoso que se produjo en el dispositivo y sus detalles de alerta relacionados.

## <a name="before-you-begin"></a>Antes de empezar

La configuración de la herramienta Micro Focus ArcSight Connector requiere varios archivos de configuración para que extraiga y analice las detecciones de la aplicación de Azure Active Directory (AAD).

Esta sección le guía para obtener la información necesaria para establecer y usar correctamente los archivos de configuración necesarios.

- Asegúrese de que ha habilitado la característica de integración siem desde el **menú** Configuración. Para obtener más información, vea [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).

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

1. Instala el instalador más reciente de Windows FlexConnector de 32 bits. Puedes encontrarlo en el Centro de software de HPE. La herramienta suele instalarse en la siguiente ubicación predeterminada: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</br></br>Puede elegir dónde guardar la herramienta, por ejemplo C: folder_location \\ \current\bin donde *folder_location* representa la ubicación de instalación.

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
   > 
   > Debe colocar los archivos de configuración en esta ubicación, donde *folder_location* representa la ubicación donde instaló la herramienta.

4. Una vez completada la instalación del conector principal, se abrirá la ventana Configuración del conector. En la ventana Configuración del conector, seleccione **Agregar un conector**.

5. Seleccione Tipo: **ArcSight FlexConnector REST** y haga clic **en Siguiente**.

6. Escriba la siguiente información en el formulario de detalles del parámetro. Todos los demás valores del formulario son opcionales y se pueden dejar en blanco.

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th>Campo</th>
    <th>Valor</th>
    </tr>
    <tr>
    <td>Archivo de configuración</td>
    <td>Escriba el nombre del archivo de propiedad de cliente. El nombre debe coincidir con el archivo proporcionado en el archivo .zip que descargó.
Por ejemplo, si el archivo de configuración del directorio flexagent se denomina &quot; &quot;WDATP-Connector.js&quot; onparser.properties , debe escribir &quot; &quot; WDATP-Connector &quot; como el nombre del archivo de propiedad del cliente.</td>
    </tr>
    <td>Dirección URL de eventos</td>
    <td>En función de la ubicación del centro de datos, seleccione la dirección URL de la UE o estados unidos: </br></br> <b>Para la</b>UE : https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br>
   </br><b>Para ESTADOS UNIDOS:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br> <br> <b>Para Reino</b>Unido : https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</td>
    <tr>
    <td>Tipo de autenticación</td>
    <td>OAuth 2</td>
    </tr>
    <td>Archivo de propiedades de cliente de OAuth 2</td>
    <td>Vaya a la ubicación del <em>archivo wdatp-connector.properties.</em> El nombre debe coincidir con el archivo proporcionado en el archivo .zip que descargó.</td>
    <tr>
    <td>Token de actualización</td>
    <td>Puede obtener un token de actualización de dos maneras: generando un token de actualización desde la página de configuración de <b>SIEM</b> o usando la herramienta restutil. <br><br> Para obtener más información sobre cómo <b></b> generar un token de actualización desde la configuración de preferencias, vea <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>. </br> </br><b>Obtenga el token de actualización con la herramienta restutil:</b> </br> a. Abra un símbolo del sistema. Vaya a C:\<em>folder_location</em>\current\bin donde <em>folder_location</em> representa la ubicación donde instaló la herramienta. </br></br> b. Tipo: <code>arcsight restutil token -config</code> desde el directorio bin. Por ejemplo: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Se abrirá una ventana del explorador web. </br> </br>c. Escriba sus credenciales y, a continuación, haga clic en el campo de contraseña para permitir que la página redirija. En el símbolo del sistema de inicio de sesión, escriba sus credenciales. </br> </br>d. Se muestra un token de actualización en el símbolo del sistema. </br></br> e. Cópielo y péguelo en el <b>campo Actualizar token.</b>
    </td>
    </tr>
    </tr>
    </table><br/>
    
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

10. Establecer **producto de dispositivo = ATP de Microsoft Defender**. Cuando hayas comprobado que los eventos fluyen a la herramienta, detén el proceso de nuevo y ve a Servicios de Windows e inicia el REST de ArcSight FlexConnector.

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
- [Solucionar problemas de integración de herramientas SIEM](troubleshoot-siem.md)
