---
title: Solución de problemas y mensajes de error en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: troubleshooting
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga ayuda para solucionar problemas y mensajes de error.
ms.openlocfilehash: dd0867611eb0a77b0e45cb5471fb5789dccf0a4d
ms.sourcegitcommit: 852075d8d8a4ca052f69e854396d1565ef713500
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2022
ms.locfileid: "65692682"
---
# <a name="troubleshoot-error-messages-and-problems-in-microsoft-365-lighthouse"></a>Solución de problemas y mensajes de error en Microsoft 365 Lighthouse

En este artículo se describen los mensajes de error y los problemas que puede encontrar al usar Microsoft 365 Lighthouse y se proporcionan los pasos de solución de problemas que puede seguir para resolverlos.

## <a name="partner-onboarding"></a>Incorporación de asociados

### <a name="message-when-trying-to-access-lighthouse-microsoft-365-lighthouse-doesnt-support-indirect-providers-at-this-time-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>Mensaje al intentar acceder a Lighthouse: "Microsoft 365 Lighthouse no admite proveedores indirectos en este momento, debe ser revendedor indirecto o asociado de factura directa para usar este servicio"

**Causa:** Intentó acceder a Lighthouse como asociado de factura indirecta. En este momento, Lighthouse solo admite revendedores indirectos y asociados de factura directa.

**Resolución:** Para obtener una lista completa de calificaciones y requisitos, consulte [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md). Si no es un proveedor indirecto y cree que ha recibido este mensaje por error, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

### <a name="message-when-trying-to-access-lighthouse-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>Mensaje al intentar acceder a Lighthouse: "Debe ser revendedor indirecto o asociado de factura directa para usar este servicio".

**Causa:** Intentó acceder a Lighthouse y no es un asociado de Microsoft. Debe estar inscrito en el programa Proveedor de soluciones en la nube (CSP) como revendedor indirecto o asociado de factura directa para usar Lighthouse.

**Resolución:** Para obtener una lista completa de calificaciones y requisitos, consulte [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md). Si cumple los requisitos para acceder a Lighthouse y cree que ha recibido este mensaje por error, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

### <a name="message-when-signing-in-to-lighthouse-accept-the-partner-amendment"></a>Mensaje al iniciar sesión en Lighthouse: "Aceptar la enmienda del asociado"

**Causa:** Intentó acceder a Lighthouse antes de que un administrador global del inquilino del asociado haya firmado la modificación del asociado.

**Resolución:** Un administrador global debe iniciar sesión en Lighthouse y aceptar la modificación del asociado para poder acceder a Lighthouse y trabajar en este. Si el error persiste después de que un administrador global haya firmado la enmienda, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

## <a name="customer-tenant-onboarding"></a>Incorporación de inquilinos del cliente  

### <a name="customer-tenants-show-a-status-other-than-active-in-the-tenant-list"></a>Los inquilinos del cliente muestran un estado distinto de "Activo" en la lista de inquilinos  

**Causa:** Los inquilinos del cliente no cumplen los siguientes criterios:

- Debe tener el acceso delegado configurado para que el proveedor de servicios administrados (MSP) pueda administrar el inquilino del cliente*
- Debe tener al menos un Microsoft 365 Empresa Premium, Microsoft 365 E3, Microsoft 365 E5, Windows 365 Business o Microsoft Defender para Empresas Licencia
- No debe tener más de 1000 usuarios con licencia 

**Resolución:** En la tabla siguiente se describen los distintos estados de inquilino que requieren acción y se explica cómo resolverlos.

*Se requiere privilegios de Administración delegados (DAP) para incorporar clientes a Lighthouse. También se recomienda establecer privilegios de Administración delegados granulares (GDAP) con los clientes para habilitar un acceso delegado más seguro. Aunque DAP y GDAP coexisten, GDAP tendrá prioridad para los clientes en los que ambos modelos están en vigor. Pronto, los clientes con solo GDAP (y sin DAP) podrán incorporarse a Lighthouse.

