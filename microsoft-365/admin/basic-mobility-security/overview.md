---
title: Información general sobre la movilidad y la seguridad básicas para Microsoft 365
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
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: Administre y proteja los dispositivos móviles conectados a su organización de Microsoft 365 mediante la configuración y el uso de Basic Mobility and Security.
ms.openlocfilehash: 7cac3397cddbfed970c8bdf8ef5128458c8fcd5c
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68190493"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Información general sobre la movilidad y la seguridad básicas para Microsoft 365

Puede administrar y proteger dispositivos móviles cuando estén conectados a su organización de Microsoft 365 mediante Basic Mobility and Security. Los dispositivos móviles como teléfonos inteligentes y tabletas que se usan para acceder al correo electrónico del trabajo, el calendario, los contactos y los documentos desempeñan un papel importante en asegurarse de que los empleados realizan su trabajo en cualquier momento, desde cualquier lugar. Por lo tanto, es fundamental que ayude a proteger la información de su organización cuando los usuarios usan dispositivos. Puede usar Basic Mobility and Security para establecer directivas de seguridad de dispositivos y reglas de acceso, y para borrar los dispositivos móviles si se pierden o se roban.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuración básica de movilidad y seguridad.":::

## <a name="what-types-of-devices-can-you-manage"></a>¿Qué tipos de dispositivos se pueden administrar?

Puede usar Basic Mobility and Security para administrar muchos tipos de dispositivos móviles, como Android, iPhone y iPad. Para administrar los dispositivos móviles que usan los usuarios de su organización, cada persona debe tener una licencia de Microsoft 365 aplicable y su dispositivo debe inscribirse en Basic Mobility and Security.

Para ver qué admite Basic Mobility and Security para cada tipo de dispositivo, consulte [Funcionalidades de movilidad y seguridad básicas](capabilities.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Pasos de configuración para la movilidad y la seguridad básicas

Un administrador global de Microsoft 365 debe completar los pasos siguientes para activar y configurar Basic Mobility and Security. Para obtener pasos detallados, siga las instrucciones que se indican en [Configuración de la movilidad y la seguridad básicas](set-up.md). 

Este es un resumen de los pasos:

**Paso 1:** Active Basic Mobility and Security siguiendo los pasos descritos en [Configuración de Basic Mobility and Security](set-up.md).

**Paso 2:** Configure Basic Mobility and Security mediante, por ejemplo, la creación de un certificado APNs para administrar dispositivos iOS y la adición de un registro del sistema de nombres de dominio (DNS) para el dominio.

**Paso 3:** Cree directivas de dispositivo y aplíquelas a grupos de usuarios. Al hacerlo, los usuarios reciben un mensaje de inscripción en su dispositivo y, cuando han completado la inscripción, sus dispositivos están restringidos por las directivas que ha configurado para ellos. Para obtener más información, consulta [Inscribir tu dispositivo móvil con Basic Mobility and Security](enroll-your-mobile-device.md). 

:::image type="content" source="../../media/basic-mobility-security/basic-mobility-microsoft-purview.png" alt-text="Configuración básica de la directiva de seguridad y movilidad.":::

## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Después de configurar Basic Mobility and Security y de que los usuarios hayan inscrito sus dispositivos, puede administrar los dispositivos, bloquear el acceso o borrar un dispositivo, si es necesario. Para obtener más información sobre algunas tareas comunes de administración de dispositivos, como dónde completar las tareas, consulte [Administración de dispositivos inscritos en Mobile Administración de dispositivos para Microsoft 365](manage-enrolled-devices.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Otras formas de administrar dispositivos y aplicaciones

Si solo necesita administración de aplicaciones móviles (MAM), quizás para personas que actualizan proyectos de trabajo en sus propios dispositivos, Intune proporciona otra opción además de inscribir y administrar dispositivos. Una suscripción Intune le permite configurar directivas MAM mediante el Azure Portal, incluso si los dispositivos de las personas no están inscritos en Intune. Para obtener más información, consulte [introducción a las directivas de Protección de aplicaciones](/mem/intune/apps/app-protection-policy).

## <a name="related-content"></a>Contenido relacionado

[Configuración de Basic Mobility and Security](set-up.md) (artículo)\
[Inscribir el dispositivo móvil mediante Basic Mobility and Security](enroll-your-mobile-device.md) (artículo)\
[Administrar dispositivos inscritos en Mobile Administración de dispositivos para Microsoft 365](manage-enrolled-devices.md) (artículo)\
