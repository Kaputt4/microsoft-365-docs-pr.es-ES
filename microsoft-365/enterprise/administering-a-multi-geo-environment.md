---
title: Administración de un entorno de multigeográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: Los administradores pueden aprender a administrar servicios de SharePoint y OneDrive en un entorno multigeográfico.
ms.openlocfilehash: 155eea030cfa700a009805fb66aeb74eaae617d3
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64949087"
---
# <a name="administering-a-multi-geo-environment"></a>Administración de un entorno de Multi-Geo

A continuación, se muestra cómo funcionan los servicios de Microsoft 365 en un entorno multigeográfico.

## <a name="administrator-experience"></a>Experiencia de administrador

El centro de administración de SharePoint tiene una <a href="https://go.microsoft.com/fwlink/?linkid=2185076" target="_blank">pestaña **Ubicaciones geográficas**</a> en el panel de navegación izquierdo que incluye un mapa de ubicaciones geográficas donde puede ver y administrar las ubicaciones geográficas. Use esta página para agregar o eliminar ubicaciones geográficas para el inquilino.

## <a name="audit-log-search"></a>Búsqueda de registros de auditoría

En la página de búsqueda de registros de auditoría de Microsoft 365 podrá encontrar un [registro de auditoría](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) unificado de todas las ubicaciones satélite. Puede ver todas las entradas de registro de auditoría entre ubicaciones geográficas, por ejemplo, las actividades de los usuarios de NAM y EUR se mostrarán en una vista de la organización y, después, puede aplicar filtros existentes para ver las actividades de un usuario específico.

> [!NOTE]
> Exchange eventos de auditoría de administrador solo están disponibles para la ubicación predeterminada.

## <a name="bcs-secure-store-apps"></a>BCS, Secure Store, Apps

Los servicios BCS, Secure Store y Apps tienen todos instancias independientes en cada ubicación satélite, por lo que el Administrador de SharePoint Online debe administrarlos y configurarlos independientemente de la ubicación satélite.

## <a name="compliance-admin-center"></a>Centro de administración de cumplimiento

