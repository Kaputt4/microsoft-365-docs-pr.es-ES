---
title: Administrar dispositivos inscritos en Administración de dispositivos móviles en Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: La movilidad y la seguridad básicas pueden ayudarle a proteger y administrar dispositivos móviles.
ms.openlocfilehash: 4ff1c43343e00b7eac7aa38b2d266f163f79e2a7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023886"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Administrar dispositivos inscritos en Administración de dispositivos móviles en Microsoft 365

La administración integrada de dispositivos móviles para Microsoft 365 te ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhones, iPads, Android y teléfonos Windows. El primer paso es iniciar sesión en Microsoft 365 y configurar La movilidad y la seguridad básicas. Para obtener más información, consulta [Configurar movilidad básica y seguridad.](set-up.md)

Después de configurarlo, los usuarios de la organización deben inscribir sus dispositivos en el servicio. Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas.](enroll-your-mobile-device.md)A continuación, puedes usar movilidad básica y seguridad para ayudar a administrar los dispositivos de la organización. Por ejemplo, puedes usar directivas de seguridad de dispositivos para ayudar a limitar el acceso al correo electrónico u otros servicios, ver informes de dispositivos y borrar de forma remota un dispositivo. Normalmente, irá al Centro de seguridad y & cumplimiento para realizar estas tareas. Para obtener más información, consulta [Centro de cumplimiento de Microsoft 365](../../compliance/microsoft-365-compliance-center.md).

## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Para llegar al panel de administración de dispositivos, siga estos pasos:

1. Vaya al [Centro de administración de Microsoft 365](../../admin/admin-overview/about-the-admin-center.md).

2. Escribe Administración de dispositivos móviles en el campo de búsqueda y selecciona **Administración de dispositivos móviles** en la lista de   resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opción de administración de dispositivos móviles":::

3. Seleccione  **Empecemos.**

## <a name="manage-mobile-devices"></a>Administrar dispositivos móviles

Después de configurar La movilidad y la seguridad básicas, estas son algunas maneras de administrar los dispositivos móviles de la organización.

|**Para**|**Haga esto…**|
|:----------------|:------------------------------------------------------------------------------|
|Eliminar los datos de un dispositivo |En el panel Administración de dispositivos, *selecciona* Nombre del dispositivo y, a continuación, Borrar por completo para eliminar toda la información o Borrado selectivo para eliminar solo la información  ****   de la organización en  ****   el dispositivo. Para obtener más información, [consulta Borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).|
|Bloquear el acceso de dispositivos no compatibles al correo electrónico de Exchange con Exchange ActiveSync |En el panel Administración de dispositivos, seleccione  **Bloquear**. |
|Configurar directivas de dispositivos como requisitos de contraseña y configuración de seguridad |En el panel Administración de dispositivos, selecciona **Directivas de seguridad de**   >  **dispositivos Agregar +**. Para obtener más información, consulta [Crear directivas de seguridad de dispositivos en Basic Mobility and Security](create-device-security-policies.md).|
|Ver la lista de dispositivos bloqueados  |En el panel Administración de dispositivos, en  **Seleccionar una vista, seleccione**     **Bloqueado**. |
|Desbloquear un dispositivo no compatible o no admitido para un usuario o grupo de usuarios  |Elija una de las siguientes opciones para desbloquear dispositivos:<br/>- Quite el usuario o los usuarios del grupo de seguridad al que se ha aplicado la directiva. Vaya al Centro de administración de Microsoft 365 > **grupos** y, a continuación, seleccione nombre de grupo. Seleccione **Editar miembros y administradores**.<br/>- Quitar el grupo de seguridad del que los usuarios son miembros de la directiva de dispositivo. Vaya a Security & Compliance Center > **Security policies** Device   >  **security policies**. Seleccione el nombre de la directiva de dispositivo y, a continuación, **seleccione Editar**  >  **implementación**.<br/>- Desbloquear todos los dispositivos no compatibles para una directiva de dispositivo. Vaya a Security & Compliance Center > **Security policies** Device   >  **security policies**. Seleccione el nombre de la directiva de dispositivo y, a continuación, **seleccione Editar**  >  **requisitos de Acceso.** Seleccione  **Permitir acceso e informar de la infracción**.<br/>- Para desbloquear un dispositivo no compatible o no compatible para un usuario o un grupo de usuarios, vaya a Security & Compliance Center > **Security policies**   >  **Device management**   >  **Manage device access settings**. Agrega un grupo de seguridad con los miembros que quieras excluir para que no se bloquee el acceso a Microsoft 365. Para obtener más información, consulta Crear, editar o eliminar un grupo de seguridad en el Centro de [administración de Microsoft 365](../../admin/email/create-edit-or-delete-a-security-group.md).|
|Quitar usuarios para que sus dispositivos ya no estén administrados por Basic Mobility and Security |Para quitar el usuario, edite el grupo de seguridad que tiene directivas de administración de dispositivos para Movilidad y seguridad básicas. Para obtener más información, consulta Crear, editar o eliminar un grupo de seguridad en el Centro de  [administración de Microsoft 365](../../admin/email/create-edit-or-delete-a-security-group.md).<br/>Para quitar la movilidad básica y la seguridad de todos los usuarios de Microsoft 365, vea Desactivar la movilidad [básica y la seguridad](turn-off.md).|

Live (v14)