| Estado | Descripción | Solución |
|--|--|--|
| Inactivo | El inquilino se quitó a petición del MSP y ya no se administra en Lighthouse. | Debe reactivar el inquilino. En la página **Inquilinos** , seleccione los tres puntos (más acciones) junto al inquilino que desea reactivar y, a continuación, seleccione **Activar inquilino**. Los datos iniciales del cliente pueden tardar entre 24 y 48 horas en aparecer en Lighthouse. |
| Inelegible: DAP o GDAP no está configurado | No tiene privilegios de administrador de DAP o GDAP configurados con el inquilino, lo que Necesita Lighthouse. | Configure los privilegios de administrador de DAP o GDAP en el Centro de partners de Microsoft. |
| No válido: falta la licencia necesaria | Al inquilino le falta una licencia necesaria. Necesitan al menos una licencia de Microsoft 365 Empresa Premium, Microsoft 365 E3, Microsoft 365 E5 o Microsoft Defender para Empresas. | Asegúrese de que el inquilino tiene al menos un Microsoft 365 Empresa Premium, Microsoft 365 E3, Microsoft 365 E5, Windows 365 Business o Microsoft Defender para Empresas licencia asignada. |
| No válido: se superó el recuento de usuarios | El inquilino tiene más de 1000 usuarios con licencia permitidos por Lighthouse. | Compruebe que el inquilino no tiene más de 1000 usuarios con licencia. |
| No válido: error de comprobación geográfica | Usted y su cliente no residen en la misma región geográfica, lo que Lighthouse requiere. | Compruebe que el cliente reside en su región geográfica. Si no es así, no puede administrar el inquilino en Lighthouse. |
| En proceso | Lighthouse descubrió el inquilino, pero todavía está en proceso de incorporación. | Espere 48 horas a Lighthouse para completar la incorporación del inquilino. |

Si ha confirmado que el inquilino del cliente cumple los criterios de incorporación y que todavía no se muestran como **Activos** en Lighthouse, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

## <a name="access-and-permissions"></a>Acceso y permisos

### <a name="message-when-trying-to-access-lighthouse-not-authorized-or-insufficient-privileges-or-access-restriction-insufficient-or-lack-of-permissions-is-causing-access-restriction"></a>Mensaje al intentar acceder a Lighthouse: "No autorizado" o "Privilegios insuficientes" o "Restricción de acceso: Insuficiente o falta de permisos está causando restricción de acceso" 

**Causa:** No pertenece al grupo de seguridad correcto en Azure AD o no se le ha asignado el rol correcto en el Centro de partners para poder acceder a Lighthouse.

**Resolución:** Asegúrese de que un administrador del inquilino del asociado con los permisos adecuados le ha asignado al grupo de seguridad de GDAP correcto en Azure AD y le ha asignado el rol correcto en el Centro de partners. Además, tenga en cuenta que algunas acciones de Lighthouse requieren que sea administrador global. Para más información sobre los roles de GDAP y lo que puede hacer cada rol, consulte [Introducción a los permisos en Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md). Para obtener una descripción detallada de todos los roles y permisos integrados de Azure AD para GDAP, consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference).

En el caso de los clientes con relaciones de DAP, el administrador del asociado deberá asignarle el rol de agente de Administración o agente del departamento de soporte técnico en el Centro de partners. Para obtener una descripción detallada de todos los roles y permisos del Centro de partners, consulte [Asignación de roles y permisos a los usuarios](/partner-center/permissions-overview).

### <a name="i-dont-see-complete-data-in-certain-areas-of-lighthouse-or-i-cant-perform-certain-tasks-or-i-cant-access-certain-tenants"></a>No veo datos completos en ciertas áreas de Lighthouse, o no puedo realizar ciertas tareas, o no puedo acceder a determinados inquilinos.

**Causa:** Tiene acceso GDAP limitado en función de los roles asignados al grupo de seguridad de Azure AD en el que se encuentra.

**Resolución:** Asegúrese de que un administrador del inquilino del asociado con los permisos adecuados le haya asignado al grupo de seguridad de GDAP correcto en Azure AD. Además, tenga en cuenta que algunas acciones de Lighthouse requieren que sea administrador global. Para más información sobre los roles de GDAP y lo que puede hacer cada rol, consulte [Introducción a los permisos en Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md). Para obtener una descripción detallada de todos los roles y permisos integrados de Azure AD para GDAP, consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference).