Hay un centro de cumplimiento central para un inquilino multigeográfico: [Centro de administración de Microsoft Purview](https://compliance.microsoft.com/).

## <a name="ediscovery"></a>eDiscovery

De forma predeterminada, un administrador de eDiscovery o de un espacio empresarial multigeográfico podrá usar eDiscovery solo en la ubicación central de ese espacio empresarial. El administrador global de Office 365 debe asignar permisos de supervisor de eDiscovery para que otros usuarios puedan ejecutar eDiscovery y asignar un parámetro "Región" en el filtro de seguridad de cumplimiento correspondiente para especificar la región donde se ejecutará eDiscovery como ubicación por satélite; en caso contrario, no se ejecutará eDiscovery en la ubicación por satélite. Para configurar el filtro de seguridad de cumplimiento de una región, vea [Configurar eDiscovery de Office 365 Multi-Geo](multi-geo-ediscovery-configuration.md).

## <a name="exchange-mailboxes"></a>Buzones de Exchange

Los buzones de Exchange de los usuarios se mueven automáticamente si cambia su PDL. Cuando se crea un nuevo buzón, se aprovisiona en la PDL del usuario o en ubicación central si no se ha establecido ningún valor para la PDL del usuario.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>directiva de prevención de pérdida de datos (DLP) de Information Protection (IP)

Puede establecer directivas de DLP e IP para OneDrive para la Empresa, SharePoint y Exchange en el Centro de seguridad y cumplimiento, incluyendo directivas necesarias para todo el espacio empresarial o para usuarios correspondientes. Por ejemplo: si quiere seleccionar una directiva para un usuario en una ubicación satélite, seleccione esta opción para aplicar la directiva a un determinado OneDrive y escriba la dirección URL de OneDrive del usuario. Vea [Información general sobre directivas de prevención de pérdida de datos](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) para obtener instrucciones generales para crear directivas de DLP.

Las directivas DLP se sincronizan automáticamente en función de su aplicabilidad a cada ubicación geográfica.

Implementar directivas de prevención de pérdida de datos Information Protection y Microsoft Purview para todos los usuarios de una ubicación geográfica no es una opción disponible en la interfaz de usuario, sino que debe seleccionar las cuentas aplicables para la directiva o aplicar la directiva globalmente a todas las cuentas.

## <a name="microsoft-power-apps"></a>Microsoft Power Apps

Power Apps creada para la ubicación satélite usará el punto final ubicado en la ubicación central del inquilino. Microsoft Power Apps no es un servicio multigeográfica. 

## <a name="power-automate"></a>Power Automate

Los flujos creados para la ubicación satélite usarán el punto final que se encuentra en la ubicación geográfica predeterminada del espacio empresarial.  Power Automate no es un servicio multigeográfica. 

## <a name="sharepoint-storage-quota"></a>Cuota de almacenamiento de SharePoint

De forma predeterminada, todas las ubicaciones geográficas de un entorno multigeográfico comparten la cuota de almacenamiento del espacio empresarial disponible.  También puede administrar la cuota de almacenamiento asignando una cuota específica para una ubicación geográfica determinada. Para obtener más información, vea las [Cuotas de almacenamiento de SharePoint en entornos multigeográficos](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Uso compartido

Los administradores pueden configurar y administrar directivas de uso compartido para cada una de sus ubicaciones. Los sitios de OneDrive y SharePoint de cada ubicación geográfica solo respetarán la configuración de uso compartido específica de la ubicación geográfica correspondiente. (Por ejemplo, puede permitir el [uso compartido externo](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) para su ubicación central, pero no para la ubicación satélite o viceversa). Tenga en cuenta que la configuración de uso compartido no permite configurar limitaciones de uso compartido entre ubicaciones geográficas.

## <a name="stream"></a>Stream

Los vídeos cargados en Stream en un chat 1:1 se almacenan en el OneDrive de la persona que carga. Las grabaciones de reuniones se almacenan en el OneDrive de cada asistente que registra la reunión.

## <a name="taxonomy"></a>Taxonomía

Se admite una [taxonomía](/sharepoint/managed-metadata) unificada para los metadatos administrados por la empresa en ubicaciones geográficas, con el patrón hospedado en la ubicación central de la empresa. Se recomienda administrar una taxonomía global desde la ubicación central y agregar solo términos específicos de la ubicación a la taxonomía de la ubicación satélite. Los términos de la taxonomía global se sincronizarán con las ubicaciones satélites.

Vea [Administrar metadatos en un espacio empresarial multigeográfico](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) para obtener detalles adicionales y orientación para desarrolladores.

## <a name="user-profile-application"></a>Aplicación de perfil de usuario

Hay una [aplicación de perfil de usuario](/sharepoint/manage-user-profiles) en cada ubicación geográfica. La información de perfil de cada usuario se hospeda en su ubicación geográfica y está disponible para el administrador de esa ubicación geográfica.

Si tiene propiedades de perfil personalizadas, se recomienda usar el mismo esquema de perfil en todas las zonas geográficas y rellenar las propiedades de perfil personalizadas en todas las ubicaciones geográficas o cuando sea necesario. Para obtener instrucciones sobre cómo rellenar los datos de perfil de usuario mediante programación, consulte la [API de actualización de Perfil de usuario masiva](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).

Vea [Trabajar con perfiles de usuario en un espacio empresarial multigeográfico](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) para obtener detalles adicionales y orientación para desarrolladores.

## <a name="yammer"></a>Yammer

Yammer no es una carga de trabajo multigeográfica. Yammer subprocesos almacenados en Yammer se colocarán en la ubicación central del inquilino. Yammer está implementando un cambio de almacenamiento de archivos que almacenará Yammer archivos en SharePoint. Yammer archivos almacenados en SharePoint se colocará el sitio SharePoint asociado al grupo de Yammer. SharePoint sitios de grupo se basan en la lógica PDL, como se describe en [SharePoint Sitios y grupos](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).
