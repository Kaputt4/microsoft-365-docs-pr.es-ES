---
title: Preguntas más frecuentes sobre movilidad básica y seguridad (FAQ)
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
description: Preguntas más frecuentes sobre movilidad básica y seguridad.
ms.openlocfilehash: a538c0b3f9fa6a4bf1861734fc9dea94030760a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906269"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Preguntas más frecuentes sobre movilidad básica y seguridad (FAQ)

Este artículo contiene preguntas más frecuentes sobre Movilidad básica y seguridad, una característica que le ayuda a administrar y proteger dispositivos móviles en Microsoft 365. Si no encuentra una respuesta a su pregunta, háganoslo saber dejando un comentario en la página para que podamos considerar agregar su pregunta a este artículo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>¿Cómo puedo obtener movilidad y seguridad básicas? No lo veo en el Centro de administración de Microsoft 365

1.  Para activar la movilidad y la seguridad básicas, vaya a la página Seguridad de [Office 365 & cumplimiento](https://protection.office.com/) normativo.

2.  Vaya a Prevención de pérdida de datos > Administración de dispositivos.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>¿Cómo puedo empezar con la administración de dispositivos en Movilidad y seguridad básicas?

Hay cuatro pasos para empezar con movilidad y seguridad básicas: 

1. Para activar la movilidad y la seguridad básicas, vaya a La seguridad de [Office 365 & cumplimiento](https://protection.office.com/).

2. Ve a Prevención de pérdida de datos > Administración de dispositivos > directivas de dispositivo.
    
3. Crear directivas de administración de dispositivos y aplicarlas a grupos de usuarios configurados en grupos de seguridad. Le recomendamos que empiece implementando las directivas en un grupo de prueba pequeño. Para obtener más información, consulta [Crear directivas de seguridad de dispositivos en Basic Mobility and Security](create-device-security-policies.md).

4. A los usuarios a los que se les ha aplicado una directiva se les pide que inscriban sus dispositivos cuando intenten obtener acceso a los datos de Microsoft 365. Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas.](enroll-your-mobile-device.md)

Para obtener más información, vea [Set up Basic Mobility and Security](set-up.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Estoy intentando configurar la movilidad básica y la seguridad, pero parece que está atascado. El estado del servicio de Microsoft 365 ha estado mostrando "aprovisionamiento" durante un tiempo. ¿Qué puedo hacer?

El servicio puede tardar algún tiempo en prepararse para usted. Cuando se complete el aprovisionamiento, verá la página Movilidad y seguridad básicas. Si ha esperado 24 horas y el estado sigue aprovisionamiento, póngase en contacto con el soporte técnico y le ayudaremos a averiguar cuál es el problema. Para obtener opciones de soporte técnico, [vea ¿Todavía necesita ayuda?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp).

## <a name="what-can-i-do-if-device-enrollment-fails"></a>¿Qué puedo hacer si se produce un error en la inscripción de dispositivos?

Si tienes problemas para inscribir un dispositivo, comprueba primero lo siguiente:

- Asegúrese de que el dispositivo aún no está inscrito en otro proveedor de administración de dispositivos móviles, como Intune.

- Asegúrate de que el dispositivo esté establecido en la fecha y hora correctas.

- Cambie a una red WIFI o móvil diferente en el dispositivo.

- Para dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación Portal de empresa de Intune en el dispositivo.
    
Si la inscripción aún no funciona, consulte [Troubleshoot Basic Mobility and Security](troubleshoot.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>¿Cuál es la diferencia entre Intune y movilidad básica y seguridad?

La movilidad y la seguridad básicas se hospedan en el servicio de Intune. Es un subconjunto de servicios de Intune proporcionados como una ventaja adicional para Microsoft 365 y es una solución integrada basada en la nube para administrar dispositivos de su organización. Para obtener una comparación en paralelo de los dos servicios que le ayudarán a decidir si usar Intune o Basic Mobility and Security for Microsoft 365 es lo más adecuado para usted, consulte [Choose between Basic Mobility Security e Intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>¿Cómo funcionan las directivas para movilidad y seguridad básicas? ¿Cómo los puedo configurar? ¿Deshabilitarlos?

Después de completar la configuración inicial de Movilidad y seguridad básicas, se crean directivas y se aplican a grupos de usuarios en el Centro de seguridad & cumplimiento. Las directivas requieren que los usuarios de las directivas inscriban sus dispositivos en Movilidad y seguridad básicas antes de poder usar el dispositivo para obtener acceso a los datos de Microsoft 365. Las directivas configuradas determinan la configuración de dispositivos móviles, por ejemplo, la frecuencia con la que se deben restablecer las contraseñas o si se requiere cifrado de datos. Para obtener más información, vea [Create device security policies in Basic Mobility and Security](create-device-security-policies.md)y Microsoft   [365 compliance center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

Para obtener instrucciones paso a paso para crear e implementar directivas de dispositivos, consulte [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).

Si desea excluir un grupo específico de usuarios de verse afectados por directivas, puede agregar un grupo al grupo de exclusión.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>¿Puedo cambiar de Exchange ActiveSync de dispositivos a Movilidad y seguridad básicas para Microsoft 365?

Si ya estás usando directivas de Exchange ActiveSync para administrar dispositivos móviles, puedes empezar a usar La movilidad y la seguridad básicas siguiendo los pasos para configurar la movilidad y la seguridad básicas. Para obtener más información, vea [Protect user and device access](../../compliance/protect-access-to-data-and-services.md) y Set up Basic Mobility and [Security](set-up.md).

Al aplicar las directivas que cree en Movilidad básica y seguridad a grupos de usuarios, estas directivas invalidan Exchange ActiveSync las directivas de buzón de dispositivo móvil y las reglas de acceso de dispositivos que haya creado anteriormente en el Centro de administración de Exchange para esos usuarios.

Una vez que un dispositivo se inscribe en Movilidad y seguridad básicas, se omite cualquier Exchange ActiveSync directiva de buzón de dispositivo móvil o regla de acceso de dispositivo aplicada al dispositivo.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>He configurado La movilidad y la seguridad básicas, pero ahora quiero quitarla. ¿Cuáles son los pasos?

Desafortunadamente, no puedes simplemente "desaprovisionar" La movilidad y la seguridad básicas después de configurarla. Pero puedes quitarlo para grupos de usuarios quitando los grupos de seguridad de usuario de las directivas de dispositivo que hayas creado. O bien, puedes deshabilitarlo para todos quitando las directivas de dispositivo para que no se apliquen y no se cumplan. Para obtener más información, consulta [Desactivar movilidad básica y seguridad.](turn-off.md)