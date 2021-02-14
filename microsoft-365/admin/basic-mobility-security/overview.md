---
title: Información general sobre movilidad y seguridad básicas para Microsoft 365
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
description: Use Movilidad y seguridad básicas para establecer directivas de seguridad de dispositivos y reglas de acceso.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430297"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Información general sobre movilidad y seguridad básicas para Microsoft 365

Puede administrar y proteger los dispositivos móviles cuando estén conectados a su organización de Microsoft 365 mediante movilidad y seguridad básicas. Los dispositivos móviles, como los smartphones y las tabletas, que se usan para tener acceso a elementos de trabajo como el correo electrónico, el calendario, los contactos y los documentos, desempeñan un papel muy importante a la hora de garantizar que los empleados puedan realizar su trabajo en cualquier momento y en cualquier lugar. Por lo tanto, es fundamental que ayude a proteger la información de su organización cuando los usuarios usan dispositivos. Puede usar movilidad y seguridad básicas para establecer directivas de seguridad de dispositivos y reglas de acceso, y para borrar los dispositivos móviles si se pierden o se roban.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuración básica de movilidad y seguridad":::

## <a name="what-types-of-devices-can-you-manage"></a>¿Qué tipos de dispositivos se pueden administrar?

Puede usar movilidad y seguridad básicas para administrar muchos tipos de dispositivos móviles como Windows Phone, Android, iPhone y iPad. Para administrar los dispositivos móviles que usan las personas de su organización, cada persona debe tener una licencia de Microsoft 365 aplicable y su dispositivo debe estar inscrito en Movilidad y Seguridad básicas.

Para ver qué admite La movilidad y la seguridad básicas para cada tipo de dispositivo, consulta [Funcionalidades de movilidad y seguridad básicas.](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>Pasos de configuración para movilidad y seguridad básicas

Un administrador global de Microsoft 365 debe completar los siguientes pasos para activar y configurar la movilidad y seguridad básicas. Para conocer los pasos detallados, siga las instrucciones de [Configuración de movilidad y seguridad básicas.](set-up.md) 

Este es un resumen de los pasos:

**Paso 1:** Active la movilidad y la seguridad básica siguiendo los pasos descritos  [en La configuración de movilidad y seguridad básicas.](set-up.md)

**Paso 2:** Configure la movilidad y seguridad básicas mediante, por ejemplo, la creación de un certificado APNs para administrar dispositivos iOS y la adición de un registro del Sistema de nombres de dominio (DNS) para que el dominio admita teléfonos Windows.

**Paso 3:** Crear directivas de dispositivo y aplicarlas a grupos de usuarios. Al hacerlo, los usuarios obtienen un mensaje de inscripción en su dispositivo y, cuando hayan completado la inscripción, sus dispositivos están restringidos por las directivas que hayas configurado para ellos. Para obtener más información, consulta [Inscribir el dispositivo móvil con movilidad y seguridad básicas.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración de directivas básicas de seguridad y movilidad":::

## <a name="device-management-tasks"></a>Tareas de administración de dispositivos

Después de configurar la movilidad y la seguridad básicas y de que los usuarios se han inscrito en sus dispositivos, puedes administrar los dispositivos, bloquear el acceso o borrar un dispositivo, si es necesario. Para obtener más información sobre algunas tareas comunes de administración de dispositivos, incluido dónde completar las tareas, vea Administrar dispositivos inscritos en administración de dispositivos [móviles para Microsoft 365.](manage-enrolled-devices.md)

## <a name="other-ways-to-manage-devices-and-apps"></a>Otras formas de administrar dispositivos y aplicaciones

Si solo necesitas la administración de aplicaciones móviles (MAM), quizás para personas que actualicen proyectos de trabajo en sus propios dispositivos, Intune ofrece otra opción además de inscribir y administrar dispositivos. Una suscripción de Intune le permite configurar directivas de MAM con Azure Portal, incluso si los dispositivos de las personas no están inscritos en Intune. Para obtener más información, consulta Introducción [a las directivas de protección de aplicaciones.](https://go.microsoft.com/fwlink/?LinkId=2132517)

## <a name="related-topics"></a>Temas relacionados

[Configurar la Seguridad de Movilidad Básica](set-up.md)

[Inscribir el dispositivo móvil con movilidad y seguridad básicas](enroll-your-mobile-device.md)

[Administrar dispositivos inscritos en la administración de dispositivos móviles para Microsoft 365](manage-enrolled-devices.md)

[Obtener detalles sobre los dispositivos administrados por movilidad y seguridad básicas](get-details-about-managed-devices.md)