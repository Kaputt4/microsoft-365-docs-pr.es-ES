---
title: Solucionar problemas y resolver mensajes de error en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga ayuda para solucionar problemas y mensajes de error.
ms.openlocfilehash: e39eea66222852d8f331aa6bc68b386bea3da763
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63513037"
---
# <a name="troubleshoot-and-resolve-problems-and-error-messages-in-microsoft-365-lighthouse"></a>Solucionar problemas y resolver mensajes de error en Microsoft 365 Lighthouse

En este artículo se describen los mensajes de error y los problemas que puede encontrar al usar Microsoft 365 Lighthouse y se proporcionan los pasos de solución de problemas que puede seguir para resolverlos.

## <a name="partner-onboarding"></a>Incorporación de partners

### <a name="message-when-trying-to-access-lighthouse-microsoft-365-lighthouse-doesnt-support-indirect-providers-at-this-time-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>Mensaje al intentar obtener acceso a Lighthouse: "Microsoft 365 Lighthouse no admite proveedores indirectos en este momento, debe ser un revendedor indirecto o socio de facturación directa para usar este servicio"

**Causa:** Intentó acceder a Lighthouse como socio de factura indirecta. En este momento, Lighthouse solo admite revendedores indirectos y socios de facturación directa.

**Resolución:** Para obtener una lista completa de cualificaciones y requisitos, consulte [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md). Si no es un proveedor indirecto y cree que recibió este mensaje por error, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

### <a name="message-when-trying-to-access-lighthouse-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>Mensaje al intentar obtener acceso a Lighthouse: "Debe ser un revendedor indirecto o un socio de facturación directa para usar este servicio"

**Causa:** Intentó acceder a Lighthouse y no es un socio de Microsoft. Debe estar inscrito en el programa Proveedor de soluciones en la nube (CSP) como revendedor indirecto o socio de facturación directa para usar Lighthouse.

**Resolución:** Para obtener una lista completa de cualificaciones y requisitos, consulte [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md). Si reúne los requisitos para acceder a Lighthouse y cree que recibió este mensaje por error, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

### <a name="message-when-signing-in-to-lighthouse-accept-the-partner-amendment"></a>Mensaje al iniciar sesión en Lighthouse: "Aceptar la modificación de partner"

**Causa:** Intentó obtener acceso a Lighthouse antes de que un administrador global del inquilino asociado firmara la modificación de socio.

**Resolución:** Un administrador global debe iniciar sesión en Lighthouse y aceptar la modificación de socio antes de poder acceder y trabajar en Lighthouse. Si el error persiste después de que un administrador global haya firmado la modificación, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

## <a name="customer-tenant-onboarding"></a>Incorporación de inquilinos de clientes  

### <a name="customer-tenants-show-a-status-other-than-active-in-the-tenant-list"></a>Los inquilinos del cliente muestran un estado distinto de "Activo" en la lista de inquilinos  

**Causa:** Los inquilinos de los clientes no cumplen los siguientes criterios:

  - Debe haber establecido privilegios de administrador delegados (DAP) o granulares delegados (GDAP) para el proveedor de servicios administrados (MSP)
  - Debe tener al menos una Microsoft 365 Empresa Premium o Microsoft 365 E3 licencia
  - No debe tener más de 1000 usuarios con licencia 

**Resolución:** En la tabla siguiente se describen los distintos estados de inquilino que requieren acción y se explica cómo resolverlos.<br><br>

