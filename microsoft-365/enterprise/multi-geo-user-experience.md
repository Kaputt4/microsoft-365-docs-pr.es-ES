---
title: Experiencia del usuario en un entorno multigeográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
description: Información sobre la experiencia del usuario de SharePoint, OneDrive y Exchange en un entorno multigeográfico para Microsoft 365.
ms.openlocfilehash: fa4c108a8f7d97820d9f66bb00f23f19e138588b
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804978"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Experiencia del usuario en un entorno multigeográfico

Esto es lo que verán los usuarios en una configuración OneDrive para la Empresa multigeográfica:

## <a name="exchange-online-mailbox"></a>Buzón de correo Exchange Online

El buzón de Exchange Online de un usuario se aprovisiona en su ubicación de datos preferida y se reubica automáticamente si cambia su PDL. Los usuarios pueden usar Outlook y Outlook en la Web normalmente sin ningún cambio en la experiencia del usuario en un entorno multigeográfico.

## <a name="hub-sites"></a>Sitios concentradores

Los sitios de SharePoint Online Hub mejoran la detección y la interacción con el contenido de los empleados, al tiempo que crean una representación completa y coherente de proyectos, departamentos o regiones. En un entorno multigeográfico, los sitios de ubicaciones satélite se pueden asociar fácilmente a un sitio central independientemente de la ubicación _geográfica_ del sitio central. Los usuarios pueden buscar y obtener resultados en la central mediante una experiencia de búsqueda única, independientemente de la ubicación geográfica de los sitios.

## <a name="microsoft-365-app-launcher"></a>Iniciador de aplicaciones de Microsoft 365

El iniciador de aplicaciones es compatible con múltiples ubicaciones geográficas y dirigirá cada icono a la ubicación geográfica correspondiente de la carga de trabajo. Los iconos de SharePoint Online y OneDrive para la Empresa apuntarán al usuario a la ubicación correspondiente a la ubicación geográfica aprovisionada del usuario. Esto significa que si el usuario tiene una OneDrive para la Empresa en la ubicación central, su icono de SharePoint Online le apuntará a SP Home en la ubicación central, pero su sitio de grupo se aprovisionará en la ubicación correspondiente a su PDL. 

## <a name="office-applications"></a>Aplicaciones de Office

Las aplicaciones de Office como Microsoft Word, Excel y PowerPoint detectarán automáticamente la ubicación geográfica OneDrive para la Empresa correcta para cada usuario cuando inicie sesión. Los usuarios no necesitan escribir la dirección URL específica de la ubicación geográfica para sus sitios de OneDrive para la Empresa o SharePoint Online.

## <a name="onedrive-for-business-sync-app"></a>OneDrive para la Empresa aplicación de sincronización

La aplicación de sincronización OneDrive para la Empresa (versión 17.3.6943.0625 y posteriores) detectará automáticamente la ubicación _correcta de Geografía_ de OneDrive para el usuario. La compatibilidad con la aplicación de sincronización incluye la capacidad de sincronizar sitios basados en grupos independientemente de su ubicación _geográfica_ . El cliente de sincronización de Groove no es compatible con Multi-Geo. 

## <a name="onedrive-for-business-location"></a>Ubicación de la instancia de OneDrive para la Empresa

Los usuarios tendrán sus OneDrive para la Empresa aprovisionados en su ubicación de datos preferida. Si un usuario navega a una dirección URL de OneDrive para la Empresa que contiene una ubicación _geográfica_ incorrecta (como un marcador de una ubicación geográfica anterior), se le redirigirá automáticamente a la OneDrive para la Empresa en la ubicación geográfica adecuada.

## <a name="onedrive-for-business-ios-and-android"></a>OneDrive para la Empresa iOS y Android 

Las aplicaciones móviles de OneDrive para iOS y Android le mostrarán los archivos y archivos OneDrive para la Empresa compartidos con usted, independientemente de su ubicación _geográfica_. La búsqueda desde las OneDrive para la Empresa aplicaciones móviles mostrará los resultados pertinentes de todas las ubicaciones _de Geography_. Descargue la versión más reciente de estas aplicaciones.

