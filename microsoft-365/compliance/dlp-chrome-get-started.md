---
title: Introducción a la extensión de cumplimiento de Microsoft
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Prepárese para implementar la extensión de cumplimiento de Microsoft.
ms.openlocfilehash: 5a2fa5958117d14715292245924dce2ff63b09a0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843835"
---
# <a name="get-started-with-microsoft-compliance-extension"></a>Introducción a la extensión de cumplimiento de Microsoft

Use estos procedimientos para implementar la extensión de cumplimiento de Microsoft.

## <a name="before-you-begin"></a>Antes de empezar

Para usar la extensión de cumplimiento de Microsoft, el dispositivo debe haber sido incorporado a la DLP del punto de conexión Consulte estos artículos si la DLP o la DLP del punto de conexión son algo nuevo para usted.

- [Información sobre la extensión de cumplimiento de Microsoft](dlp-chrome-learn-about.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
- [Herramientas y métodos de incorporación para dispositivos Windows 10](dlp-configure-endpoints.md)
- [Configurar la conexión a Internet y el proxy del dispositivo para la DLP de punto de conexión](endpoint-dlp-configure-proxy.md)
- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a>Licencias de SKU y suscripciones

Antes de empezar, debe confirmar la [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y cualquier complemento. Para acceder y usar la funcionalidad Endpoint DLP, debe tener una de estas suscripciones o complementos.

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Cumplimiento de Microsoft 365 E5
- Cumplimiento de Microsoft 365 A5
- Gobierno y protección de información de Microsoft 365 E5
- Gobierno y protección de información de Microsoft 365 A5

Para una guía detallada sobre las licencias, vea: [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

- Su organización debe tener la licencia de DLP para punto de conexión
- Sus dispositivos deben ejecutar Windows 10 x64 compilación 1809 o posterior.
- El dispositivo debe tener la versión del cliente antimalware 4.18.2101.9 o posterior. Para comprobar la versión actual, abra la aplicación de **Seguridad de Windows**, seleccione el icono **Configuración** y, a continuación, **Acerca de**.


### <a name="permissions"></a>Permisos

Los datos de Endpoint DLP se pueden ver en el [Explorador de actividad](data-classification-activity-explorer.md). Hay siete roles que conceden permisos al explorador de actividad; la cuenta que use para acceder a los datos debe pertenecer a uno de ellos.

- Administrador global
- Administrador de cumplimiento
- Administrador de seguridad
- Administrador de datos de cumplimiento
- Lector global
- Lector de seguridad
- Lector de informes

### <a name="overall-installation-workflow"></a>Flujo general de trabajo de la instalación

La implementación de la extensión de cumplimiento de Microsoft es un proceso de varias fases. Puede elegir entre instalar en las máquinas de una en una o usar Microsoft Endpoint Manager o la directiva de grupo para la implementación a nivel de la organización.

1. [Preparar sus dispositivos](#prepare-your-devices).
2. [Autohospedaje de máquina única de instalación básica](#basic-setup-single-machine-selfhost)
3. [Implementar con Microsoft Endpoint Manager](#deploy-using-microsoft-endpoint-manager)
4. [Implementar mediante la directiva de grupo](#deploy-using-group-policy)
5. [Probar la extensión](#test-the-extension)
6. [Usar el panel de administración de alertas para ver las alertas de DLP de Chrome](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [Visualizar datos de DLP de Chrome en el explorador de actividad](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a>Preparar la infraestructura

Si va a implementar la extensión de cumplimiento de Microsoft en todos sus dispositivos Windows 10 supervisados, debería quitar Google Chrome de las listas de aplicaciones y de exploradores no permitidos. Para más información, consulte [Exploradores no permitidos](endpoint-dlp-using.md#unallowed-browsers). Si solo va a realizar la implementación en unos pocos dispositivos, puede dejar Chrome en las listas de aplicaciones o exploradores no permitidos. La extensión de cumplimiento de Microsoft ignorará las restricciones de ambas listas para aquellos equipos en los que se haya instalado.  

### <a name="prepare-your-devices"></a>Preparar sus dispositivos

1. Use los procedimientos de estos temas para incorporar sus dispositivos:
    1. [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
    1. [Herramientas y métodos de incorporación para dispositivos Windows 10](dlp-configure-endpoints.md)
    1. [Configurar la conexión a Internet y el proxy del dispositivo para la DLP de punto de conexión](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a>Autohospedaje de máquina única de instalación básica

Esta método es el recomendado. 

1. Inicie sesión en el equipo de Windows 10 en el que quiera instalar la extensión de cumplimiento de Microsoft y ejecute este script de PowerShell como administrador. 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  Vaya a [Extensión de cumplimiento de Microsoft - Almacén web de Chrome (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).

3.  Instale la extensión mediante las instrucciones de la página del almacén web de Chrome.

### <a name="deploy-using-microsoft-endpoint-manager"></a>Implementación con Microsoft Endpoint Manager

Use este método de configuración para implementaciones a nivel de la organización.


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a>Habilitar la clave del registro requerida mediante Microsoft Endpoint Manager

1.  Cree un script de PowerShell con el contenido siguiente:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com).

3.  Vaya a **Dispositivos** > **Scripts** y seleccione **Agregar**.

4.  Cuando se le solicite, vaya a la ubicación del script creado.

5.  Seleccione la siguiente configuración:
    1. Ejecutar este script con las credenciales de inicio de sesión: SÍ
    1. Aplicar comprobación de firma de script: NO
    1. Ejecutar script en host de PowerShell de 64 bits: SÍ

6.  Seleccione los grupos adecuados de dispositivos y aplique la directiva.

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Pasos para la instalación forzada de Microsoft Endpoint Manager

Antes de agregar la extensión de cumplimiento de Microsoft a la lista de extensiones instaladas de manera forzosa, es importante incorporar ADMX de Chrome. Los pasos de este proceso en Microsoft Endpoint Manager son documentados por Google: [Administrar el explorador Chrome con Microsoft Intune - Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).

 Tras incorporar ADMX, se pueden dar los siguientes pasos para crear un perfil de configuración para esta extensión.

1.  Inicie sesión en el Centro de administración de Microsoft Endpoint Manager (https://endpoint.microsoft.com).

2.  Vaya a Perfiles de configuración.

3.  Seleccione **Crear perfil**.

4.  Seleccione **Windows 10** como plataforma.

5.  Seleccione **Personalizado** como tipo de perfil.

6.  Seleccione la pestaña **Configuración**.

7.  Seleccione **Agregar**.

8.  Escriba la información siguiente de directiva:
    
    OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    Tipo de datos: `String`<br/>
    Valor: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9.  Haga clic en Crear

### <a name="deploy-using-group-policy"></a>Implementar mediante la directiva de grupo

Si no quiere usar Microsoft Endpoint Manager, puede usar directivas de grupo para implementar la extensión de cumplimiento de Microsoft en toda la organización

1. Sus dispositivos deben poder ser administrados mediante la directiva de grupo, y debe importar todos los ADMX de Chrome en el almacén central de la directiva de grupo. Para más información, consulte [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

2.  Crear un script de PowerShell mediante este comando de PowerShell:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  Abra la **Consola de administración de la directiva de grupo** y vaya a la unidad organizativa (OU).

4.  Haga clic y seleccione **Crear un GPO en este dominio y vincularlo aquí**. Cuando se solicite, asigne un nombre descriptivo a este objeto de directiva de grupo (GPO) y finalice la creación.

5.  Haga clic en el GPO y seleccione **Editar**.

6.  Vaya a **Configuración del equipo** > **Preferencias** > **Configuración del panel de control** > **Tareas programadas**.

7.  Cree una nueva tarea inmediata. Para ello, haga clic y seleccione **Nuevo** > **Tarea inmediata (al menos Windows 7)**.

8.  Asigne un nombre y una descripción a la tarea.

9.  Elija la cuenta correspondiente para ejecutar la tarea inmediata, por ejemplo NT Authority.

10. Seleccione **Ejecutar con los privilegios más altos**.

11. Configure la directiva para Windows 10.

12. En la pestaña **Acciones**, seleccione la acción **Iniciar un programa**.

13. Escriba la ruta de acceso al Programa/Script creado en el paso 1.

14. Seleccione **Aplicar**.

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>Agregar la extensión de Chrome a la lista ForceInstall

1.  En el Editor de administración de directivas de grupo, vaya a su OU.

2.  Expanda la siguiente ruta **Configuración del equipo/usuario** > **Directivas** > **Plantillas administrativas** > **Plantillas administrativas clásicas** > **Google** > **Google Chrome** > **Extensiones**. Esta ruta puede variar en función de su configuración.

3.  Seleccione **Configurar la lista de extensiones instaladas de manera forzosa**.

4.  Haga clic con el botón derecho y seleccione **Editar**.

5.  Seleccione **Habilitado**.

6.  Seleccionar **Mostrar**.

7.  En **Valor**, agregue la siguiente entrada: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8.  Seleccione **Aceptar** y, luego, **Aplicar**.

### <a name="test-the-extension"></a>Probar la extensión

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a>Cargar en el servicio en la nube o acceso por salida de la nube de exploradores no permitidos  

1. Cree u obtenga un elemento confidencial y pruebe a cargar un archivo a uno de los dominios de servicio restringido de la organización. Los datos confidenciales deben coincidir con uno de nuestros [Tipos de información confidencial](sensitive-information-type-entity-definitions.md) o con uno de los tipos de información confidencial de su organización. Debería recibir una notificación del sistema DLP en el dispositivo en el que esté probando que muestre que esta acción no está permitida cuando el archivo está abierto.

#### <a name="testing-other-dlp-scenarios-in-chrome"></a>Probar otros escenarios DLP en Chrome 

Ahora que ha quitado Chrome de la lista de aplicaciones/exploradores no permitidos, puede probar los siguientes escenarios para confirmar que el comportamiento se ajusta a los requisitos de su organización:

- Copiar datos de un elemento confidencial a otro documento mediante el Portapapeles
    - Para probarlo, abra un archivo que esté protegido contra acciones de copiar al portapapeles en el explorador Chrome y trate de copiar datos del archivo.
    - Resultado esperado: se muestra una notificación de sistema de DLP que indica que esta acción no se permite cuando el archivo está abierto.
- Imprimir un documento
    - Para probarlo, abra un archivo que esté protegido contra acciones de impresión en el explorador Chrome y trate de imprimir el archivo.
    - Resultado esperado: se muestra una notificación de sistema de DLP que indica que esta acción no se permite cuando el archivo está abierto.
- Copiar en un medio extraíble USB
    - Para probarlo, trate de guardar el archivo en un almacenamiento de medio extraíble.
    - Resultado esperado: se muestra una notificación de sistema de DLP que indica que esta acción no se permite cuando el archivo está abierto.
- Copiar en un recurso compartido de red
    - Para probarlo, trate de guardar el archivo en un recurso compartido de red.
    - Resultado esperado: se muestra una notificación de sistema de DLP que indica que esta acción no se permite cuando el archivo está abierto.


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a>Usar el panel de administración de alertas para ver las alertas de DLP de Chrome

1. Abra la página sobre la **Prevención de pérdida de datos** en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) y seleccione **Alertas**.

2. Vea los procedimientos descritos en [Cómo configurar y ver las alertas de las directivas DLP](dlp-configure-view-alerts-policies.md) para ver las alertas de las directivas DLP del punto de conexión.


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>Visualizar datos de Endpoint DLP en el explorador de actividad

1. Abra la [Página clasificación de datos](https://compliance.microsoft.com/dataclassification?viewid=overview) del dominio en el Centro de cumplimiento de Microsoft 365 y elija **Explorador de actividad**.

2. Consulte los procedimientos descritos en [Introducción al explorador de actividad](data-classification-activity-explorer.md) para tener acceso a todos los datos de los dispositivos con Endpoint y filtrarlos.

   > [!div class="mx-imgBorder"]
   > ![filtro de explorador de actividad filtro para dispositivos de punto de conexión](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>Problemas y limitaciones conocidos

1. No se admite la Invalidación del bloqueo para la salida de la nube.
2. No se admite el modo incógnito y se debe deshabilitar.

## <a name="next-steps"></a>Pasos siguientes
Ahora que tiene dispositivos incorporados y puede ver los datos de la actividad en el explorador de actividad, está listo para realizar el siguiente paso, donde puede crear directivas DLP que protegen los elementos confidenciales.

- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md)

## <a name="see-also"></a>Consulte también

- [Obtenga información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/)
- [Herramientas y métodos de incorporación para equipos con Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).
- [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivos de Azure AD Unidos](/azure/active-directory/devices/concept-azure-ad-join)
- [Descargar el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
