---
title: Información general sobre movilidad básica y seguridad para Microsoft 365
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
description: Usa Movilidad y seguridad básicas para establecer directivas de seguridad de dispositivos y reglas de acceso.
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706315"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Información general sobre movilidad básica y seguridad para Microsoft 365

Puedes administrar y proteger los dispositivos móviles cuando estén conectados a tu organización Microsoft 365 mediante movilidad y seguridad básicas. Los dispositivos móviles, como los smartphones y las tabletas, que se usan para tener acceso a elementos de trabajo como el correo electrónico, el calendario, los contactos y los documentos, desempeñan un papel muy importante a la hora de garantizar que los empleados puedan realizar su trabajo en cualquier momento y en cualquier lugar. Por lo tanto, es fundamental que ayudes a proteger la información de la organización cuando las personas usan dispositivos. Puedes usar Movilidad y seguridad básicas para establecer directivas de seguridad de dispositivos y reglas de acceso, y para borrar los dispositivos móviles si se pierden o se roban.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuración básica de movilidad y seguridad":::

## <a name="what-types-of-devices-can-you-manage"></a>¿Qué tipos de dispositivos se pueden administrar?

Puedes usar Movilidad y seguridad básicas para administrar muchos tipos de dispositivos móviles como Windows Phone, Android, iPhone y iPad. Para administrar los dispositivos móviles usados por los usuarios de la organización, cada persona debe tener una licencia de Microsoft 365 y su dispositivo debe estar inscrito en Movilidad y seguridad básicas.

Para ver qué admite movilidad y seguridad básicas para cada tipo de dispositivo, consulta [Funcionalidades de movilidad y seguridad básicas.](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>Pasos de configuración para movilidad y seguridad básicas

Un Microsoft 365 global debe completar los siguientes pasos para activar y configurar La movilidad y la seguridad básicas. Para conocer los pasos detallados, siga las instrucciones [de Configurar movilidad y seguridad básicas.](set-up.md) 

Este es un resumen de los pasos:

**Paso 1:** Active La movilidad y la seguridad básicas siguiendo los pasos descritos  [en Configurar la movilidad básica y la seguridad.](set-up.md)

**Paso 2:** Configure la movilidad y la seguridad básicas mediante, por ejemplo, crear un certificado de APNs para administrar dispositivos iOS y agregar un registro de sistema de nombres de dominio (DNS) para que el dominio admita Windows teléfonos.

**Paso 3:** Crear directivas de dispositivo y aplicarlas a grupos de usuarios. Al hacerlo, los usuarios obtienen un mensaje de inscripción en su dispositivo y, cuando han completado la inscripción, sus dispositivos están restringidos por las directivas que haya configurado para ellos. Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración básica de la directiva de seguridad y movilidad":::

## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Después de configurar La movilidad y la seguridad básicas y de que los usuarios se han inscrito en sus dispositivos, puedes administrar los dispositivos, bloquear el acceso o borrar un dispositivo, si es necesario. Para obtener más información sobre algunas tareas comunes de administración de dispositivos, incluido dónde completar las [tareas,](manage-enrolled-devices.md)consulta Administrar dispositivos inscritos en Administración de dispositivos móviles para Microsoft 365 .

## <a name="other-ways-to-manage-devices-and-apps"></a>Otras formas de administrar dispositivos y aplicaciones

Si solo necesitas administración de aplicaciones móviles (MAM), quizás para personas que actualicen proyectos de trabajo en sus propios dispositivos, Intune ofrece otra opción además de inscribir y administrar dispositivos. Una suscripción a Intune te permite configurar directivas de MAM con Azure Portal, incluso si los dispositivos de las personas no están inscritos en Intune. Para obtener más información, consulta [Introducción a las directivas de protección de aplicaciones.](/mem/intune/apps/app-protection-policy)

## <a name="related-content"></a>Contenido relacionado

[Configurar movilidad y seguridad básicas](set-up.md) (artículo)\
[Inscribir el dispositivo móvil con movilidad básica y seguridad](enroll-your-mobile-device.md) (artículo)\
[Administrar dispositivos inscritos en Administración de](manage-enrolled-devices.md) dispositivos móviles para Microsoft 365 (artículo)\
[Obtener detalles sobre los dispositivos administrados por Basic Mobility and Security](get-details-about-managed-devices.md) (artículo)