| Estado | Descripción | Solución |
|--|--|--|
| Inactivo | El inquilino se desinbordó a petición del MSP y ya no se está administrando en Lighthouse. | Debe reactivar el espacio empresarial. En la **página Inquilinos** , seleccione los tres puntos (más acciones) junto al espacio empresarial que desea reactivar y, a continuación, **seleccione Activar inquilino**. Los datos iniciales del cliente pueden tardar entre 24 y 48 horas en aparecer en Lighthouse. |
| Ineligible: DAP o GDAP no están configurados | No tiene privilegios de administrador de DAP o GDAP configurados con el inquilino, lo que necesita Lighthouse. | Configurar privilegios de administrador de DAP o GDAP en el Centro de partners de Microsoft. |
| Ineligible: falta la licencia necesaria | Al inquilino le falta una licencia necesaria. Necesitan al menos una Microsoft 365 Empresa Premium o Microsoft 365 E3 licencia. | Asegúrese de que el inquilino tenga asignada al menos Microsoft 365 Empresa Premium o Microsoft 365 E3 licencia. |
| Ineligible: se ha superado el número de usuarios | El inquilino tiene más del máximo de 1000 usuarios con licencia permitidos por Lighthouse. | Compruebe que el inquilino no tiene más de 1000 usuarios con licencia. |
| Ineligible: error en la comprobación geográfica | Usted y su cliente no residen en la misma región geográfica, que es requerida por Lighthouse. | Compruebe que el cliente reside en su región geográfica. Si no es así, no puede administrar el espacio empresarial en Lighthouse. |
| En proceso | Lighthouse descubrió el inquilino, pero aún está en proceso de incorporación. | Permitir a Lighthouse 48 horas completar la incorporación del inquilino. |

Si confirmaste que el inquilino del cliente cumple los criterios de incorporación y aún no se muestran como **activos** en Lighthouse, ponte en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

## <a name="access-and-permissions"></a>Acceso y permisos

### <a name="message-when-trying-to-access-lighthouse-not-authorized-or-insufficient-privileges-or-access-restriction-insufficient-or-lack-of-permissions-is-causing-access-restriction"></a>Mensaje al intentar obtener acceso a Lighthouse: "No autorizado" o "Privilegios insuficientes" o "Restricción de acceso: insuficiente o falta de permisos está provocando restricción de acceso" 

**Causa:** No pertenece al grupo de seguridad correcto en Azure AD o no se le ha asignado el rol correcto en el Centro de partners para poder acceder a Lighthouse.

**Resolución:** Asegúrese de que un administrador de su inquilino asociado con los permisos adecuados le haya asignado el grupo de seguridad GDAP correcto en Azure AD y le haya asignado el rol correcto en el Centro de partners. Además, ten en cuenta que algunas acciones de Lighthouse requieren que seas un administrador global. Para obtener más información sobre los roles de GDAP y lo que cada rol puede hacer, consulte [Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md). Para obtener una descripción detallada de todos Azure AD roles y permisos integrados para GDAP, vea [Azure AD roles integrados](/azure/active-directory/roles/permissions-reference).

Para los clientes con relaciones DAP, el administrador del partner tendrá que asignarle el rol Agente de administración o Agente de soporte técnico en el Centro de partners. Para obtener una descripción detallada de todos los roles y permisos del Centro de partners, vea [Asignar roles y permisos a los usuarios](/partner-center/permissions-overview).

### <a name="i-dont-see-complete-data-in-certain-areas-of-lighthouse-or-i-cant-perform-certain-tasks-or-i-cant-access-certain-tenants"></a>No veo datos completos en determinadas áreas de Lighthouse, o no puedo realizar determinadas tareas o no puedo acceder a determinados inquilinos

**Causa:** Tiene acceso de GDAP limitado en función de los roles asignados al grupo Azure AD seguridad en el que se encuentra.

**Resolución:** Asegúrese de que un administrador de su inquilino asociado con los permisos adecuados le haya asignado el grupo de seguridad GDAP correcto en Azure AD. Además, ten en cuenta que algunas acciones de Lighthouse requieren que seas un administrador global. Para obtener más información sobre los roles de GDAP y lo que cada rol puede hacer, consulte [Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md). Para obtener una descripción detallada de todos Azure AD roles y permisos integrados para GDAP, vea [Azure AD roles integrados](/azure/active-directory/roles/permissions-reference).

## <a name="customer-tenant-management"></a>Administración de inquilinos de clientes  

### <a name="customer-tenant-has-no-data-showing-in-lighthouse"></a>El inquilino del cliente no tiene datos que se muestren en Lighthouse

