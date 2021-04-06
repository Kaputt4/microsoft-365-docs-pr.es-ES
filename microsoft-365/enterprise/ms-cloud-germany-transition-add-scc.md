---
title: Información sobre la experiencia de exhibición de documentos electrónicos durante la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: pasos de migración de exhibición de documentos electrónicos para la migración desde Microsoft Cloud Deutschland.'
ms.openlocfilehash: 16da6e6d1994ae107b62ff1f915454568a35344d
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592144"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>Información sobre la experiencia de exhibición de documentos electrónicos durante la migración desde Microsoft Cloud Deutschland
Las secciones siguientes proporcionan información adicional sobre la experiencia de exhibición de documentos electrónicos al pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.

## <a name="ediscovery-administration-until-phase-4"></a>Administración de eDiscovery hasta la fase 4
Hasta la fase 4, el Centro de seguridad y cumplimiento estará totalmente disponible. Todo el contenido sigue estando en Microsoft Cloud Germany y es manejable por el Centro de seguridad y cumplimiento de Microsoft Cloud Germany ( https://protection.office.de/) .

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>Experiencia de exhibición de documentos electrónicos entre la fase 4 y el final de la fase 9
Desde el principio de la fase 4 hasta que se complete la fase 9, las búsquedas de exhibición de documentos electrónicos producirán un error o devolverán 0 resultados para las ubicaciones de SharePoint Online, OneDrive para la Empresa y Exchange Online que se han migrado.

> [!NOTE]
> Durante la migración, los clientes pueden seguir crear casos, retenciones, búsquedas y exportaciones en el Centro de seguridad [& cumplimiento,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)incluida [la búsqueda de contenido.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) Sin embargo, las búsquedas en las ubicaciones de SharePoint Online, OneDrive para la Empresa y Exchange Online que se han migrado devolverán 0 resultados o producirán un error.

En caso de que una búsqueda devuelva cero resultados o un error durante la migración, haga lo siguiente para SharePoint Online: 
- Descargue los sitios directamente desde el sitio de SharePoint Online o OneDrive para la Empresa siguiendo las instrucciones de Descargar archivos y carpetas [de OneDrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Este método requerirá permisos de administrador de SharePoint Online o permisos de solo lectura en el sitio.
- Si se superan los límites, como se explica en Descargar archivos y carpetas de OneDrive o [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)los clientes pueden usar el cliente de sincronización de OneDrive para la Empresa siguiendo las instrucciones de Sincronizar archivos de SharePoint y Teams con el [equipo.](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)

- Para obtener más información,  [vea Exhibición de](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery)documentos electrónicos local en Exchange Server .


## <a name="ediscovery-administration-after-phase-9"></a>Administración de eDiscovery después de la fase 9

**Se aplica a:** Todos los clientes que usan eDiscovery

En la fase 9, se completarán los pasos finales para pasar a la nueva región del centro de datos alemán. En esta fase, se migrarán todos los componentes de servicio restantes. Después de la fase 9, ya no se admite el uso del Centro de seguridad y cumplimiento en Microsoft Cloud Germany (protection.office.de). En su lugar, use el nuevo [Centro de seguridad](https://security.microsoft.com/) o centro de [cumplimiento.](https://compliance.microsoft.com/) Todos los datos se han migrado a los nuevos portales de administración. 

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
|  Todas las ubicaciones de SharePoint Online, OneDrive para la Empresa y Exchange Online se han migrado junto con el Centro de seguridad y cumplimiento (SCC). | Toda la actividad de exhibición de documentos electrónicos debe ejecutarse desde el espacio empresarial mundial. Las búsquedas ahora serán 100% correctas. Cualquier error o error debe seguir los canales de soporte técnico normales. | Ninguno |
||||

### <a name="ediscovery-retention-policy"></a>Directiva de retención de eDiscovery
**Se aplica a:**  Todos los clientes que aplicaron una directiva de retención como parte de los pasos previos a la migración

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Quitar directivas de retención de toda la organización que se crearon durante los pasos previos a la migración | Los clientes pueden quitar las directivas de retención de toda la organización que se crearon durante el trabajo previo a la migración de los clientes. | Ninguno |
||||
