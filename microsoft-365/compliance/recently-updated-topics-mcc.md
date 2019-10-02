---
title: Novedades en el centro de cumplimiento de Microsoft 365
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Al igual que con las características del centro de cumplimiento de Microsoft 365, el contenido de ayuda está evolucionando siempre. Estamos creando artículos nuevos, actualizando los existentes y realizando cambios en función de sus comentarios. Descubra las novedades y las actualizaciones de este mes.
ms.openlocfilehash: 744c1822331c71e718007105f58d1bc64b3c70df
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369660"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Actualizaciones recientes del contenido de cumplimiento de Microsoft 365

Al igual que con las características del centro de cumplimiento de Microsoft 365, el contenido de ayuda está evolucionando siempre. Estamos creando artículos nuevos, actualizando los existentes y realizando cambios en función de sus comentarios. Eche un vistazo al siguiente para ver las novedades y las actualizaciones de este mes.

> [!TIP]
> Para estar al tanto de las últimas actualizaciones de características en el centro de cumplimiento de Microsoft 365, consulte [what's New in the microsoft 365 Compliance Center](whats-new.md).

## <a name="september"></a>Septiembre

### <a name="ediscovery"></a>eDiscovery

[Investigar, solucionar problemas y resolver problemas comunes de eDiscovery](ediscovery-troubleshooting-common-issues.md) (nuevo)<br> Incluye los pasos básicos de solución de problemas que puede seguir para identificar y resolver los problemas que se encuentren durante una búsqueda de exhibición de documentos electrónicos o en cualquier otro lugar del proceso de eDiscovery.

###<a name="supervision"></a>Supervisión

[Configuración de directivas de supervisión para la organización](configure-supervision-policies.md) (actualizada)<br>Se quitaron los detalles sobre el uso de Outlook para realizar revisiones. En su lugar, use las opciones de revisión y etiquetado disponibles en la interfaz de usuario de supervisión.

## <a name="august-2019"></a>Agosto de 2019

### <a name="auditing"></a>Auditoría

[Administrar la auditoría de buzones de correo](enable-mailbox-auditing.md#more-information) (actualizado)<br>Se agregaron detalles sobre cómo los eventos de registro de auditoría de buzones de correo solo están disponibles para los usuarios con licencias de E5 o buzones en los que un administrador activó manualmente la auditoría de buzones de correo. También nuevas instrucciones sobre cómo usar el cmdlet **Search-MailboxAuditLog** en Exchange Online PowerShell para buscar en el registro de auditoría de buzones de correo los usuarios sin licencias de E5.

[Buscar en el registro de auditoría de 365 de Office para solucionar escenarios comunes](auditing-troubleshooting-scenarios.md#investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization) (actualizados)<br>Nueva sección sobre el uso de la autenticación de paso a través para investigar los inicios de sesión correctos por parte de usuarios externos.

### <a name="content-search--ediscovery"></a>Búsqueda de contenido & eDiscovery

[Configurar el filtrado de permisos para la búsqueda de contenido](permissions-filtering-for-content-search.md#using-a-filters-list-to-combine-filter-types) (actualizado)<br>Se agregaron detalles sobre el uso de una lista de filtros, que permite agregar filtros de buzón de correo y sitio a un único filtro de permisos de búsqueda.

[Búsqueda de contenido en Office 365](content-search.md#searching-disconnected-or-de-licensed-mailboxes) (actualizado)<br>Se agregaron detalles sobre los buzones de búsqueda desconectados o deshabilitados.

[Búsqueda de contenido en Office 365](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment) (actualizado)<br>
[Configurar límites de cumplimiento para investigaciones de eDiscovery en Office 365](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments) (actualizado)<br>Se agregaron detalles a ambos artículos sobre la búsqueda de contenido en entornos multigeográfico de SharePoint.

### <a name="data-governance"></a>Gobierno de datos

[Información general sobre el archivado ilimitado en Office 365](unlimited-archiving.md#how-auto-expanding-archiving-works) (actualizado)<br>Se agregaron detalles sobre cómo Office 365 agrega un máximo de 20 archivos auxiliares para un total de 1 TB de almacenamiento adicional.

### <a name="data-investigations"></a>Investigaciones de datos

[Eliminar elementos de su ubicación original (versión preliminar)](delete-items-from-original-locations.md) (nueva)<br>Ahora disponible en la versión preliminar, puede seleccionar elementos en un conjunto de evidencias y, a continuación, eliminarlos temporalmente de sus ubicaciones originales en Exchange, SharePoint y OneDrive.

[Administración de un incidente de derrame de datos en Microsoft 365](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) (actualizado)<br>Se agregaron detalles sobre cómo usar la nueva característica "eliminar elementos de su ubicación original" para eliminar datos derramados.

### <a name="permissions"></a>Permisos

[Permisos en el centro de cumplimiento de microsoft 365 y el centro de seguridad de microsoft 365](../security/office-365-security/permissions-microsoft-365-compliance-security.md) (nueva)<br>Los nuevos grupos de roles de Azure Active Directory se publicaron en la versión preliminar pública.

### <a name="records-management"></a>Administración de registros

[Información general sobre el administrador del plan de archivos (actualizado)](file-plan-manager.md#export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews)<br>Se agregó una tabla que enumera los valores válidos que se van a usar en la plantilla de Excel.

### <a name="supervision"></a>Supervisión

[Directivas de supervisión en Office 365](supervision-policies.md) (actualizada)<br>Se ha aclarado la compatibilidad de grupos y listas de distribución de Office 365, se han agregado instrucciones para coincidencias de palabras clave en correos electrónicos y datos adjuntos, y se clarifica la compatibilidad con Outlook en los canales de Team

### <a name="windows-information-protection"></a>Windows Information Protection

[Lista de aplicaciones de Microsoft habilitadas para su uso con Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/enlightened-microsoft-apps-and-wip) (actualizado) <br>Microsoft 3D Viewer ahora es una aplicación habilitada.
