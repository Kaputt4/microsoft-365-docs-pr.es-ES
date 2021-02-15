---
title: Administrar dispositivos inscritos en administración de dispositivos móviles en Microsoft 365
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
ms.openlocfilehash: 4954da0ff44276d9bd46cabc78bc52c7879e5e26
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876965"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Administrar dispositivos inscritos en administración de dispositivos móviles en Microsoft 365

La administración de dispositivos móviles integrada para Microsoft 365 le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhone, iPad, Android y teléfonos Windows. El primer paso es iniciar sesión en Microsoft 365 y configurar la movilidad y seguridad básicas. Para obtener más información, consulta [Configurar movilidad y seguridad básicas.](set-up.md)

Después de configurarlo, las personas de la organización deben inscribir sus dispositivos en el servicio. Para obtener más información, consulta [Inscribir el dispositivo móvil con movilidad y seguridad básicas.](enroll-your-mobile-device.md)A continuación, puedes usar movilidad básica y seguridad para ayudar a administrar los dispositivos de la organización. Por ejemplo, puede usar directivas de seguridad de dispositivos para ayudar a limitar el acceso al correo electrónico u otros servicios, ver informes de dispositivos y borrar de forma remota un dispositivo. Normalmente, irá al Centro de seguridad y & cumplimiento para realizar estas tareas. Para obtener más información, vea [el Centro de cumplimiento de Microsoft 365.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Para ir al panel de administración de dispositivos, sigue estos pasos:

1. Vaya al Centro [de administración de Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Escriba Administración de dispositivos móviles en el campo de búsqueda y seleccione **Administración de dispositivos móviles** en la lista de   resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opción de administración de dispositivos móviles":::

3. Seleccione  **Empecemos.**

## <a name="manage-mobile-devices"></a>Administrar dispositivos móviles

Una vez que haya configurado la movilidad y la seguridad básicas, puede administrar los dispositivos móviles de su organización de algunas maneras.

|**Para**|**Haga esto…**|
|:----------------|:------------------------------------------------------------------------------|
|Eliminar los datos de un dispositivo |En el Panel de administración de  **** dispositivos, selecciona el nombre del dispositivo *y,* a continuación, eliminación completa para eliminar toda la información o la eliminación selectiva para eliminar solo la información de   la organización en el  ****   dispositivo. Para obtener más información, [consulta Borrar un dispositivo móvil en Movilidad y seguridad básicas.](wipe-mobile-device.md)|
|Bloquear el acceso de dispositivos no compatibles al correo electrónico de Exchange con Exchange ActiveSync |En el panel Administración de dispositivos, seleccione  **Bloquear**. |
|Configurar directivas de dispositivo, como los requisitos de contraseña y la configuración de seguridad |En el panel Administración de dispositivos, selecciona **Directivas de seguridad de**   >  **dispositivos Agregar +**. Para obtener más información, consulta [Crear directivas de seguridad de dispositivos en Movilidad y seguridad básicas.](create-device-security-policies.md)|
|Ver la lista de dispositivos bloqueados  |En el panel Administración de dispositivos, en  **Seleccionar una vista,**   seleccione  **Bloqueado.** |
|Desbloquear un dispositivo no compatible o no admitido para un usuario o grupo de usuarios  |Elige una de las siguientes opciones para desbloquear dispositivos:<br/>- Quite el usuario o los usuarios del grupo de seguridad al que se ha aplicado la directiva. Vaya al Centro de administración de Microsoft 365 > **grupos** y, a continuación, seleccione el nombre del grupo. Seleccione **Editar miembros y administradores.**<br/>- Quita el grupo de seguridad del que son miembros los usuarios de la directiva de dispositivo. Go to Security & Compliance Center > **Security policies** Device   >  **security policies**. Seleccione el nombre de la directiva de dispositivo y, a **continuación, seleccione Editar**  >  **implementación.**<br/>- Desbloquear todos los dispositivos no compatibles para una directiva de dispositivo. Go to Security & Compliance Center > **Security policies** Device   >  **security policies**. Seleccione el nombre de la directiva de dispositivo y, a continuación, **seleccione Editar**  >  **requisitos de acceso.** Seleccione  **Permitir acceso e informar de la infracción.**<br/>- Para desbloquear un dispositivo no compatible o no compatible para un usuario o un grupo de usuarios, vaya al Centro de seguridad & Cumplimiento >Directivas de seguridad Administración de dispositivos Administrar la configuración de acceso de  ****   >  ****   >  **** dispositivos. Agregue un grupo de seguridad con los miembros que desea excluir de que se bloquee el acceso a Microsoft 365. Para obtener más información, vea Crear, editar o eliminar un grupo de [seguridad en el Centro de administración de Microsoft 365.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)|
|Quitar usuarios para que sus dispositivos ya no sean administrados por movilidad y seguridad básicas |Para quitar el usuario, edite el grupo de seguridad que tiene directivas de administración de dispositivos para movilidad y seguridad básicas. Para obtener más información, vea Crear, editar o eliminar un grupo de  [seguridad en el Centro de administración de Microsoft 365.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)<br/>Para quitar la movilidad básica y la seguridad de todos los usuarios de Microsoft 365, vea Desactivar movilidad [y seguridad básicas.](turn-off.md)|

Live (v14)