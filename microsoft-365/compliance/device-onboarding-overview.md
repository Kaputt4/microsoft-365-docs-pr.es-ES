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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Incorporación de dispositivos Windows 10 y Windows 11 a Microsoft 365
ms.openlocfilehash: 867a3e356592c054dd3badbc960a5ae4b7edc80a
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67343467"
---
# <a name="onboard-windows-10-and-windows-11-devices-into-microsoft-365-overview"></a>Introducción a la incorporación de dispositivos Windows 10 y Windows 11 a Microsoft 365 

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

Prevención de pérdida de datos en punto de conexión (punto de conexión DLP) y administración de riesgos internos requieren que los dispositivos Windows 11 y Windows 10 se incorporen al servicio para que puedan enviar datos de supervisión a los servicios.
 
La DLP de punto de conexión permite supervisar dispositivos Windows 10 o Windows 11 y detectar cuándo se usan y comparten elementos confidenciales. Esto le proporciona la visibilidad y el control que necesita para asegurarse de que se usan y protegen correctamente, así como para ayudar a evitar algún comportamiento peligroso que podría comprometerlos. Para obtener más información sobre las ofertas de DLP de Microsoft, consulte [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md). Para obtener más información sobre el punto de conexión DLP, consulte [Obtener información sobre la prevención de pérdida de datos del punto de conexión](endpoint-dlp-learn-about.md).

La administración de riesgos internos usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, evaluar prioridades y actuar rápidamente en la actividad de usuario de riesgo. Al usar registros de Microsoft 365 y Microsoft Graph, la administración de riesgos internos le permite definir directivas específicas para identificar indicadores de riesgo y tomar medidas para mitigar estos riesgos. Para obtener más información, consulte [Más información sobre la administración de riesgos internos](insider-risk-management.md).

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

2. La versión del cliente antimalware es 4.18.2110 o posterior. Para comprobar la versión actual, abra la aplicación de Seguridad de Windows, seleccione el icono Configuración y, a continuación, Acerca de. El número de versión aparece en la versión del cliente antimalware. Instale Windows Update KB4052623 para actualizar a la última versión del cliente antimalware.

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

5. Existe una versión compatible instalada y actualizada de Microsoft Office. Para obtener la protección y la experiencia de usuario más sólidas, asegúrese de que esté instalada la versión 16.0.14701.0 o posterior de Aplicaciones de Microsoft 365.
> [!NOTE]
   > - Si está ejecutando Office 365: es necesario 4577063 KB.
   > - Si está en el Canal mensual para empresas de Aplicaciones de Microsoft 365, versiones 2004-2008, debe actualizar a la versión 2009 o posterior. Vea [Historial de actualizaciones de las Aplicaciones de Microsoft 365 (enumeradas por fecha)](/officeupdates/update-history-microsoft365-apps-by-date) las versiones actuales. Para más información sobre este problema conocido, vea la sección Office Suite de [Notas de la versión para las versiones del canal actual en 2020](/officeupdates/current-channel#version-2010-october-27).

6. Si tiene puntos de conexión que usan un proxy de dispositivo para conectarse a Internet, siga los procedimientos descritos en [Configurar el proxy del dispositivo y la conexión a Internet para Information Protection](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection).

## <a name="onboarding-windows-10-or-windows-11-devices"></a>Incorporación de dispositivos Windows 10 o Windows 11 

Para poder supervisar y proteger los elementos confidenciales de un dispositivo, es necesario que habilite la supervisión del dispositivo y que incorpore los puntos de conexión. Ambas acciones se realizan en el portal de cumplimiento de Microsoft Purview.

Cuando quiera incorporar dispositivos que todavía no hayan sido incorporados, descargue el script apropiado y, luego, impleméntelo en esos dispositivos. Siga los procedimientos de incorporación de dispositivos que se indican a continuación.

Si ya tiene dispositivos incorporados en [ Microsoft Defender para punto de conexión (MDATP)](/windows/security/threat-protection/), estos aparecerán en la lista de dispositivos administrados.

En este escenario de implementación, incorporarás dispositivos Windows 10 o Windows 11 que aún no se han incorporado.

1. Abra el [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com). Elija **Configuración**  >  **Habilitar la supervisión de dispositivos**.

   > [!NOTE]
   > Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.

2. Abra la página de configuración del Centro de cumplimiento y elija **Activar la supervisión de dispositivos Windows**.

3. Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**. 

> [!NOTE]
> Si ya ha implementado Microsoft Defender para punto de conexión, todos los dispositivos que se incorporaron durante ese proceso aparecerán en la lista **Dispositivos**. No es necesario incorporarlos de nuevo.

4. Elija **Incorporación** para iniciar el proceso de incorporación.

5. Elija el modo en que desea implementar estos dispositivos adicionales de la lista **Método de implementación** y, después, **Descargar paquete**.

6. Elija el procedimiento adecuado que se debe seguir en la tabla siguiente:

|Tema | Descripción|
|:---|:---|
[Intune](device-onboarding-mdm.md) | Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.|
|[Configuration Manager](device-onboarding-sccm.md) | Puede usar Microsoft Endpoint Configuration Manager (rama actual) versión 1606 o Microsoft Endpoint Configuration Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en dispositivos.|
|[Directiva de grupo](device-onboarding-gp.md) | Utilice Directiva de grupo para implementar el paquete de configuración en los dispositivos.
[Script local](device-onboarding-script.md) | Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.
[Dispositivos de infraestructura de escritorio virtual (VDI)](device-onboarding-vdi.md) | Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.

## <a name="see-also"></a>Vea también

- [Información sobre riesgos internos de Microsoft](insider-risk-management.md)
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
