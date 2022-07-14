---
title: Información general de la página Windows 365 (PC en la nube) en Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: katmartin
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Windows 365 (PC en la nube).
ms.openlocfilehash: dded3bc455a66a77ae325f1d6a54660a88846c1e
ms.sourcegitcommit: 221212fff9737e0ea386755deb8fed62ae9c254b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66787240"
---
# <a name="overview-of-the-windows-365-cloud-pcs-page-in-microsoft-365-lighthouse"></a>Información general de la página Windows 365 (PC en la nube) en Microsoft 365 Lighthouse  
  
Windows 365 es un servicio basado en la nube que permite a los administradores de Microsoft Endpoint Manager (MEM) aprovisionar y administrar equipos en la nube para sus usuarios que tienen una licencia de Windows 365. Windows 365 está totalmente integrado con MEM para la administración de dispositivos y con Microsoft 365 Lighthouse para la administración de asociados de equipos en la nube en todos sus inquilinos de clientes.

Para obtener más información sobre Windows 365, consulte [¿Qué es Windows 365?](/windows-365/overview) Para obtener una lista de los requisitos de Windows 365, consulte [Requisitos para Windows 365](/windows-365/enterprise/requirements).

> [!IMPORTANT]
> Debe ir a [MEM](https://go.microsoft.com/fwlink/p/?linkid=2150463) para aprovisionar equipos en la nube para cada inquilino de cliente antes de poder administrarlos en Lighthouse. No se puede aprovisionar desde Lighthouse.

Una vez que haya aprovisionado equipos en la nube para el inquilino del cliente, la tarjeta de Windows 365 de la página principal de Microsoft 365 proporciona una breve alerta sobre los equipos en la nube que necesitan acción, como el número de equipos en la nube que no se pudieron aprovisionar y los errores de conexión de red de Azure. Para obtener un estado detallado, seleccione el botón de la tarjeta de Windows 365 (o seleccione **Windows 365** en el panel de navegación izquierdo) para abrir la página de Windows 365. En esta página, puede obtener información general sobre el estado de los equipos en la nube asignados a los inquilinos del cliente, ver una lista de todos los equipos en la nube que administra y los inquilinos a los que están asignados y ver las conexiones de red de Azure entre los inquilinos del cliente y Azure Active Directory (Azure AD) y su estado.

## <a name="overview-tab"></a>‎Pestaña da Información general

En la pestaña Información general, la barra de anotaciones de recuento de colores muestra el número total de equipos en la nube o conexiones de red de Azure en todos los inquilinos de cliente que tienen los siguientes estados: Conexiones de red con errores, No aprovisionadas, Error de aprovisionamiento y Desaprovisionamiento pronto.

Puede ver un desglose de los estados del equipo en la nube para cada inquilino de cliente en la lista debajo de la barra de anotación. Para ver qué inquilinos tienen equipos en la nube con un estado específico, seleccione ese estado en la barra count-annotation para filtrar la lista. Para ver los estados del equipo en la nube para uno o más inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Para obtener información detallada sobre el estado de un inquilino de cliente determinado, seleccione un valor en cualquiera de las columnas de estado de ese inquilino. En función de la columna en la que se encuentra el valor, se abrirá la pestaña **Conexiones de red de Azure** o **Todos los equipos** en la nube y se mostrará más información.

La pestaña Información general también incluye las siguientes opciones:

- **Actualizar:** Seleccione esta opción para recuperar los datos de PC en la nube más actuales.
- **Exportar:** Seleccione esta opción para exportar los datos de Cloud PC a un archivo de valores separados por comas (.csv) de Excel.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente un equipo en la nube específico en la lista.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png" alt-text="Captura de pantalla de la pestaña Información general de Windows 365." lightbox="../media/m365-lighthouse-win365-page-overview/win365-overview-tab.png":::

## <a name="all-cloud-pcs-tab"></a>Pestaña Todos los equipos en la nube

En la pestaña Todos los equipos en la nube, la barra de anotaciones de recuento de colores muestra el número total de equipos en la nube en todos los inquilinos de cliente que tienen los siguientes estados: Aprovisionado, No aprovisionado, Error de aprovisionamiento y Desaprovisionamiento pronto.

Puede ver todos los equipos en la nube y su estado de aprovisionamiento en la lista debajo de la barra de anotación. Se proporciona la siguiente información:

- **Nombre del equipo en la nube:** Nombre asignado al equipo en la nube.
- **Usuario:** Usuario para el que se ha aprovisionado o intentado aprovisionar un equipo en la nube.
- **Nombre del dispositivo:** Intune nombre del dispositivo, un identificador único para un equipo en la nube.
- **Inquilino:** Inquilino del cliente en el que se aprovisionó un equipo en la nube.
- **Estado:** Estado de aprovisionamiento del equipo en la nube.
- **Tipo de licencia:** Empresa o Empresa.
- **Especificaciones:** Configuración de hardware de PC en la nube.

Para ver qué inquilinos tienen equipos en la nube con un estado de aprovisionamiento específico, seleccione ese estado en la barra count-annotation para filtrar la lista. Para ver los estados de aprovisionamiento de equipos en la nube para uno o más inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Seleccione cualquier equipo en la nube en la lista para ver más detalles y ejecutar acciones de administración como:
- **Reiniciar:** Seleccione esta opción para reiniciar el dispositivo. 
- **Reprovision:** Seleccione esta opción para restablecer el dispositivo. También puede ver la directiva de aprovisionamiento en el vínculo microsoft Endpoint Manager.
- **Renombrar:** Seleccione esta opción para cambiar el nombre del dispositivo asignado a un usuario.
- **Cambiar tipo de cuenta:** Seleccione el tipo de cuenta para el usuario: Usuario estándar (recomendado) o Administrador local.

La pestaña Todos los equipos en la nube también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos de Cloud PC a un archivo de valores separados por comas (.csv) de Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos de PC en la nube más actuales.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente un equipo en la nube específico en la lista.

Para ver una lista completa de los estados de aprovisionamiento de EQUIPOS en la nube y lo que significan, consulte [Información general sobre la administración de dispositivos para equipos](/windows-365/enterprise/device-management-overview#column-details) en la nube en la biblioteca de documentación de Windows 365.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png" alt-text="Captura de pantalla de la pestaña todos los equipos en la nube de Windows 365." lightbox="../media/m365-lighthouse-win365-page-overview/all-cloud-pcs-tab.png":::

## <a name="azure-network-connections-tab"></a>Pestaña Conexiones de red de Azure

En la pestaña Conexiones de red de Azure, la barra de anotaciones de recuento de colores muestra el número total de conexiones de red de Azure en todos los inquilinos de cliente que tienen Windows 365 Enterprise equipos en la nube y pueden tener los siguientes estados: Conexiones correctas y Conexiones con errores.

En la lista debajo de la barra de anotación de recuento, puede ver todas las conexiones de red de Azure y su estado de conexión.

Para ver las conexiones con un estado de aprovisionamiento específico, seleccione ese estado en la barra count-annotation para filtrar la lista. Para ver los estados de conexión de uno o más inquilinos de clientes específicos, use el menú desplegable **Inquilinos** para filtrar la lista.

Si necesita realizar acciones o solucionar problemas de una conexión en la lista, seleccione **Ver detalles de conexión en Microsoft Endpoint Manager**.

La pestaña Conexiones de red de Azure también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos de conexión a un archivo de valores separados por comas (.csv) de Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos de conexión más actuales.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente una conexión específica.

:::image type="content" source="../media/m365-lighthouse-win365-page-overview/azure-network-connections-tab.png" alt-text="Captura de pantalla de la pestaña Conexiones de red de Azure." lightbox="../media/m365-lighthouse-win365-page-overview/azure-network-connections-tab.png":::

## <a name="related-content"></a>Contenido relacionado

[¿Qué es Windows 365?](/windows-365/overview) (artículo)\
[Windows 365 información general sobre la administración de dispositivos para equipos en la nube](/windows-365/enterprise/device-management-overview) (artículo)\
[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)