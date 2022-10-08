---
title: Información general de la página Cumplimiento de dispositivos en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Cumplimiento de dispositivos.
ms.openlocfilehash: a326b837a1526eae8ff4a7fa80fc4b463f861849
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195465"
---
# <a name="overview-of-the-device-compliance-page-in-microsoft-365-lighthouse"></a>Información general de la página Cumplimiento de dispositivos en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse permite ver información e información relacionada con el cumplimiento de Intune dispositivo para todos los inquilinos del cliente seleccionando **Dispositivos Compatibilidad** >  de dispositivos en el panel de navegación izquierdo para abrir la página Cumplimiento de dispositivos. En esta página, puede obtener información general sobre el estado de cumplimiento entre inquilinos, ver una lista de dispositivos para cada inquilino y obtener informes de estado sobre las directivas de cumplimiento y la configuración.

## <a name="overview-tab"></a>‎Pestaña da Información general  
  
En la pestaña Información general, puede ver el estado de cumplimiento de los dispositivos entre los inquilinos, ver las tendencias de cumplimiento de dispositivos mensuales y realizar un seguimiento de si los dispositivos tienen asignadas directivas de cumplimiento. También puede ver cuántos inquilinos no tienen ningún requisito de cumplimiento de dispositivos aplicado mediante directivas de acceso condicional. Puede seleccionar **Ver más** para ver más detalles.

Para obtener información detallada sobre el cumplimiento de dispositivos para un inquilino de cliente determinado, seleccione un valor en cualquiera de las columnas de estado de ese inquilino. Se abrirá la pestaña Dispositivos para que pueda ver los detalles de cumplimiento del dispositivo para el inquilino seleccionado.

Para exportar datos de cumplimiento de dispositivos a un archivo de valores separados por comas (.csv) de Excel, seleccione **Exportar**.

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="Captura de pantalla de la pestaña Información general." lightbox="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png":::

## <a name="devices-tab"></a>Pestaña Dispositivos

En la pestaña Dispositivos, la barra de anotaciones de recuento de colores muestra el número total de dispositivos en todos los inquilinos del cliente que tienen los siguientes estados de cumplimiento: Compliant, Not compliant, In grace period y Not evaluated. Para obtener más información sobre los distintos estados de cumplimiento, consulte [Supervisión de directivas de cumplimiento de dispositivos Intune](/mem/intune/protect/compliance-policy-monitor).

Para ver qué inquilinos tienen dispositivos con un estado de cumplimiento específico, seleccione ese estado en la barra count-annotation para filtrar la lista. Para ver los estados de cumplimiento de dispositivos para uno o más inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Seleccione cualquier nombre de dispositivo en la lista para ver más detalles sobre el estado de cumplimiento actual del dispositivo. Puede sincronizar o reiniciar el dispositivo, o bien seleccionar **Ver dispositivo en Microsoft Endpoint Manager** si necesita solucionar problemas o realizar otras acciones.

> [!NOTE]
> Al reiniciar un dispositivo, el propietario del dispositivo no recibe una notificación automática y puede perder el trabajo no guardado. Por este motivo, es posible que quiera notificar al propietario del dispositivo antes de reiniciar un dispositivo.

La pestaña Dispositivos también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos de cumplimiento de dispositivos a un archivo de valores separados por comas (.csv) de Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos de cumplimiento de dispositivos más actuales.
- **Sincronizar:** Seleccione uno o varios dispositivos de la lista que tengan el estado No compatible, En período de gracia o No evaluado y, a continuación, seleccione esta opción para forzar a esos dispositivos a protegerse con Intune y recibir inmediatamente las directivas que se les hayan asignado.
- **Reiniciar:** Seleccione uno o varios dispositivos de la lista que tengan el estado No compatible, En período de gracia o No evaluado y, a continuación, seleccione esta opción para reiniciar esos dispositivos.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente un dispositivo específico en la lista.
 
:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="Captura de pantalla de la pestaña Dispositivos." lightbox="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png":::

## <a name="policies-tab"></a>Pestaña Directivas

En la pestaña Directivas, puede ver las directivas de cumplimiento de dispositivos entre los inquilinos y comparar dos o tres directivas del mismo tipo de plataforma mediante la opción **Comparar** .

Para ver las directivas de los dispositivos en una plataforma específica, use el menú desplegable del **sistema** operativo para filtrar la lista. Para ver las directivas de uno o más inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Seleccione cualquier nombre de directiva de la lista para ver más detalles sobre esa directiva. Si necesita realizar acciones o ver información adicional, seleccione **Ver esta directiva en Microsoft Endpoint Manager**.

La pestaña Directivas también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos de la directiva de cumplimiento de dispositivos a un archivo de valores separados por comas (.csv) de Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos más actuales de la directiva de cumplimiento de dispositivos.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente una directiva de cumplimiento de dispositivos específica en la lista.

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="Captura de pantalla de la pestaña Directivas." lightbox="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png":::

## <a name="settings-tab"></a>Pestaña Configuración

La pestaña Configuración proporciona un informe agregado de la configuración no compatible entre dispositivos de inquilino. 

Para ver la configuración no compatible para dispositivos en una plataforma específica, use el menú desplegable **Plataforma** para filtrar la lista. Para ver la configuración no compatible para uno o más inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Seleccione cualquier nombre de configuración no compatible en la lista para abrir un panel donde pueda ver una lista de inquilinos que tienen dispositivos con esa configuración no compatible específica. Desde aquí, puede explorar en profundidad aún más si selecciona cualquier inquilino de la lista para ver información sobre los dispositivos dentro de ese inquilino que tienen la configuración específica no compatible. También puede sincronizar o reiniciar el dispositivo, o bien seleccionar **Ver dispositivo en Microsoft Endpoint Manager** si necesita solucionar problemas o realizar otras acciones.

La pestaña Configuración también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar datos de configuración no compatibles a un archivo de valores separados por comas (.csv) de Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos de configuración no compatibles más actuales.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente una configuración específica no compatible en la lista.

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Captura de pantalla de la pestaña Configuración." lightbox="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png":::

## <a name="related-content"></a>Contenido relacionado

[Información general de la página Windows 365 (PC en la nube) de Microsoft 365 Lighthouse](m365-lighthouse-win365-page-overview.md) (artículo)\
[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)
