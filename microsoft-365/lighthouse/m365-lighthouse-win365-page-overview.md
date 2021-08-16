---
title: Microsoft 365 Lighthouse Windows de la página 365 (equipos en la nube)
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Windows 365 (equipos en la nube).
ms.openlocfilehash: 1ad05cf2cae824c0bab61635f05cbce13f6fcbd57dfcb904c0e53fd3b25e9ab0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53907193"
---
# <a name="windows-365-cloud-pcs-page-overview"></a>Windows de la página 365 (equipos en la nube)  

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).
  
Windows 365 es un servicio basado en la nube que permite a los administradores de Microsoft Endpoint Manager (MEM) aprovisionar y administrar equipos en la nube para sus usuarios que tienen una licencia Windows 365. Windows 365 está totalmente integrado con MEM para la administración de dispositivos y con Microsoft 365 Lighthouse para la administración de partners de equipos en la nube en todos sus inquilinos de clientes.

Para obtener más información Windows 365, vea [¿Qué Windows 365?](/windows-365/overview) Para obtener una lista de Windows 365 requisitos, vea [Requirements for Windows 365](/windows-365/requirements).

> [!IMPORTANT]
> Debe ir a [MEM para](https://go.microsoft.com/fwlink/p/?linkid=2150463) aprovisionar equipos en la nube para cada inquilino del cliente antes de poder administrarlos en Microsoft 365 Lighthouse. No puede aprovisionar desde Microsoft 365Lighthouse.

Una vez que haya aprovisionado equipos en la nube para el inquilino del cliente, la tarjeta Windows 365 de la página principal de Microsoft 365 proporciona una breve alerta sobre los equipos en la nube que necesitan acción, como el número de equipos en la nube que no pudieron aprovisionar y los errores de conexión de red local. Para obtener un estado detallado, seleccione el botón de la tarjeta Windows 365 (o **seleccione Windows 365** en el panel de navegación izquierdo) para abrir la página Windows 365. En esta página, puede obtener una introducción al estado de los equipos en la nube asignados a los inquilinos de cliente, ver una lista de todos los equipos en la nube que administra y los inquilinos a los que están asignados y ver las conexiones de red locales entre los inquilinos de cliente y Azure Active Directory (Azure AD) y su estado.

## <a name="overview-tab"></a>Ficha Información general

En la pestaña Información general, la barra de recuento y anotación coloreada muestra el número total de equipos en la nube o conexiones de red locales en todos los inquilinos de clientes que tienen los siguientes estados: Conexiones de red con errores, No aprovisionadas, Error de aprovisionamiento y Desaprovisionamiento pronto.

Puede ver un desglose de los estados del equipo en la nube para cada inquilino de cliente en la lista debajo de la barra de anotaciones. Para ver qué inquilinos tienen equipos en la nube con un estado específico, seleccione ese estado en la barra de anotación de recuento para filtrar la lista. Para ver los estados del equipo en la nube para uno o varios inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Para obtener información de estado detallada para un inquilino de cliente determinado, seleccione un valor debajo de cualquiera de las columnas de estado para ese inquilino. Según la columna en la  que se encuentra  el valor, se abrirá la pestaña Conexiones de red locales o Todos los equipos en la nube y se mostrará más información.

La pestaña Información general también incluye las siguientes opciones:

- **Actualizar:** Seleccione esta opción para recuperar los datos de PC en la nube más actuales.
- **Exportar:** Seleccione esta opción para exportar datos del equipo en la nube a Excel de valores separados por comas (.csv).
- **Buscar:** Escriba palabras clave para localizar rápidamente un equipo en la nube específico en la lista.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png" alt-text="Captura de pantalla de Windows pestaña Información general de 365.":::

## <a name="all-cloud-pcs-tab"></a>Pestaña Todos los equipos en la nube

En la pestaña Todos los equipos en la nube, la barra de recuento y anotación coloreada muestra el número total de equipos en la nube en todos los inquilinos de clientes que tienen los siguientes estados: Aprovisionado, No aprovisionado, Error de aprovisionamiento y Desaprovisionamiento pronto.

Puede ver todos los equipos en la nube y su estado de aprovisionamiento en la lista debajo de la barra de anotaciones. Se proporciona la siguiente información:

- **Nombre del equipo en la nube:** Nombre asignado al equipo en la nube.
- **Inquilino:** Inquilino del cliente en el que se aprovisionó un equipo en la nube.
- **Nombre del dispositivo:** Nombre de dispositivo de Intune: un identificador único para un equipo en la nube.
- **Tipo de equipo:** Tipo de EQUIPO en la nube según skus estándar.
- **Estado:** Estado de aprovisionamiento del equipo en la nube.
- **Usuario:** Usuario para el que se ha aprovisionado o intentado aprovisionar un equipo en la nube.

Para ver qué inquilinos tienen equipos en la nube con un estado de aprovisionamiento específico, seleccione ese estado en la barra de anotación de recuento para filtrar la lista. Para ver los estados de aprovisionamiento del equipo en la nube para uno o varios inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Seleccione cualquier equipo en la nube de la lista para ver más detalles. Si necesitas tomar medidas en el equipo en la nube, hay opciones para ver las directivas de aprovisionamiento de inquilinos y los detalles del dispositivo en Microsoft Endpoint Manager.

La pestaña Todos los equipos en la nube también incluye las siguientes opciones:

- **Actualizar:** Seleccione esta opción para recuperar los datos de PC en la nube más actuales.
- **Exportar:** Seleccione esta opción para exportar datos del equipo en la nube a Excel de valores separados por comas (.csv).
- **Buscar:** Escriba palabras clave para localizar rápidamente un equipo en la nube específico en la lista.
- **Reintentar el aprovisionamiento:** Seleccione de 1 a 20 equipos en la nube de la lista que tienen un estado de Error de aprovisionamiento y, a continuación, seleccione esta opción para reintentar el aprovisionamiento de esos equipos en la nube.

Para ver una lista completa de los estados del equipo en la nube y lo que significan, consulte [Cloud PC overview page](/windows-365/device-management-overview#cloud-pc-overview-page) in the Windows 365 documentation library.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png" alt-text="Captura de pantalla de la Windows 365 Todos los equipos en la nube.":::

## <a name="on-premises-network-connections-tab"></a>Ficha Conexiones de red local

En la pestaña Conexiones de red locales, la barra de anotaciones de recuento coloreada muestra el número total de conexiones de red locales en todos los inquilinos de cliente que tienen los siguientes estados: Conexiones correctas y Conexiones con errores.

En la lista debajo de la barra de recuento y anotación, puede ver todas las conexiones de red locales y su estado de conexión.

Para ver las conexiones con un estado de aprovisionamiento específico, seleccione ese estado en la barra de recuento y anotación para filtrar la lista. Para ver los estados de conexión de uno o varios inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Si necesita tomar medidas o solucionar problemas de una conexión en la lista, seleccione Ver detalles de conexión **en Microsoft Endpoint Manager**.

La pestaña Conexiones de red local también incluye las siguientes opciones:

- **Actualizar:** Seleccione esta opción para recuperar los datos de conexión más actuales.
- **Exportar:** Seleccione para exportar datos de conexión a un Excel de valores separados por comas (.csv).
- **Buscar:** Escriba palabras clave para localizar rápidamente una conexión específica.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/on-prem-network-connections-tab.png" alt-text="Captura de pantalla de la Windows 365 conexiones de red locales.":::

## <a name="related-content"></a>Contenido relacionado

[¿Qué Windows 365?](/windows-365/overview) (artículo)\
[Windows de administración de dispositivos 365 para equipos en](/windows-365/device-management-overview) la nube (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)