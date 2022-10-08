---
title: Administración de dispositivos inscritos en Mobile Administración de dispositivos en Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- MET150
description: Inicie sesión en Microsoft 365 y configure Basic Mobility and Security para usar la administración integrada de dispositivos móviles para proteger y administrar los dispositivos móviles de los usuarios.
ms.openlocfilehash: d9021534e6d4290fcfdfe6d387fc932898027124
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68204989"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Administración de dispositivos inscritos en Mobile Administración de dispositivos en Microsoft 365

La administración integrada de dispositivos móviles para Microsoft 365 le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhones, iPads, Android y teléfonos Windows. El primer paso consiste en iniciar sesión en Microsoft 365 y configurar Basic Mobility and Security. Para obtener más información, consulte [Configuración de Basic Mobility and Security](set-up.md).

Después de configurarlo, los usuarios de la organización deben inscribir sus dispositivos en el servicio. Para obtener más información, consulta [Inscribir tu dispositivo móvil con Basic Mobility and Security](enroll-your-mobile-device.md). A continuación, puede usar Basic Mobility and Security para ayudar a administrar los dispositivos de su organización. Por ejemplo, puede usar directivas de seguridad de dispositivos para ayudar a limitar el acceso al correo electrónico u otros servicios, ver informes de dispositivos y borrar un dispositivo de forma remota. Normalmente, irá al Centro de cumplimiento de seguridad & para realizar estas tareas. Para obtener más información, consulte [portal de cumplimiento Microsoft Purview](../../compliance/microsoft-365-compliance-center.md).

## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Para acceder al panel de administración de dispositivos, siga estos pasos:

1. Inicie sesión en el Centro de administración de Microsoft 365 y vaya a la [página Mobile Administración de dispositivos (Mobile Administración de dispositivos).](https://portal.office.com/adminportal/home?#/MifoDevices)

1. Seleccione **Vamos a empezar**.

## <a name="manage-mobile-devices"></a>Administrar dispositivos móviles

Después de configurar Basic Mobility and Security, estas son algunas maneras de administrar los dispositivos móviles de la organización.

|Para|Haga esto|
|---|---|
|Eliminar los datos de un dispositivo|En el panel Administración de dispositivos, seleccione *nombre del dispositivo* y, a continuación, **Borrado completo** para eliminar toda la información o **Borrado selectivo** para eliminar solo la información de la organización en el dispositivo. Para obtener más información, consulta [Borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).|
|Bloquear el acceso de dispositivos no compatibles al correo electrónico de Exchange con Exchange ActiveSync|En el panel Administración de dispositivos, seleccione **Bloquear**.|
|Configuración de directivas de dispositivo, como los requisitos de contraseña y la configuración de seguridad|En el panel Administración de dispositivos, seleccione Directivas  > **de seguridad de** dispositivos **Agregar +**. Para obtener más información, consulte [Creación de directivas de seguridad de dispositivos en Basic Mobility and Security](create-device-security-policies.md).|
|Ver la lista de dispositivos bloqueados|En el panel Administración de dispositivos, en **Seleccionar una vista**, seleccione **Bloqueado**.|
|Desbloquear un dispositivo no compatible o no admitido para un usuario o grupo de usuarios|Elija una de las siguientes opciones para desbloquear dispositivos:<br/>- Quite el usuario o los usuarios del grupo de seguridad al que se ha aplicado la directiva. Vaya a grupos de Centro de administración de Microsoft 365 > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**y, a**</a> continuación, seleccione nombre del grupo. Seleccione **Editar miembros y administradores**.<br/>- Quite el grupo de seguridad del que son miembros los usuarios de la directiva de dispositivo. Vaya a Security & Compliance Center > **Security policies** > **Device security policies (Directivas de seguridad del dispositivo**). Seleccione el nombre de la directiva de dispositivo y, a continuación, seleccione **Editar** > **implementación**.<br/>- Desbloquee todos los dispositivos no conformes para una directiva de dispositivo. Vaya a Security & Compliance Center > **Security policies** > **Device security policies (Directivas de seguridad del dispositivo**). Seleccione el nombre de la directiva de dispositivo y, a continuación, seleccione **Editar** > **requisitos de acceso**. Seleccione **Permitir infracción de acceso e informe**.<br/>- Para desbloquear un dispositivo no compatible o no compatible para un usuario o un grupo de usuarios, vaya al Centro de cumplimiento de Seguridad & > **Directivas** >  de seguridad **Administración de** >  dispositivos **Administrar la configuración de acceso** a dispositivos. Agregue un grupo de seguridad con los miembros que desea excluir para que no se bloquee el acceso a Microsoft 365. Para obtener más información, consulte [Creación, edición o eliminación de un grupo de seguridad en el Centro de administración de Microsoft 365](../../admin/email/create-edit-or-delete-a-security-group.md).|
|Eliminación de usuarios para que sus dispositivos ya no estén administrados por Basic Mobility and Security|Para quitar el usuario, edite el grupo de seguridad que tiene directivas de administración de dispositivos para Basic Mobility and Security. Para obtener más información, consulte [Creación, edición o eliminación de un grupo de seguridad en el Centro de administración de Microsoft 365](../../admin/email/create-edit-or-delete-a-security-group.md).<br/>Para quitar la movilidad y la seguridad básicas de todos los usuarios de Microsoft 365, consulte [Desactivar la movilidad y la seguridad básicas](turn-off.md).|

Live (v14)
