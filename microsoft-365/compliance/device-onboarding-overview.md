---
title: Introducción a la incorporación de dispositivos Windows 10 o Windows 11 a Microsoft 365
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
description: Incorporación de dispositivos Windows 10 y Windows 11 a Microsoft 365
ms.openlocfilehash: a83db434b488ce28c71df0fb7e3185be88b87b01
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950949"
---
# <a name="onboard-windows-10-and-windows-11-devices-into-microsoft-365-overview"></a>Introducción a la incorporación de dispositivos Windows 10 y Windows 11 a Microsoft 365 

**Se aplica a:**

- [Prevención de pérdida de datos en punto de conexión en Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

Prevención de pérdida de datos en punto de conexión en Microsoft 365 (punto de conexión DLP) y administración de riesgos internos requieren que los dispositivos Windows 10 y Windows 11 se incorporen al servicio para que puedan enviar datos de supervisión a los servicios.
 
El punto de conexión DLP de Microsoft 365 permite supervisar dispositivos Windows 10 o Windows 11 y detectar cuándo se usan y comparten elementos confidenciales. Esto le proporciona la visibilidad y el control que necesita para asegurarse de que se usan y protegen correctamente, así como para ayudar a evitar algún comportamiento peligroso que podría comprometerlos. Para obtener más información sobre las ofertas de DLP de Microsoft, consulte [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md). Para obtener más información sobre el punto de conexión DLP, consulte [Obtener información sobre la prevención de pérdida de datos del punto de conexión](endpoint-dlp-learn-about.md).

La administración de riesgos internos usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, evaluar prioridades y actuar rápidamente en la actividad de usuario de riesgo. Al usar registros de Microsoft 365 y Microsoft Graph, la administración de riesgos internos le permite definir directivas específicas para identificar indicadores de riesgo y tomar medidas para mitigar estos riesgos. Para obtener más información, consulte [Obtenga información sobre la administración de riesgos internos en Microsoft 365](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365).

La incorporación de dispositivos se comparte en Microsoft 365 y Microsoft Defender para punto de conexión (MDE). Si ya has incorporado dispositivos a MDE, aparecerán en la lista de dispositivos administrados y no se necesitan pasos adicionales para incorporar esos dispositivos específicos. Los dispositivos de incorporación en el Centro de cumplimiento también se incorporan a MDE.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Compruebe los requisitos de licencia [aquí](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="permissions"></a>Permisos

Para habilitar la administración de dispositivos, la cuenta que use debe pertenecer a uno de los siguientes roles:

- Administrador global
- Administrador de seguridad
- Administrador de cumplimiento

Si desea usar una cuenta personalizada para ver la configuración de administración de dispositivos, debe tener uno de estos roles:

- Administrador global
- Administrador de cumplimiento
- Administrador de datos de cumplimiento
- Lector global

Si desea usar una cuenta personalizada para acceder a la página de incorporación y baja, debe tener uno de estos roles:

- Administrador global
- Administrador de cumplimiento

Si desea usar una cuenta personalizada para activar o desactivar la supervisión de dispositivos, debe tener uno de estos roles:

- Administrador global
- Administrador de cumplimiento

### <a name="prepare-your-windows-devices"></a>Preparar sus dispositivos Windows 

Asegúrese de que los dispositivos Windows que necesite incorporar cumplan estos requisitos.

1. Debe ejecutarse Windows 10 x64 compilación 1809 o posterior o Windows 11.

2. La versión del cliente antimalware es 4.18.2009.7 o posterior. Para comprobar la versión actual, abra la aplicación de Seguridad de Windows, seleccione el icono Configuración y, a continuación, Acerca de. El número de versión aparece en la versión del cliente antimalware. Instale Windows Update KB4052623 para actualizar a la última versión del cliente antimalware.

   > [!NOTE]
   > Ningún componente de Seguridad de Windows necesita estar activo, pero[la protección en tiempo real y el monitor de comportamiento](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) ) deben estar habilitados.

3. Las siguientes actualizaciones de Windows para Windows 10 se instalan para los dispositivos que se supervisarán.

   > [!NOTE]
   > Estas actualizaciones no son un requisito previo para incorporar un dispositivo, pero contienen correcciones para problemas importantes, por lo que deben instalarse antes de usar el producto.
   >
    > - For Windows 10 1809 - KB4559003, KB4577069, KB4580390
    > - Para Windows 10 1903 o 1909 - KB4559004, KB4577062, KB4580386
    > - For Windows 10 2004 - KB4568831, KB4577063

4. Todos los dispositivos deben cumplir una de estas opciones:

   - [Unido a Azure Active Directory (Azure AD)](/azure/active-directory/devices/concept-azure-ad-join)
   - [Unido a Azure AD híbrido ](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
   - [Registrado en AAD](/azure/active-directory/user-help/user-help-register-device-on-network)

5. Para dispositivos que ejecutan Office 2016 (en lugar de cualquier otra versión de Office): KB4577063

6. Si se encuentra en el Canal mensual para empresas de Aplicaciones de Microsoft 365 versiones 2004-2008, existe un problema conocido con la clasificación de contenido Office y debe actualizar a la versión 2009 o posterior. Vea [Historial de actualizaciones de las Aplicaciones de Microsoft 365 (enumeradas por fecha)](/officeupdates/update-history-microsoft365-apps-by-date) las versiones actuales. Para obtener más información sobre este problema, vea la sección Office Suite de [Notas de la versión para obtener las versiones del canal actuales en 2020](/officeupdates/current-channel#version-2010-october-27).

7. Si tiene puntos de conexión que usan un proxy de dispositivo para conectarse a Internet, siga los procedimientos descritos en [Configurar el proxy del dispositivo y la conexión a Internet para Information Protection](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection).

## <a name="onboarding-windows-10-or-windows-11-devices"></a>Incorporación de dispositivos Windows 10 o Windows 11 

Para poder supervisar y proteger los elementos confidenciales de un dispositivo, es necesario que habilite la supervisión del dispositivo y que incorpore los puntos de conexión. Ambas acciones se realizan en el portal de cumplimiento de Microsoft 365.

Cuando quiera incorporar dispositivos que todavía no hayan sido incorporados, descargue el script apropiado y, luego, impleméntelo en esos dispositivos. Siga los procedimientos de incorporación de dispositivos que se indican a continuación.

Si ya tiene dispositivos incorporados en [ Microsoft Defender para punto de conexión (MDATP)](/windows/security/threat-protection/), estos aparecerán en la lista de dispositivos administrados.

En este escenario de implementación, incorporarás dispositivos Windows 10 o Windows 11 que aún no se han incorporado.

1. Abra el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com). Elija **Configuración**  >  **Habilitar la supervisión de dispositivos**.

   > [!NOTE]
   > Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.

2. Abra la página de configuración del Centro de cumplimiento y elija **Incorporar dispositivos**.

   > [!div class="mx-imgBorder"]
   > ![habilitar la administración de dispositivos.](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

3. Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**. 

> [!NOTE]
> Si ya has implementado Microsoft Defender para punto de conexión, todos los dispositivos que se incorporaron durante ese proceso aparecerán en la **lista Dispositivos**. No es necesario incorporarlos de nuevo.

4. Elija **Incorporación** para iniciar el proceso de incorporación.

5. Elija el modo en que desea implementar estos dispositivos adicionales de la lista **Método de implementación** y, después, **Descargar paquete**.

6. Elija el procedimiento adecuado que se debe seguir en la tabla siguiente:

Tema | Descripción
:---|:---
[Incorporación de dispositivos Windows 10 o 11 con directiva de grupo](device-onboarding-gp.md) | Utilice Directiva de grupo para implementar el paquete de configuración en los dispositivos.
[Incorpore dispositivos Windows 10 o 11 con Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md) | Puede usar Microsoft Endpoint Configuration Manager (rama actual) versión 1606 o Microsoft Endpoint Configuration Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en dispositivos.
[Incorpore los dispositivos Windows 10 o 11 con herramientas de administración de dispositivos móviles](device-onboarding-mdm.md) | Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.
[Incorpore los dispositivos Windows 10 o 11 con un script local](device-onboarding-script.md) | Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.
[Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](device-onboarding-vdi.md) | Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.

Una vez que un dispositivo está incorporado, debe estar visible en la lista de dispositivos y también empezar a informar de los registros de actividad de auditoría en el Explorador de actividades.

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>Visualizar alertas de DLP del punto de conexión en el panel de administración de alertas de DLP

1. Abra la página Prevención de pérdida de datos en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a> y elija Alertas.

2. Consulte los procedimientos descritos en [Cómo configurar y ver las alertas de las directivas DLP](dlp-configure-view-alerts-policies.md) para ver las alertas de las directivas DLP del punto de conexión.

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>Visualizar datos de Endpoint DLP en el explorador de actividad

1. Abra la [Página clasificación de datos](https://compliance.microsoft.com/dataclassification?viewid=overview) del dominio en el Centro de cumplimiento de Microsoft 365 y elija Explorador de actividad.

2. Consulte los procedimientos descritos en [Introducción al explorador de actividad](data-classification-activity-explorer.md) para tener acceso a todos los datos de los dispositivos con Endpoint y filtrarlos.

   > [!div class="mx-imgBorder"]
   > ![filtro de explorador de actividad para dispositivos de punto de conexión.](../media/endpoint-dlp-4-getting-started-activity-explorer.png)


## <a name="see-also"></a>Consulte también

- [Obtenga información sobre la administración de riesgos internos en Microsoft 365](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
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