Para obtener más información, vea Usar [OneDrive en iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) y [Usar OneDrive para Android para](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) obtener más información.

## <a name="onedrive-for-business-mobile-client"></a>cliente móvil de OneDrive para la Empresa 

El cliente móvil de OneDrive para la Empresa es compatible con varias zonas geográficas y mostrará el contenido y los resultados pertinentes de todas las ubicaciones _geográficas_.

## <a name="search"></a>Búsqueda

Cada ubicación _geography_ tiene su propio índice de búsqueda y centro de búsqueda. Cuando un usuario busca, la consulta se envía a todas las ubicaciones _geography_ y los resultados devueltos se combinan y, a continuación, se clasifican para que el usuario obtenga resultados unificados. Los usuarios obtienen resultados de todas las ubicaciones _geography_ independientemente de su propia ubicación _geográfica_ . Consulte [Configurar la búsqueda de OneDrive para la Empresa multigeográfica](configure-search-for-multi-geo.md) para obtener información específica.

Se admiten los siguientes clientes de búsqueda:

-   OneDrive para la Empresa

-   Office Delve

-   Inicio de SharePoint Online

-   Centro de búsqueda

-   Aplicaciones de búsqueda personalizada que usan la API de SharePoint Search

## <a name="sharepoint-online-home"></a>Inicio de SharePoint Online 

En SharePoint Online Multi-Geo, la casa de SharePoint Online se hospeda en la ubicación donde reside el usuario según lo determinado por su ubicación de OneDrive para la Empresa. Por ejemplo: si el usuario tiene sus OneDrive para la Empresa hospedados en una ubicación satélite europea, su inicio de SharePoint Online se representará desde Europa. La página principal de SharePoint Online incluye todo el contenido relevante para el usuario, independientemente de su ubicación _geográfica_ . 

**Sitios seguidos, noticias de sitios, sitios recientes, sitios frecuentes y sitios sugeridos**

Todos estos componentes se mostrarán para el usuario independientemente de la ubicación _geography_ donde se hospeda el contenido, siempre y cuando el usuario tenga permisos para dicho contenido. 

**Vínculos destacados**

Los administradores pueden configurar vínculos destacados en la página principal de SharePoint Online según corresponda a cada ubicación _geográfica_ . Esto permite que el administrador destaque en la página principal de SharePoint de cada región los vínculos que sean apropiados para los usuarios de la región. 

## <a name="sharepoint-mobile-client"></a>Cliente móvil de SharePoint

El cliente móvil de SharePoint es compatible con las capacidades multigeográficas y mostrará el contenido y los resultados relevantes de todas las ubicaciones geográfica.

## <a name="sharing"></a>Uso compartido

La experiencia del selector de Personas muestra a todos los usuarios independientemente de su ubicación _geográfica_. Esto permite a un usuario compartir con otro usuario en su misma ubicación geográfica o en cualquier otra de las ubicaciones _geográficas del inquilino_. El contenido de diferentes ubicaciones _geográficas_ se mostrará en la vista **Compartido conmigo** en la OneDrive para la Empresa del usuario, Word, Excel, PowerPoint y Office.com y se puede acceder a él con una experiencia de Sign-On, independientemente de _la ubicación geográfica_ en la que se hospede.

## <a name="microsoft-teams-experience"></a>Experiencia de Microsoft Teams

Microsoft Teams es un servicio multigeográfica. OneDrive para la Empresa archivos y los archivos vistos recientemente se muestran independientemente de la ubicación _geográfica_ del usuario. @ menciona el trabajo con usuarios de todas las ubicaciones _geography_ .

## <a name="user-profiles"></a>Perfiles de usuario

La información del perfil de usuario se domina en la ubicación _geography_ del usuario. Al seleccionar un usuario, se le dirigirá a la ubicación _geográfica_ adecuada para el usuario, donde verá sus detalles completos del perfil.

Si Office Delve está desactivado, verá la experiencia de perfil clásica en SharePoint Online, que no es compatible con multigeográfica.


