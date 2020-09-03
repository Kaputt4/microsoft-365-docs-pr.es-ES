---
title: Información general sobre la movilidad y la seguridad básicas de Microsoft 365
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
description: Use la movilidad y la seguridad básicas para establecer directivas de seguridad de dispositivos y reglas de acceso.
ms.openlocfilehash: 7c1a4bc5ddf476463788f99305215ee6853190f1
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337082"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Información general sobre la movilidad y la seguridad básicas de Microsoft 365

Puede administrar y proteger los dispositivos móviles cuando están conectados a su organización de Microsoft 365 mediante la movilidad y la seguridad básicas. Los dispositivos móviles, como los smartphones y las tabletas, que se usan para tener acceso a elementos de trabajo como el correo electrónico, el calendario, los contactos y los documentos, desempeñan un papel muy importante a la hora de garantizar que los empleados puedan realizar su trabajo en cualquier momento y en cualquier lugar. Por lo tanto, es fundamental que ayude a proteger la información de su organización cuando los usuarios usan dispositivos. Puede usar la movilidad y la seguridad básicas para establecer las directivas de seguridad de los dispositivos y las reglas de acceso, así como para borrar los dispositivos móviles si se pierden o son robados.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuración básica de movilidad y seguridad":::

## <a name="what-types-of-devices-can-you-manage"></a>¿Qué tipos de dispositivos se pueden administrar?

Puede usar la movilidad y la seguridad básicas para administrar muchos tipos de dispositivos móviles, como Windows Phone, Android, iPhone y iPad. Para administrar los dispositivos móviles que usan las personas de la organización, cada persona debe tener una licencia de Microsoft 365 aplicable y su dispositivo debe estar inscrito en la movilidad y la seguridad básicas.

Para ver qué es compatible con la movilidad y la seguridad básicas para cada tipo de dispositivo, consulte [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Pasos de configuración para la movilidad y la seguridad básicas

Un administrador global de Microsoft 365 debe completar los pasos siguientes para activar y configurar la movilidad y la seguridad básicas. Para conocer los pasos detallados, siga las instrucciones de [set up Basic Mobility and Security](set-up-basic-mobility-and-security.md). 

Este es un resumen de los pasos:

**Paso 1:** Para activar la movilidad y la seguridad básicas, siga los pasos descritos en [set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).

**Paso 2:** Configure la movilidad y la seguridad básicas; por ejemplo, cree un certificado APN para administrar dispositivos iOS y agregar un registro de sistema de nombres de dominio (DNS) para su dominio para que admita Windows Phone.

**Paso 3:** Crear directivas de dispositivo y aplicarlas a grupos de usuarios. Al hacerlo, los usuarios reciben un mensaje de inscripción en su dispositivo y, cuando hayan completado la inscripción, sus dispositivos estarán restringidos por las directivas que haya configurado para ellos. Para obtener más información, vea [inscribir un dispositivo móvil con la seguridad y la movilidad básicos](enroll-your-mobile-device-using-basic-mobility-and-security.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración básica de la Directiva de seguridad y movilidad":::

## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Una vez que tenga una configuración básica de movilidad y seguridad y que los usuarios hayan inscrito sus dispositivos, puede administrar los dispositivos, bloquear el acceso o borrar un dispositivo, si es necesario. Para obtener más información sobre algunas de las tareas de administración de dispositivos comunes, como dónde completar las tareas, vea [administrar dispositivos inscritos en administración de dispositivos móviles para Microsoft 365](manage-devices-enrolled-in-mdm-in-microsoft-365.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Otras formas de administrar dispositivos y aplicaciones

Si solo necesita la administración de aplicaciones móviles (MAM), quizás para las personas que actualicen proyectos de trabajo en sus propios dispositivos, Intune ofrece otra opción además de inscribir y administrar dispositivos. Una suscripción de Intune le permite configurar directivas de MAM mediante el portal de Azure, incluso si los dispositivos de los usuarios no están inscritos en Intune. Para obtener más información, vea [directivas de protección de aplicaciones](https://go.microsoft.com/fwlink/?LinkId=2132517).

## <a name="related-topics"></a>Temas relacionados

[Configurar la Seguridad de Movilidad Básica](set-up-basic-mobility-and-security.md)

[Inscribir el dispositivo móvil con la seguridad y la movilidad básicas](enroll-your-mobile-device-using-basic-mobility-and-security.md)

[Administrar dispositivos inscritos en la administración de dispositivos móviles para Microsoft 365](manage-devices-enrolled-in-mdm-in-microsoft-365.md)

[Obtener información sobre los dispositivos administrados por la seguridad y la movilidad básicos](get-details-about-basic-mobility-and-security-managed-devices.md)