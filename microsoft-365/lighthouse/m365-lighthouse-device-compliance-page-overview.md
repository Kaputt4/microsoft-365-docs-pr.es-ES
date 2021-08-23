---
title: Microsoft 365 Lighthouse Introducción a la página de cumplimiento de dispositivos
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Cumplimiento de dispositivos.
ms.openlocfilehash: c87f808a3694c1f256a8a4787591a93444cf792f
ms.sourcegitcommit: 00a8a3376ea02770143af9a80cbe17a2b62636e3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2021
ms.locfileid: "58364942"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a>Microsoft 365 Lighthouse Introducción a la página de cumplimiento de dispositivos

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse permite ver información e información relacionada con el cumplimiento de dispositivos  de Intune para todos los inquilinos de clientes seleccionando Dispositivos en el panel de navegación izquierdo para abrir la página Cumplimiento de dispositivos. En esta página, puede obtener información general sobre el estado de cumplimiento entre inquilinos, ver una lista de dispositivos para cada inquilino y obtener informes de estado sobre las directivas y la configuración de cumplimiento.

## <a name="overview-tab"></a>Ficha Información general  
  
En la pestaña Información general, puedes ver el estado de cumplimiento del dispositivo en todos los inquilinos, ver las tendencias de cumplimiento de dispositivos mensuales y realizar un seguimiento de si los dispositivos tienen directivas de cumplimiento asignadas. También puedes ver información sobre las acciones y requisitos de cumplimiento del dispositivo de inquilino en función de las directivas de acceso condicional. 

Para obtener información detallada sobre el cumplimiento de dispositivos para un inquilino de cliente determinado, seleccione un valor en cualquiera de las columnas de estado de ese inquilino. Se abrirá la pestaña Dispositivos para que puedas ver los detalles de cumplimiento del dispositivo para el inquilino seleccionado.

Para exportar datos de cumplimiento de dispositivos a un Excel de valores separados por comas (.csv), seleccione **Exportar**.

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="Captura de pantalla de la pestaña Información general.":::

## <a name="devices-tab"></a>Pestaña Dispositivos

En la pestaña Dispositivos, la barra de recuento y anotación coloreada muestra el número total de dispositivos en todos los inquilinos del cliente que tienen los siguientes estados de cumplimiento: Compatible, No compatible, En período de gracia y No evaluado. Para obtener más información acerca de los distintos estados de cumplimiento, vea [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).

Para ver qué inquilinos tienen dispositivos con un estado de cumplimiento específico, seleccione ese estado en la barra de anotación de recuento para filtrar la lista. Para ver los estados de cumplimiento del dispositivo para uno o varios inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Selecciona cualquier nombre de dispositivo de la lista para ver más detalles sobre el estado de cumplimiento actual del dispositivo. Puedes sincronizar o reiniciar el dispositivo, o seleccionar Ver dispositivo en **Microsoft Endpoint Manager** si necesitas solucionar problemas o realizar más acciones.

> [!NOTE]
> Cuando reinicias un dispositivo, el propietario del dispositivo no se notifica automáticamente y puede perder el trabajo no guardado. Por este motivo, es posible que quieras notificar al propietario del dispositivo antes de reiniciar un dispositivo.

La pestaña Dispositivos también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar datos de cumplimiento de dispositivos a Excel de valores separados por comas (.csv).
- **Actualizar:** Selecciona para recuperar los datos de cumplimiento del dispositivo más actuales.
- **Sincronización:** Seleccione uno o varios dispositivos de la lista que tengan el estado No conforme, En período de gracia o No evaluados y, a continuación, seleccione esta opción para forzar a esos dispositivos a que se desenladen con Intune y reciban inmediatamente las directivas que se les hayan asignado.
- **Reiniciar:** Seleccione uno o varios dispositivos de la lista que tengan el estado No conforme, En período de gracia o No evaluados y, a continuación, seleccione esta opción para reiniciar esos dispositivos.
- **Buscar:** Escribe palabras clave para localizar rápidamente un dispositivo específico en la lista.
 
:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="Captura de pantalla de la pestaña Dispositivos.":::

## <a name="policies-tab"></a>Pestaña Directivas

En la pestaña Directivas, puedes ver directivas de cumplimiento de dispositivos en los inquilinos y comparar dos o tres directivas del mismo tipo de plataforma mediante la **opción** Comparar.

Para ver directivas para dispositivos en una plataforma específica, use el menú desplegable **del sistema** operativo para filtrar la lista. Para ver directivas para uno o varios inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Seleccione cualquier nombre de directiva de la lista para ver más detalles sobre esa directiva. Si necesita tomar medidas o ver información adicional, seleccione **Ver esta directiva en Microsoft Endpoint Manager**.

La pestaña Directivas también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar datos de directiva de cumplimiento de dispositivos a un Excel de valores separados por comas (.csv).
- **Actualizar:** Seleccione esta opción para recuperar los datos de directiva de cumplimiento de dispositivos más actuales.
- **Buscar:** Escribe palabras clave para localizar rápidamente una directiva de cumplimiento de dispositivos específica en la lista.

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="Captura de pantalla de la pestaña Directivas.":::

## <a name="settings-tab"></a>Configuración pestaña

La pestaña Configuración proporciona un informe agregado de la configuración no compatible en todos los dispositivos de inquilino. 

Para ver la configuración no compatible para dispositivos en una plataforma específica, use el **menú** desplegable Plataforma para filtrar la lista. Para ver la configuración no compatible para uno o varios inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Seleccione cualquier nombre de configuración no compatible en la lista para abrir un panel donde puede ver una lista de inquilinos que tienen dispositivos con esa configuración específica no compatible. Desde aquí, puede explorar más detalladamente si selecciona cualquier espacio empresarial de la lista para ver información sobre los dispositivos dentro de ese espacio empresarial que tienen la configuración específica no compatible. También puedes sincronizar o reiniciar el dispositivo, o seleccionar Ver dispositivo en **Microsoft Endpoint Manager** si necesitas solucionar problemas o realizar más acciones.

La Configuración también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar datos de configuración no compatibles a un Excel de valores separados por comas (.csv).
- **Actualizar:** Seleccione esta opción para recuperar los datos de configuración no compatibles más actuales.
- **Buscar:** Escriba palabras clave para buscar rápidamente una configuración específica no compatible en la lista.

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Captura de pantalla de la Configuración pestaña.":::

## <a name="related-content"></a>Contenido relacionado

[Windows de la página 365 (equipos en la nube)](m365-lighthouse-win365-page-overview.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
