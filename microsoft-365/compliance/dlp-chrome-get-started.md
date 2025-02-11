---
title: Introducción a la extensión de Microsoft Purview
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
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- highpri
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: Prepárese para implementar la extensión de Microsoft Purview.
ms.openlocfilehash: 2349e0461d7bad7ee7f09ce4033774bf94c9b525
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2022
ms.locfileid: "68793684"
---
# <a name="get-started-with-microsoft-purview-extension"></a>Introducción a la extensión de Microsoft Purview

Use estos procedimientos para implementar la extensión de Microsoft Purview.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-begin"></a>Antes de empezar

Para usar la extensión de Microsoft Purview, el dispositivo debe haber sido incorporado a la DLP del punto de conexión Consulte estos artículos si la DLP o la DLP del punto de conexión son algo nuevo para usted.

- [Más información sobre la extensión de Microsoft Purview](dlp-chrome-learn-about.md)
- [Información sobre la prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
- [Herramientas y métodos de incorporación para dispositivos Windows 10](device-onboarding-overview.md)
- [Configurar la configuración de proxy de dispositivo y conexión a Internet para Information Protection](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection)
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
- El dispositivo debe tener la versión de cliente antimalware 4.18.2202.x o posterior. Para comprobar la versión actual, abra la aplicación de **Seguridad de Windows**, seleccione el icono **Configuración** y, a continuación, **Acerca de**.


### <a name="permissions"></a>Permisos

Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md). There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.

- Administrador global
- Administrador de cumplimiento
- Administrador de seguridad
- Administrador de datos de cumplimiento
- Lector global
- Lector de seguridad
- Lector de informes

#### <a name="roles-and-role-groups"></a>Roles y grupos de roles

Hay roles y grupos de roles en la versión preliminar que puede probar para ajustar los controles de acceso.

Esta es una lista de los roles aplicables que se encuentran en versión preliminar. Para obtener más información sobre ellos, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md).

- Administrador de Information Protection
- Analista de Information Protection
- Investigador de protección de información
- Lector de protección de información

Esta es una lista de los grupos de roles aplicables que se encuentran en versión preliminar. Para obtener más información sobre, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md).

- Protección de la información
- Administradores de Information Protection
- Analistas de Information Protection
- Investigadores de Information Protection
- Lectores de Information Protection

### <a name="overall-installation-workflow"></a>Flujo general de trabajo de la instalación

La implementación de la extensión es un proceso de varias fases. Puede elegir entre instalar en las máquinas de una en una o usar Microsoft Endpoint Manager o la directiva de grupo para la implementación a nivel de la organización.

