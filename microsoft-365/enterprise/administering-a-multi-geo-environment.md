---
title: Comportamiento del servicio en un entorno habilitado para varias zonas geográficas
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
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
ms.openlocfilehash: ae6673488e552e1da9acd14526194734d194c305
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68803625"
---
# <a name="service-behavior-a-multi-geo-enabled-environment"></a>Comportamiento del servicio en un entorno habilitado para varias zonas geográficas

Aquí se muestra cómo funcionan los servicios de Microsoft 365 en un entorno multigeográfico.

## <a name="administrator-experience"></a>Experiencia de administrador

El Centro de administración de SharePoint tiene una [pestaña **Ubicaciones geográficas**](https://go.microsoft.com/fwlink/?linkid=2185076) en el panel de navegación izquierdo que incluye un mapa de ubicaciones geográficas donde puede ver y administrar las ubicaciones geográficas. Use esta página para agregar o eliminar ubicaciones geográficas para el _inquilino_.

## <a name="audit-log-search"></a>Búsqueda en el registro de auditoría

Un [registro de auditoría](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) unificado para todas las ubicaciones _de Geografía satélite_ está disponible en la página de búsqueda de registros de auditoría de Microsoft 365. Puede ver todas las entradas de registro de auditoría entre ubicaciones geográficas, por ejemplo, las actividades de los usuarios de NAM y EUR se mostrarán en una vista de la organización y, después, puede aplicar filtros existentes para ver las actividades de un usuario específico.

> [!NOTE]
> Los eventos de auditoría del administrador de Exchange solo están disponibles para la ubicación predeterminada.

## <a name="bcs-secure-store-apps"></a>BCS, Secure Store, Apps

Los servicios BCS, Secure Store y Apps tienen todos instancias independientes en cada ubicación satélite, por lo que el Administrador de SharePoint Online debe administrarlos y configurarlos independientemente de la ubicación satélite.

## <a name="compliance-admin-center"></a>Centro de administración de cumplimiento

Hay un portal de cumplimiento Microsoft Purview central para un _inquilino multigeográfico_: [Centro de administración de Microsoft Purview](https://compliance.microsoft.com/).

## <a name="ediscovery"></a>eDiscovery

De forma predeterminada, un administrador o administrador de eDiscovery de un _inquilino multigeográfico_ solo podrá realizar eDiscovery en la _geografía aprovisionada principal_ de ese _inquilino_. El administrador global de Office 365 debe asignar permisos de supervisor de eDiscovery para que otros usuarios puedan ejecutar eDiscovery y asignar un parámetro "Región" en el filtro de seguridad de cumplimiento correspondiente para especificar la región donde se ejecutará eDiscovery como ubicación por satélite; en caso contrario, no se ejecutará eDiscovery en la ubicación por satélite. Para configurar el filtro de seguridad de cumplimiento de una región, vea [Configurar eDiscovery de Office 365 Multi-Geo](multi-geo-ediscovery-configuration.md).

## <a name="exchange-online-mailboxes"></a>Buzones de correo de Exchange Online

Los buzones Exchange Online de los usuarios se mueven automáticamente si se cambia su PDL. Cuando se crea un nuevo buzón, se aprovisiona en la PDL del usuario o en la ubicación central si no se ha establecido ningún valor para la PDL del usuario.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>directiva de prevención de pérdida de datos (DLP) de Information Protection (IP)

Puede establecer las directivas DLP de IP para OneDrive para la Empresa, SharePoint Online y Exchange Online en el Centro de seguridad y cumplimiento, determinando el ámbito de las directivas según sea necesario para todo el _inquilino_ o para los usuarios aplicables. Por ejemplo: si desea seleccionar una directiva para un usuario en una ubicación satélite, seleccione aplicar la directiva a un OneDrive para la Empresa específico y escriba la dirección URL de OneDrive para la Empresa del usuario. Vea [Información general sobre directivas de prevención de pérdida de datos](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) para obtener instrucciones generales para crear directivas de DLP.

Las directivas DLP se sincronizan automáticamente en función de su aplicabilidad a cada ubicación geográfica.

La implementación de directivas de Information Protection y Prevención de pérdida de datos de Microsoft Purview para todos los usuarios de una ubicación geográfica no es una opción disponible en la interfaz de usuario; en su lugar, debe seleccionar las cuentas aplicables para la directiva o aplicar la directiva globalmente a todas las cuentas.

## <a name="microsoft-power-apps"></a>Microsoft Power Apps

Power Apps creado para la ubicación satélite usará el punto final ubicado en la ubicación central del _inquilino_. Microsoft Power Apps no es un servicio multigeográfica. 

## <a name="microsoft-power-automate"></a>Microsoft Power Automate

Los flujos creados para la ubicación satélite usarán el punto final ubicado en la ubicación geográfica predeterminada para el _inquilino_.  Microsoft Power Automate no es un servicio multigeográfica. 

## <a name="sharepoint-online-storage-quota"></a>Cuota de almacenamiento de SharePoint Online

De forma predeterminada, todas las ubicaciones geográficas de un entorno multigeográfico comparten la cuota de almacenamiento de _inquilinos_ disponible.  También puede administrar la cuota de almacenamiento asignando una cuota específica para una ubicación geográfica determinada. Para obtener más información, vea las [Cuotas de almacenamiento de SharePoint en entornos multigeográficos](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Uso compartido

Los administradores pueden configurar y administrar directivas de uso compartido para cada una de sus ubicaciones. Los sitios OneDrive para la Empresa y SharePoint Online de cada ubicación geográfica respetarán solo la configuración de uso compartido específica de la ubicación geográfica correspondiente. (Por ejemplo, puede permitir el [uso compartido externo](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) para la ubicación central, pero no para la ubicación satélite o viceversa). Tenga en cuenta que la configuración de uso compartido no permite configurar las limitaciones de uso compartido entre ubicaciones geográficas.

## <a name="microsoft-stream"></a>Microsoft Stream

Los vídeos cargados en Microsoft Stream en un chat 1:1 se almacenan en el OneDrive para la Empresa de la persona que carga. Las grabaciones de reuniones se almacenan en el OneDrive para la Empresa de cada asistente que registra la reunión.

## <a name="taxonomy"></a>Taxonomía

Se admite una [taxonomía](/sharepoint/managed-metadata) unificada para los metadatos administrados por la empresa en ubicaciones geográficas, con el patrón hospedado en la ubicación central de la empresa. Se recomienda administrar una taxonomía global desde la ubicación central y agregar solo términos específicos de la ubicación a la taxonomía de la ubicación satélite. Los términos de la taxonomía global se sincronizarán con las ubicaciones satélites.

Consulte [Administración de metadatos en un inquilino multigeográfico](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) para obtener más detalles y para obtener instrucciones para desarrolladores.

## <a name="user-profile-application"></a>Aplicación de perfil de usuario

Hay una aplicación de [perfil de usuario](/sharepoint/manage-user-profiles) en cada ubicación geográfica. La información de perfil de cada usuario se hospeda en su ubicación geográfica y está disponible para el administrador de esa ubicación geográfica.

Si tiene propiedades de perfil personalizadas, se recomienda usar el mismo esquema de perfil en todas las zonas geográficas y rellenar las propiedades de perfil personalizadas en todas las ubicaciones geográficas o cuando sea necesario. Para obtener instrucciones sobre cómo rellenar los datos de perfil de usuario mediante programación, consulte la [API de actualización de Perfil de usuario masiva](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).

Consulte [Trabajar con perfiles de usuario en un inquilino multigeográfico](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) para obtener más detalles y obtener instrucciones para desarrolladores.

## <a name="yammer"></a>Yammer

Yammer no es una carga de trabajo multigeográfica. Los subprocesos de Yammer almacenados en Yammer se colocarán en la ubicación central _del inquilino_ . Yammer está implementando un cambio de almacenamiento de archivos que almacenará los archivos de Yammer en SharePoint. Los archivos de Yammer almacenados en SharePoint se colocarán en el sitio de SharePoint asociado al grupo de Yammer. Los sitios de grupo de SharePoint se basan en la lógica PDL como se describe en [Sitios y grupos de SharePoint](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).
