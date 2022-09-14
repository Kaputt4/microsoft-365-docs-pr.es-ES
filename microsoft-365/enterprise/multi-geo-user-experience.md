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
ms.openlocfilehash: a543653410d2b9330c0ea2c5e3e717918506ae2b
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687205"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Experiencia del usuario en un entorno multigeográfico

Esto es lo que verán los usuarios en una configuración de OneDrive multigeográfico:

## <a name="exchange-mailbox"></a>Buzón de Exchange

El buzón de Exchange de un usuario se aprovisiona en su ubicación de datos preferida y si esta cambia el buzón se reubica automáticamente. Los usuarios pueden usar Outlook y Outlook en la Web normalmente sin cambios en la experiencia del usuario en un entorno de multigeográfico.

## <a name="hub-sites"></a>Sitios centrales

Los sitios de SharePoint Hub mejoran la detección y la interacción con el contenido de los empleados, al tiempo que crean una representación completa y coherente de proyectos, departamentos o regiones. En un entorno multigeográfico, los sitios de ubicaciones satélite pueden asociarse fácilmente con un sitio central independientemente de su ubicación geográfica. Los usuarios pueden buscar y obtener resultados en la central mediante una experiencia de búsqueda única, independientemente de la ubicación geográfica de los sitios.

## <a name="microsoft-365-app-launcher"></a>Iniciador de aplicaciones de Microsoft 365

El iniciador de aplicaciones es compatible con múltiples ubicaciones geográficas y dirigirá cada icono a la ubicación geográfica correspondiente de la carga de trabajo. Los iconos de SharePoint y OneDrive apuntarán al usuario a la ubicación correspondiente a la ubicación geográfica aprovisionada del usuario. Esto significa que si el usuario tiene un OneDrive en la ubicación central, el icono de SharePoint apuntarán a la página principal de SharePoint en la ubicación central, pero se aprovisionará su sitio de grupo en la ubicación correspondiente a su ubicación de datos preferida. 

## <a name="office-applications"></a>Aplicaciones de Office

Las aplicaciones de Office como Word, Excel y PowerPoint detectarán automáticamente la ubicación geográfica correcta de OneDrive para cada usuario cuando inicie sesión. Los usuarios no tienen que escribir la dirección URL específica de geoárea de su instancia de OneDrive.

## <a name="onedrive-sync-app"></a>Sincronización de OneDrive aplicación

La aplicación Sincronización de OneDrive (versión 17.3.6943.0625 y posteriores) detectará automáticamente la ubicación geográfica correcta de OneDrive para el usuario. La compatibilidad con la aplicación de sincronización incluye la capacidad de sincronizar sitios basados en grupos independientemente de su ubicación geográfica. El cliente de sincronización de Groove no se admite para la multigeográfica. 

## <a name="onedrive-location"></a>Ubicación de OneDrive

Los usuarios tendrán su OneDrive aprovisionado en su ubicación de datos preferida. Si un usuario navega a una dirección URL de OneDrive que contiene una ubicación geográfica incorrecta (como un marcador de una ubicación geográfica anterior), se le redirigirá automáticamente a OneDrive en la ubicación geográfica adecuada.

## <a name="onedrive-ios-and-android"></a>OneDrive para iOS y Android 

Las aplicaciones móviles de OneDrive para iOS y Android le mostrarán los archivos y archivos de OneDrive compartidos con usted, independientemente de su ubicación geográfica. La búsqueda desde las aplicaciones móviles de OneDrive mostrará los resultados pertinentes de todas las ubicaciones geográficas. Descargue la versión más reciente de estas aplicaciones.

Para obtener más información, vea Usar [OneDrive en iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) y [Usar OneDrive para Android para](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) obtener más información.

## <a name="onedrive-mobile-client"></a>Cliente móvil de OneDrive 

El cliente móvil de OneDrive es compatible con las capacidades multigeográficas y mostrará el contenido y los resultados relevantes de todas las ubicaciones geográfica.

## <a name="search"></a>Búsqueda

Cada ubicación geográfica tiene su propio índice de búsqueda y centro de búsqueda. Cuando un usuario busca, la consulta se envía a todas las ubicaciones geográficas y los resultados devueltos se combinan y, a continuación, se clasifican para que el usuario obtenga resultados unificados. Los usuarios obtienen resultados de todas las ubicaciones geográficas independientemente de su propia ubicación geográfica. Consulte [Configurar la búsqueda de OneDrive Multi-Geo](configure-search-for-multi-geo.md) para obtener información específica.

Se admiten los siguientes clientes de búsqueda:

-   OneDrive

-   Delve

-   Página principal de SharePoint

-   Centro de búsqueda

-   Aplicaciones de búsqueda personalizada que usan la API de SharePoint Search

## <a name="sharepoint-home"></a>Página principal de SharePoint 

En SharePoint Multi-Geo, la casa de SharePoint se hospeda en la ubicación donde reside el usuario según lo determinado por su ubicación de OneDrive. Por ejemplo: si el usuario tiene su OneDrive hospedado en una ubicación satélite europea, su inicio de SharePoint se representará desde Europa. La página principal de SharePoint incluye todo el contenido relevante para el usuario independientemente de su ubicación geográfica. 

**Sitios seguidos, noticias de sitios, sitios recientes, sitios frecuentes y sitios sugeridos**

Todos estos componentes se mostrarán con independencia de la ubicación geográfica donde se hospeda el contenido, siempre y cuando el usuario tenga permisos para dicho contenido. 

**Vínculos destacados**

Los administradores pueden configurar vínculos destacados en la página principal de SharePoint según sea adecuado para cada ubicación geográfica. Esto permite que el administrador destaque en la página principal de SharePoint de cada región los vínculos que sean apropiados para los usuarios de la región. 

## <a name="sharepoint-mobile-client"></a>Cliente móvil de SharePoint

El cliente móvil de SharePoint es compatible con las capacidades multigeográficas y mostrará el contenido y los resultados relevantes de todas las ubicaciones geográfica.

## <a name="sharing"></a>Uso compartido

La experiencia de selector de personas muestra todos los usuarios, independientemente de su ubicación geográfica. Esto permite que un usuario pueda compartir con otro de su misma ubicación geográfica o en cualquier otra ubicación geográfica de su inquilino. El contenido de distintas ubicaciones geográficas se mostrará en la vista **Compartido conmigo** en OneDrive, Word, Excel, PowerPoint y Office.com del usuario y se puede acceder a él con una sola experiencia Sign-On independientemente de la ubicación geográfica en la que se hospede.

## <a name="teams-experience"></a>Experiencia de Teams

Teams es un servicio multigeográfica. Los archivos de OneDrive y los archivos vistos recientemente se muestran independientemente de la ubicación geográfica del usuario. Las @menciones funcionan con los usuarios de todas las ubicaciones geográficas.

## <a name="user-profiles"></a>Perfiles de usuario

La información de perfiles de usuario se controla en la ubicación geográfica del usuario. Al seleccionar un usuario, se le dirigirá a la ubicación geográfica correcta del usuario, donde verá los detalles completos de su perfil.

Si Delve está desactivada, verá la experiencia de perfil clásica de SharePoint, que no es de reconocimiento multigeográfico.