1. [Preparar sus dispositivos](#prepare-your-devices).
2. [Autohospedaje de máquina única de instalación básica](#basic-setup-single-machine-selfhost)
3. [Implementar con Microsoft Endpoint Manager](#deploy-using-microsoft-endpoint-manager)
4. [Implementar mediante la directiva de grupo](#deploy-using-group-policy)
5. [Probar la extensión](#test-the-extension)
6. [Usar el panel de administración de alertas para ver las alertas de DLP de Chrome](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [Visualizar datos de DLP de Chrome en el explorador de actividad](#viewing-chrome-dlp-data-in-activity-explorer)

### <a name="prepare-infrastructure"></a>Preparar la infraestructura

Si va a implementar la extensión en todos sus dispositivos Windows 10 supervisados, debería quitar Google Chrome de las listas de aplicaciones y de exploradores no permitidos. Para más información, consulte [Exploradores no permitidos](dlp-configure-endpoint-settings.md#unallowed-browsers). Si solo va a realizar la implementación en unos pocos dispositivos, puede dejar Chrome en las listas de aplicaciones o exploradores no permitidos. La extensión ignorará las restricciones de ambas listas para aquellos equipos en los que se haya instalado.

### <a name="prepare-your-devices"></a>Preparar sus dispositivos

1. Use los procedimientos de estos temas para incorporar sus dispositivos:
    1. [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
    1. [Incorporación de dispositivos Windows 10 y Windows 11](device-onboarding-overview.md)
    1. [Configurar la configuración de proxy de dispositivo y conexión a Internet para Information Protection](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection)

### <a name="basic-setup-single-machine-selfhost"></a>Autohospedaje de máquina única de instalación básica

Esta método es el recomendado.

1. Vaya a [Extensión de Microsoft Purview: Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).

2. Instale la extensión mediante las instrucciones de la página del almacén web de Chrome.

### <a name="deploy-using-microsoft-endpoint-manager"></a>Implementación con Microsoft Endpoint Manager

Use este método de configuración para implementaciones a nivel de la organización.

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Pasos para la instalación forzada de Microsoft Endpoint Manager

Antes de agregar la extensión a la lista de extensiones instaladas de manera forzosa, es importante incorporar ADMX de Chrome. Los pasos de este proceso en Microsoft Endpoint Manager son documentados por Google: [Administrar el explorador Chrome con Microsoft Intune - Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).

 Tras incorporar ADMX, se pueden dar los siguientes pasos para crear un perfil de configuración para esta extensión.

1. Inicie sesión en el Centro de administración de Microsoft Endpoint Manager (https://endpoint.microsoft.com).

2. Vaya a Perfiles de configuración.

3. Seleccione **Crear perfil**.

4. Seleccione **Windows 10** como plataforma.

5. Seleccione **Personalizado** como tipo de perfil.

6. Seleccione la pestaña **Configuración**.

7. Seleccione **Agregar**.

8. Escriba la información siguiente de directiva:

    OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    Tipo de datos: `String`<br/>
    Valor: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9. Haga clic en Crear

### <a name="deploy-using-group-policy"></a>Implementar mediante la directiva de grupo

Si no quiere usar Microsoft Endpoint Manager, puede usar directivas de grupo para implementar la extensión en toda la organización.

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>Agregar la extensión de Chrome a la lista ForceInstall

1. En el Editor de administración de directivas de grupo, vaya a su OU.

2. Expanda la siguiente ruta **Configuración del equipo/usuario** > **Directivas** > **Plantillas administrativas** > **Plantillas administrativas clásicas** > **Google** > **Google Chrome** > **Extensiones**. Esta ruta puede variar en función de su configuración.

3. Seleccione **Configurar la lista de extensiones instaladas de manera forzosa**.

4. Haga clic con el botón derecho y seleccione **Editar**.

5. Seleccione **Habilitado**.

6. Seleccionar **Mostrar**.

7. En **Valor**, agregue la siguiente entrada: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8. Seleccione **Aceptar** y, luego, **Aplicar**.

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

1. Abra la página de **prevención de pérdida de datos** en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> y seleccione **Alertas**.

2. Vea los procedimientos descritos en [Cómo configurar y ver las alertas de las directivas DLP](dlp-configure-view-alerts-policies.md) para ver las alertas de las directivas DLP del punto de conexión.

### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>Visualizar datos de Endpoint DLP en el explorador de actividad

1. Abra la [página Clasificación de datos](https://compliance.microsoft.com/dataclassification?viewid=overview) del dominio en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a> y elija **Explorador de actividad**.

2. Consulte los procedimientos descritos en [Introducción al explorador de actividad](data-classification-activity-explorer.md) para tener acceso a todos los datos de los dispositivos con Endpoint y filtrarlos.

   > [!div class="mx-imgBorder"]
   > ![filtro de explorador de actividad para dispositivos de punto de conexión.](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>Problemas y limitaciones conocidos

1. No se admite el modo incógnito y se debe deshabilitar.

## <a name="next-steps"></a>Pasos siguientes

Ahora que tiene dispositivos incorporados y puede ver los datos de la actividad en el explorador de actividad, está listo para realizar el siguiente paso, donde puede crear directivas DLP que protegen los elementos confidenciales.

- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md)

## <a name="see-also"></a>Consulte también

- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/)
- [Herramientas y métodos de incorporación para equipos con Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).
- [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivos de Azure AD Unidos](/azure/active-directory/devices/concept-azure-ad-join)
- [Descargar el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