## <a name="customer-tenant-management"></a>Administración de inquilinos del cliente  

### <a name="customer-tenant-has-no-data-showing-in-lighthouse"></a>El inquilino del cliente no tiene datos que se muestren en Lighthouse

**Causa:** Está intentando ver los datos en Lighthouse antes de que se complete la incorporación de inquilinos.

**Resolución:** Los datos iniciales del cliente pueden tardar entre 24 y 48 horas en aparecer en Lighthouse. Si han pasado más de 48 horas desde que incorporó el inquilino y aún no puede ver ni cargar datos del inquilino, o no puede ver ni cargar los datos que anteriormente había podido, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md). Esté preparado para proporcionar los registros de red pertinentes y una lista de las opciones que se hayan modificado.

### <a name="customer-tenant-data-isnt-updating-after-making-changes-in-the-customer-tenant"></a>Los datos del inquilino del cliente no se actualizan después de realizar cambios en el inquilino del cliente

**Causa:** Los cambios realizados dentro del inquilino del cliente pueden tardar hasta 4 horas en sincronizarse con los datos del inquilino del cliente en Lighthouse.

**Resolución:** Si han pasado más de 4 horas y los datos del inquilino del cliente siguen sin actualizarse en Lighthouse, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md). Prepárese para proporcionar información sobre el inquilino del cliente.

### <a name="message-when-applying-a-baseline-to-a-customer-tenant-process-error-occurred"></a>Mensaje al aplicar una línea base a un inquilino de cliente: "Error de proceso"  

**Causa:** No completó correctamente la configuración de Microsoft Intune dentro del inquilino del cliente.

**Resolución:** Compruebe que ha completado los pasos de configuración básicos para Intune dentro del inquilino del cliente. Si el problema persiste después de comprobar que Intune configuración está completa para el inquilino del cliente, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

### <a name="cant-access-partner-tenant-data-in-lighthouse"></a>No se puede acceder a los datos del inquilino del asociado en Lighthouse

**Causa**: Lighthouse solo admite la visualización y administración de inquilinos de *clientes* . Actualmente no admite la visualización y *administración de* inquilinos asociados.

**Resolución:** Siga usando cualquier método que haya usado para ver y administrar el inquilino del asociado.

## <a name="device-and-threat-management"></a>Administración de dispositivos y amenazas 

### <a name="i-dont-see-any-customer-tenant-data-on-the-device-compliance-and-threat-management-pages-of-lighthouse"></a>No veo ningún dato de inquilino de cliente en las páginas Cumplimiento de dispositivos y Administración de amenazas de Lighthouse

**Causa 1:** El inquilino del cliente no ha completado la incorporación a Intune. Los datos del inquilino del cliente no estarán disponibles en las páginas Cumplimiento de dispositivos o Administración de amenazas de Lighthouse hasta que el inquilino del cliente haya completado la incorporación a Intune.

**Resolución:** Compruebe que el inquilino del cliente para el que intenta ver los datos haya completado la incorporación a Intune. Una vez completada la incorporación en Intune, espere 4 horas para que los datos del dispositivo aparezcan en Lighthouse.

**Causa 2:** El inquilino del cliente se ha incorporado recientemente a Lighthouse y los datos se siguen cargando en Lighthouse.

**Resolución:** Una vez que un inquilino de cliente se incorpore a Lighthouse, permita que aparezcan entre 24 y 48 horas para que aparezcan los datos iniciales del cliente.

**Causa 3:** El dispositivo de inquilino del cliente es nuevo y los datos del dispositivo se siguen cargando en Lighthouse.

**Resolución:** Cuando se agrega un dispositivo de inquilino, espere 4 horas para que los datos del dispositivo aparezcan en Lighthouse.

Si los datos siguen sin aparecer en las páginas Cumplimiento de dispositivos y Administración de amenazas después de seguir las instrucciones de resolución, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

## <a name="related-content"></a>Contenido relacionado

[Problemas conocidos con Microsoft 365 Lighthouse](m365-lighthouse-known-issues.md) (artículo)\
[preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)\
[Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md) (artículo)
