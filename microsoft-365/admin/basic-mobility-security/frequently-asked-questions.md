---
title: Preguntas más frecuentes sobre la movilidad y la seguridad básicas (FAQ)
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
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
description: Preguntas más frecuentes acerca de la movilidad y la seguridad básicas.
ms.openlocfilehash: e05815392510ad54bb530457d7f0f6490ece4a95
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430308"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Preguntas más frecuentes sobre la movilidad y la seguridad básicas (FAQ)

Este artículo contiene las preguntas más frecuentes acerca de la movilidad y la seguridad básicas, una característica que le ayuda a administrar y proteger los dispositivos móviles en Microsoft 365. Si no encuentra una respuesta a su pregunta, háganoslo saber dejando un Comentario en la página para que podamos considerar la adición de su pregunta a este artículo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>¿Cómo puedo obtener movilidad y seguridad básicas? No lo veo en el centro de administración de 365 de Microsoft

1.  Para activar la movilidad y la seguridad básicas, vaya a la página [Office 365 Security & Compliance](https://protection.office.com/) .   

2.  Vaya a prevención de pérdida de datos > de administración de dispositivos.   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>¿Cómo puedo empezar con la administración de dispositivos en la movilidad y la seguridad básicas?

Hay cuatro pasos para empezar a trabajar con la movilidad y la seguridad básicas: 

1. Para activar la movilidad y la seguridad básicas, vaya a [Office 365 security & Compliance](https://protection.office.com/).
    
2. Vaya a prevención de pérdida de datos > de administración de dispositivos > directivas de dispositivos.
    
3. Crear directivas de administración de dispositivos y aplicarlas a grupos de usuarios que se configuran en grupos de seguridad. Se recomienda comenzar con la implementación de las directivas en un pequeño grupo de prueba. Para obtener más información, vea [crear directivas de seguridad de dispositivos en Basic Mobility and Security](create-device-security-policies.md).      

4. Los usuarios a los que se les haya aplicado una directiva se les pedirán que inscriban sus dispositivos cuando intenten acceder a datos de Microsoft 365. Para obtener más información, vea [inscribir un dispositivo móvil con la seguridad y la movilidad básicos](enroll-your-mobile-device.md).

Para obtener más información, consulte [set up Basic Mobility and Security](set-up.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Estoy intentando configurar la movilidad y la seguridad básica, pero parece que está atascado. El estado del servicio de Microsoft 365 se ha mostrado "aprovisionamiento" durante un tiempo. ¿Qué puedo hacer?

Puede tardar algún tiempo en preparar el servicio para usted. Cuando se complete el aprovisionamiento, verá la página Administración de dispositivos móviles para Microsoft 365. Si ha esperado 24 horas y el estado todavía es aprovisionamiento, póngase en contacto con el soporte técnico y le ayudaremos a determinar qué es el problema. Para obtener información sobre las opciones de soporte técnico, consulte ¿ [necesita ayuda?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>¿Qué puedo hacer si se produce un error en la inscripción del dispositivo?

Si tiene problemas para obtener un dispositivo inscrito, compruebe primero lo siguiente:

- Asegúrese de que el dispositivo ya no está inscrito con otro proveedor de administración de dispositivos móviles, como Intune.
    
- Asegúrese de que el dispositivo está configurado con la fecha y hora correctas.
    
- Cambia a otra red de telefonía móvil o Wi-Fi en el dispositivo.
    
- Para dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación del portal de empresa de Intune en el dispositivo.
    
Si la inscripción sigue sin funcionar, consulte [troubleshoot Basic Mobility and Security](troubleshoot.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>¿Cuál es la diferencia entre Intune y la movilidad y la seguridad básicas?

El servicio de Intune hospeda la movilidad y la seguridad básica. Es un subconjunto de servicios de Intune proporcionado como beneficio adicional para Microsoft 365 y es una solución basada en la nube integrada para administrar los dispositivos de su organización. Para realizar una comparación en paralelo de los dos servicios a fin de ayudarle a decidir si el uso de Intune o de la movilidad y seguridad básicas de Microsoft 365 es la mejor opción para usted, vea [Choose between Basic Mobility Security and Intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>¿Cómo funcionan las directivas para la movilidad y la seguridad básicas? ¿Cómo se configura? ¿Las deshabilita?

Una vez completada la configuración inicial de la movilidad y la seguridad básicas, puede crear directivas y aplicarlas a grupos de usuarios en el centro de seguridad & cumplimiento. Las directivas requieren que los usuarios de las directivas inscriban sus dispositivos en Basic Mobility and Security antes de que se pueda usar el dispositivo para obtener acceso a los datos de Microsoft 365. Las directivas que se configuran determinan la configuración para dispositivos móviles, por ejemplo, la frecuencia con la que se deben restablecer las contraseñas o si se requiere cifrado de datos. Para obtener más información, vea [Create Device Security policies in Basic Mobility and Security](create-device-security-policies.md)   y [Microsoft 365 Compliance Center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

Para obtener instrucciones paso a paso para crear e implementar directivas de dispositivo, consulte [Create Device Security policies in Basic Mobility and Security](create-device-security-policies.md).

Si desea excluir a un grupo específico de usuarios de las directivas que se ven afectados, puede Agregar un grupo al grupo de exclusión.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>¿Puedo cambiar de la administración de dispositivos de Exchange ActiveSync a la movilidad y la seguridad básicas de Microsoft 365?

Si ya está usando directivas de Exchange ActiveSync para administrar dispositivos móviles, puede empezar a usar la movilidad y la seguridad básicas siguiendo los pasos para configurar la movilidad y la seguridad básicas. Para obtener más información, consulte proteger el acceso de los [usuarios y los dispositivos](https://go.microsoft.com/fwlink/?LinkId=615145) y [configurar la movilidad y la seguridad básicas](set-up.md).

Cuando se aplican las directivas que se crean en la movilidad básica y la seguridad a los grupos de usuarios, estas directivas invalidan las directivas de buzón de dispositivo móvil de Exchange ActiveSync y las reglas de acceso de dispositivo que haya creado previamente en el centro de administración de Exchange para esos usuarios.

Una vez inscrito un dispositivo en la movilidad y la seguridad básica, se ignora cualquier directiva de buzón de dispositivo móvil de Exchange ActiveSync o regla de acceso de dispositivo aplicada al dispositivo.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Configuré la movilidad y la seguridad básicas, pero ahora quiero quitarla. ¿Cuáles son los pasos?

Desafortunadamente, no se puede simplemente "desaprovisionar" la movilidad y la seguridad básicas una vez que se ha configurado. Pero puede quitarla para grupos de usuarios quitando grupos de seguridad de usuarios de las directivas de dispositivo que ha creado. O bien, puede deshabilitarla para todos los usuarios si quita las directivas de dispositivo para que no estén en su ubicación y no se apliquen. Para obtener más información, vea [desactivar la movilidad y la seguridad básicas](turn-off.md).

