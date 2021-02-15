---
title: Preguntas más frecuentes sobre movilidad y seguridad básicas (P+F)
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
description: Preguntas más frecuentes sobre movilidad y seguridad básicas.
ms.openlocfilehash: 5651b9f9742c45f1229e55b298cf78532c835c9a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876881"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Preguntas más frecuentes sobre movilidad y seguridad básicas (P+F)

Este artículo contiene las preguntas más frecuentes sobre movilidad y seguridad básicas, una característica que le ayuda a administrar y proteger dispositivos móviles en Microsoft 365. Si no encuentra una respuesta a su pregunta, háganoslo saber dejando un comentario en la página para que podamos considerar agregar su pregunta a este artículo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>¿Cómo puedo obtener la movilidad y la seguridad básicas? No lo veo en el Centro de administración de Microsoft 365

1.  Active la movilidad básica y la seguridad yendo a la página Seguridad y [& cumplimiento de Office 365.](https://protection.office.com/)

2.  Ve a Prevención de pérdida de datos > administración de dispositivos.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>¿Cómo puedo empezar a usar la administración de dispositivos en movilidad y seguridad básicas?

Hay cuatro pasos para empezar a trabajar con movilidad y seguridad básicas: 

1. Active la movilidad y la seguridad básicas yendo a La seguridad [de Office 365 & cumplimiento.](https://protection.office.com/)

2. Ve a Prevención de pérdida de datos > administración de dispositivos > directivas de dispositivo.
    
3. Crear directivas de administración de dispositivos y aplicarlas a grupos de usuarios configurados en grupos de seguridad. Le recomendamos que empiece implementando las directivas en un pequeño grupo de prueba. Para obtener más información, consulta [Crear directivas de seguridad de dispositivos en Movilidad y seguridad básicas.](create-device-security-policies.md)

4. A los usuarios a los que se les ha aplicado una directiva se les pide que inscriban sus dispositivos cuando intenten acceder a los datos de Microsoft 365. Para obtener más información, consulta [Inscribir el dispositivo móvil con movilidad y seguridad básicas.](enroll-your-mobile-device.md)

Para obtener más información, vea [Configurar movilidad y seguridad básicas.](set-up.md)

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Estoy intentando configurar la movilidad y la seguridad básicas, pero parece que está bloqueado. El Estado del servicio de Microsoft 365 ha estado mostrando "aprovisionamiento" durante un tiempo. ¿Qué puedo hacer?

El servicio puede tardar algún tiempo en prepararse para usted. Cuando se complete el aprovisionamiento, verá la página Movilidad y seguridad básica. Si ha esperado 24 horas y el estado sigue aprovisionamiento, póngase en contacto con el soporte técnico y le ayudaremos a averiguar cuál es el problema. Para obtener opciones de soporte técnico, [consulte ¿Aún necesita ayuda?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp).

## <a name="what-can-i-do-if-device-enrollment-fails"></a>¿Qué puedo hacer si se produce un error en la inscripción de dispositivos?

Si tienes problemas para inscribir un dispositivo, comprueba primero lo siguiente:

- Asegúrate de que el dispositivo aún no esté inscrito en otro proveedor de administración de dispositivos móviles, como Intune.

- Asegúrate de que el dispositivo está establecido en la fecha y hora correctas.

- Cambia a otra red WIFI o de telefonía móvil en el dispositivo.

- Para dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación Portal de empresa de Intune en el dispositivo.
    
Si la inscripción sigue sin funcionar, consulte Solucionar problemas [de movilidad y seguridad básicas.](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>¿Cuál es la diferencia entre Intune y movilidad y seguridad básicas?

La movilidad y la seguridad básicas se hospedan en el servicio de Intune. Es un subconjunto de servicios de Intune proporcionados como una ventaja adicional para Microsoft 365 y es una solución integrada basada en la nube para administrar dispositivos en su organización. Para obtener una comparación en paralelo de los dos servicios para ayudarle a decidir si el uso de Intune o Movilidad y seguridad básica para Microsoft 365 es la mejor opción para usted, vea Elegir entre Seguridad de movilidad básica e [Intune.](choose-between-basic-mobility-and-security-and-intune.md)

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>¿Cómo funcionan las directivas para movilidad y seguridad básicas? ¿Cómo puedo configurarlos? ¿Deshabilitarlos?

Una vez completada la configuración inicial de Movilidad y seguridad básicas, se crean directivas y se aplican a grupos de usuarios en el Centro de seguridad & cumplimiento. Las directivas requieren que los usuarios de las directivas inscriban sus dispositivos en movilidad básica y seguridad antes de que el dispositivo pueda usarse para acceder a los datos de Microsoft 365. Las directivas que configure determinan la configuración de los dispositivos móviles, por ejemplo, la frecuencia con la que se deben restablecer las contraseñas o si se requiere cifrado de datos. Para obtener más información, vea [Crear directivas de seguridad de dispositivos en movilidad](create-device-security-policies.md)y seguridad básicas y centro de cumplimiento de Microsoft   [365.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

Para obtener instrucciones paso a paso para crear e implementar directivas de dispositivo, consulta Crear directivas de seguridad de dispositivos [en Movilidad y Seguridad básicas.](create-device-security-policies.md)

Si desea excluir un grupo específico de usuarios de que no se ven afectados por las directivas, puede agregar un grupo al grupo de exclusión.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>¿Puedo cambiar de Exchange ActiveSync de dispositivos a Movilidad y seguridad básicas para Microsoft 365?

Si ya usa directivas de Exchange ActiveSync para administrar dispositivos móviles, puede empezar a usar Movilidad y seguridad básica siguiendo los pasos para configurar la movilidad y la seguridad básicas. Para obtener más información, vea Proteger el acceso de usuarios [y dispositivos](https://go.microsoft.com/fwlink/?LinkId=615145) [y Configurar movilidad y seguridad básicas.](set-up.md)

Al aplicar las directivas que cree en Movilidad y seguridad básicas Exchange ActiveSync grupos de usuarios, estas directivas invalidan Exchange ActiveSync las directivas de buzón de dispositivo móvil y las reglas de acceso de dispositivo que haya creado anteriormente en el Centro de administración de Exchange para esos usuarios.

Después de inscribir un dispositivo en movilidad y seguridad básicas, se omiten todas Exchange ActiveSync directiva de buzón de dispositivo móvil o regla de acceso de dispositivo aplicada al dispositivo.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>He configurado la movilidad y la seguridad básicas, pero ahora quiero quitarla. ¿Cuáles son los pasos?

Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up. Pero puedes quitarla para grupos de usuarios quitando grupos de seguridad de usuario de las directivas de dispositivo que hayas creado. O bien, puedes deshabilitarla para todos los usuarios quitando las directivas de dispositivo para que no se apliquen y no se apliquen. Para obtener más información, consulta [Desactivar movilidad y seguridad básicas.](turn-off.md)