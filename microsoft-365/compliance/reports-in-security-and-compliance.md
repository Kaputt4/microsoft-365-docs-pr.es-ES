---
title: Informes en el Centro de seguridad y cumplimiento
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: Use el Centro de seguridad & cumplimiento para obtener varios informes para su organización de SharePoint Online y Exchange Online, además de informes de Azure Active Directory.
ms.openlocfilehash: 8762c1bbb23d2b9f3840076f0ffa465cf7ab264b
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936183"
---
# <a name="reports-in-the-security--compliance-center"></a>Informes en el Centro de seguridad y cumplimiento

Puede usar la página Ver **informes** en el Centro de seguridad & Cumplimiento para obtener acceso rápidamente a los informes de auditoría de las organizaciones de SharePoint Online y Exchange Online. También puede acceder a los informes de inicio de sesión de usuario de Azure Active Directory (AD), a los informes de actividad de usuario y al registro de auditoría de Azure AD desde la **página Ver informes.** Esto se debe a que su suscripción de pago a Microsoft 365 incluye una suscripción gratuita a Microsoft Azure. La primera vez que intente obtener acceso a estos informes de Azure, tendrá que completar un proceso de registro único. 
  
> [!TIP]
> Para ver informes adicionales sobre la actividad de su organización, consulte [Informes de actividades en el Centro de administración de Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports) 
  
 **Antes de empezar**
  
Necesita los siguientes permisos para ver informes en el Centro de seguridad & cumplimiento.
  
- Debe tener asignado el rol lector de seguridad en el Centro de administración de Exchange (EAC) para ver informes en el Centro de & cumplimiento. De forma predeterminada, este rol se asigna a los grupos de roles Administración de la organización y Lector de seguridad en el EAC.
    
- Debe tener asignado el rol View-Only administración de cumplimiento DLP en el Centro de seguridad y cumplimiento de & para ver informes DLP en el Centro de seguridad & cumplimiento. De forma predeterminada, este rol se asigna a los grupos de roles Administrador de cumplimiento, Administración de la organización, Administrador de seguridad y Lector de seguridad en el Centro de & Cumplimiento.

- Además, debe tener asignado el rol View-Only Destinatarios en el EAC para ver informes DLP en el EAC. De forma predeterminada, este rol se asigna a los grupos de roles Administración del cumplimiento, Administración de la organización y Administración View-Only organización en el EAC.
  
 **Para abrir la página Ver informes en el Centro de & cumplimiento:**
  
1. Vaya a [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Inicie sesión con las credenciales de una cuenta de usuario de su organización.
    
En la **página Ver informes,** puede ver los siguientes tipos de informes: 
  
- [Informes de auditoría](#auditing-reports)
- [Informe de revisión de supervisión](#supervisory-review-report)
- [Informes de prevención de pérdida de datos](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Informes de auditoría

En la tabla siguiente se  describen los  informes de la sección Auditoría de la página Ver informes del Centro de & cumplimiento. 
  
|**Informe**|**Descripción**|
|:-----|:-----|
|**informe de registro de auditoría** <br/> |Puede buscar en el registro de auditoría la actividad de usuario y administrador de su organización. El informe contiene entradas de actividad de usuario y administrador en Exchange Online, SharePoint Online, OneDrive para la Empresa y Azure Active Directory, que es el servicio de directorio para Office 365. Para obtener más información, [vea Buscar en el registro de auditoría de Office 365.](search-the-audit-log-in-security-and-compliance.md)  <br/> |
|**Informes de Azure AD** <br/> |Para buscar actividad de inicio de sesión inusual o sospechosa en su organización, puede usar los informes de inicio de sesión y actividad en Microsoft Azure. También puede ver eventos en el registro de auditoría de Azure AD. Para ver informes en Azure, solo tiene que hacer clic **en Ver informes de Azure AD.** Para obtener más información, vea: <br/><br/>[Use su suscripción gratuita de Azure Active Directory en Office 365.](use-your-free-azure-ad-subscription-in-office-365.md) <br/> [Ver los informes de acceso y uso.](https://go.microsoft.com/fwlink/p/?LinkId=506902)  <br/> |
|**Informes de auditoría de Exchange** <br/> | Puede usar la funcionalidad de auditoría de Microsoft 365 para realizar un seguimiento de los cambios realizados en la configuración de Exchange Online por parte de los administradores de su organización. También se registran los cambios realizados en la organización de Exchange Online por un administrador del centro de datos de Microsoft o por un administrador delegado. Para Exchange Online, el registro de auditoría de administrador está habilitado de forma predeterminada, por lo que no tiene que hacer nada para activarlo. Exchange Online también proporciona un registro de auditoría de buzones para que pueda realizar un seguimiento del acceso a los buzones por parte de otra persona que no sea el propietario del buzón. Tiene que habilitar el registro de auditoría de buzones de correo para cada buzón en el que quiera realizar un seguimiento del acceso de no propietarios.  <br/>  Tanto para el proceso de registro de auditoría del administrador como de los buzones, puede ejecutar informes de auditoría para ver las entradas del registro de auditoría. También puede exportar los registros de auditoría del administrador y de los buzones que se le envían en un plazo de 24 horas en un archivo XML adjunto al mensaje de correo electrónico. <br/><br/>Para obtener más información acerca de la exportación de registros de auditoría, consulte:  <br/><br/> [Exportar registros de auditoría de buzones](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Ver y exportar el registro de auditoría de administración del centro de datos](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Buscar los informes de cambios del grupo de roles o auditorías de administrador](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Informes de auditoría de Exchange](https://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## <a name="supervisory-review-report"></a>Informe de revisión de supervisión

Con el informe de revisión de supervisión, puede ver el estado de todas las directivas de revisión de supervisión de su organización. Para obtener más información, consulte [Configurar directivas de revisión de supervisión para su organización.](configure-supervision-policies.md)
  
## <a name="data-loss-prevention-reports"></a>Informes de prevención de pérdida de datos

Los informes de prevención de pérdida de datos (DLP) contienen información sobre las directivas y reglas dlp que se han aplicado al contenido que contiene datos confidenciales de la organización. También puede configurar el informe para mostrar información acerca de las acciones de DLP que se basaban en las reglas y directivas DLP. Para obtener más información, vea [Ver el informe de prevención de pérdida de datos.](view-the-dlp-reports.md)
