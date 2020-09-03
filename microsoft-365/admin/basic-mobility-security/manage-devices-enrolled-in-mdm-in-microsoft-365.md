---
title: Administrar dispositivos inscritos en la administración de dispositivos móviles en Microsoft 365
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
description: La movilidad y la seguridad básica pueden ayudarle a proteger y administrar dispositivos móviles.
ms.openlocfilehash: 36ea0d12becca2e97a56aceea107fa1f5bf6ded4
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337089"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Administrar dispositivos inscritos en la administración de dispositivos móviles en Microsoft 365

La administración integrada de dispositivos móviles para Microsoft 365 ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhone, iPad, Android y Windows Phone. El primer paso es iniciar sesión en Microsoft 365 y configurar la movilidad y la seguridad básicas. Para obtener más información, consulte [set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).

Una vez configurada, los usuarios de la organización deben inscribir sus dispositivos en el servicio. Para obtener más información, vea [inscribir un dispositivo móvil con la seguridad y la movilidad básicos](enroll-your-mobile-device-using-basic-mobility-and-security.md).A continuación, puede usar la movilidad básica y la seguridad para ayudar a administrar los dispositivos de su organización. Por ejemplo, puede usar directivas de seguridad de dispositivo para ayudar a limitar el acceso al correo electrónico u otros servicios, ver informes de dispositivos y borrar de forma remota un dispositivo. Normalmente, va al centro de seguridad & cumplimiento para realizar estas tareas. Para obtener más información, consulte [Microsoft 365 Compliance Center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Para ir al panel de administración de dispositivos, siga estos pasos:

1. Vaya al [centro de administración de Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Escriba administración de dispositivos móviles en el campo de búsqueda y seleccione **Administración de dispositivos móviles**   en la lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opción de administración de dispositivos móviles":::

3. Seleccione  **administrar dispositivos**.

## <a name="manage-mobile-devices"></a>Administrar dispositivos móviles
    
Una vez configurada la configuración de movilidad y seguridad básica, estas son algunas formas en las que puede administrar los dispositivos móviles de su organización.

|**Para**|**Haga esto…**|
|:----------------|:------------------------------------------------------------------------------|
|Eliminar los datos de un dispositivo |En el panel de administración de dispositivos, seleccione *nombre de dispositivo*y, a continuación,  **borrado completo**   para eliminar toda la información o  **borrado selectivo**   para eliminar solo la información de la organización en el dispositivo. Para obtener más información, consulte [borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).|
|Bloquear el acceso de dispositivos no compatibles al correo electrónico de Exchange con Exchange ActiveSync |En el panel de administración de dispositivos, seleccione  **bloquear**. |
|Configurar directivas de dispositivo, como la configuración de seguridad y los requisitos de contraseña |En el panel de administración de dispositivos, seleccione **directivas de seguridad de dispositivos**   >  **Add +**. Para obtener más información, vea [crear directivas de seguridad de dispositivos en Basic Mobility and Security](create-device-security-policies-in-basic-mmobility-and-security.md).|
|Ver la lista de dispositivos bloqueados  |En el panel de administración de dispositivos, en  **seleccionar una vista** ,   Seleccione  **bloqueado**. |
|Desbloquear un dispositivo no compatible o no admitido para un usuario o grupo de usuarios  |Seleccione una de las siguientes opciones para desbloquear dispositivos:<br/>-Quite el usuario o los usuarios del grupo de seguridad al que se ha aplicado la Directiva. Vaya a Microsoft 365 administración del centro de administración > **grupos**y, a continuación, seleccione nombre del grupo. Seleccione **Editar miembros y administradores**.<br/>-Quite el grupo de seguridad al que pertenecen los usuarios de la Directiva de dispositivo. Vaya al centro de cumplimiento & de  **seguridad >directivas**de seguridad de dispositivos de seguridad   >  **Device security policies**. Seleccione nombre de la Directiva de dispositivo y, después, seleccione **Editar**  >  **implementación**.<br/>-Desbloquea todos los dispositivos no conformes para una directiva de dispositivo. Vaya al centro de cumplimiento & de  **seguridad >directivas**de seguridad de dispositivos de seguridad   >  **Device security policies**. Seleccione nombre de la Directiva de dispositivo y, a continuación, seleccione **Editar**  >  **requisitos de acceso**. Seleccione  **permitir acceso e informar de infracción**.<br/>-Para desbloquear un dispositivo no compatible o no compatible para un usuario o un grupo de usuarios, vaya al centro de cumplimiento de & de seguridad > **directivas de seguridad**   >  **Administración de dispositivos**   >  **administrar la configuración de acceso al dispositivo**. Agregue un grupo de seguridad con los miembros que desea excluir del bloqueo de acceso a Microsoft 365. Para obtener más información, vea [crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).|
|Obtener información sobre los dispositivos de la organización  |Para obtener más información, como los dispositivos que están inscritos y las directivas de seguridad de dispositivos, consulte [Get details Basic Mobility and Security Managed](get-details-about-basic-mobility-and-security-managed-devices.md)Devices.|
|Quitar usuarios para que sus dispositivos ya no estén administrados por la movilidad y la seguridad básicas |Para quitar al usuario, edite el grupo de seguridad que tiene las directivas de administración de dispositivos para la movilidad y la seguridad básicas. Para obtener más información, vea  [crear, editar o eliminar un grupo de seguridad en el centro de administración de Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).<br/>Para quitar la movilidad y la seguridad básicas de todos los usuarios de Microsoft 365, consulte [desactivar la movilidad y la seguridad básicas](turn-off-basic-mobility-and-security.md).|

Activo (V14)