**Causa:** Está intentando ver los datos en Lighthouse antes de que se complete la incorporación de inquilinos.

**Resolución:** Los datos iniciales del cliente pueden tardar entre 24 y 48 horas en aparecer en Lighthouse. Si han pasado más de 48 horas desde que incorporó el inquilino y aún no puede ver o cargar datos de inquilino, o no puede ver o cargar datos que anteriormente había podido, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md). Esté preparado para proporcionar registros de red relevantes y una lista de las opciones que se hayan modificado.

### <a name="customer-tenant-data-isnt-updating-after-making-changes-in-the-customer-tenant"></a>Los datos del inquilino del cliente no se actualizan después de realizar cambios en el inquilino del cliente

**Causa:** Los cambios realizados dentro del inquilino del cliente pueden tardar hasta 4 horas en sincronizarse con los datos del inquilino del cliente en Lighthouse.

**Resolución:** Si han pasado más de 4 horas y los datos del inquilino del cliente aún no se actualizan en Lighthouse, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md). Esté preparado para proporcionar información del inquilino del cliente.

### <a name="message-when-applying-a-baseline-to-a-customer-tenant-process-error-occurred"></a>Mensaje al aplicar una línea base a un inquilino del cliente: "Error de proceso"  

**Causa:** No ha completado correctamente la configuración de Microsoft Intune dentro del inquilino del cliente.

**Resolución:** Compruebe que ha completado los pasos básicos de configuración de Intune en el inquilino del cliente. Si el problema persiste después de comprobar que la configuración de Intune se ha completado para el inquilino del cliente, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

### <a name="cant-access-partner-tenant-data-in-lighthouse"></a>No se puede acceder a los datos de inquilinos de partners en Lighthouse

**Causa**: Lighthouse solo admite la visualización y administración de *inquilinos* de clientes. Actualmente no es compatible con la visualización y administración de inquilinos *asociados* .

**Resolución:** Siga usando cualquier método que haya estado usando para ver y administrar el espacio empresarial del partner.

## <a name="device-and-threat-management"></a>Administración de dispositivos y amenazas 

### <a name="i-dont-see-any-customer-tenant-data-on-the-device-compliance-and-threat-management-pages-of-lighthouse"></a>No veo datos de inquilinos de clientes en las páginas de administración de amenazas y cumplimiento de dispositivos de Lighthouse

**Causa 1:** El inquilino del cliente no ha completado la incorporación a Intune. Los datos del inquilino del cliente no estarán disponibles en las páginas Cumplimiento del dispositivo o Administración de amenazas de Lighthouse hasta que el inquilino del cliente haya completado la incorporación a Intune.

**Resolución:** Compruebe que el inquilino del cliente para el que está intentando ver los datos haya completado la incorporación a Intune. Una vez completada la incorporación en Intune, espere 4 horas para que los datos del dispositivo aparezcan en Lighthouse.

**Causa 2:** El inquilino del cliente se incorporó recientemente a Lighthouse y los datos se siguen cargando en Lighthouse.

**Resolución:** Una vez que un inquilino del cliente se incorpore a Lighthouse, espere de 24 a 48 horas para que aparezcan los datos de cliente iniciales.

**Causa 3:** El dispositivo de inquilino del cliente es nuevo y los datos del dispositivo se siguen cargando en Lighthouse.

**Resolución:** Cuando se agrega un dispositivo de inquilino, espere 4 horas para que los datos del dispositivo aparezcan en Lighthouse.

Si los datos siguen sin aparecer en las páginas de administración de amenazas y cumplimiento de dispositivos después de seguir las instrucciones de resolución, póngase en contacto con el soporte técnico. Para obtener más información, consulte [Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md).

## <a name="related-content"></a>Contenido relacionado

[Problemas conocidos con Microsoft 365 Lighthouse](m365-lighthouse-known-issues.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)\
[Obtener ayuda y soporte técnico para Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md) (artículo)