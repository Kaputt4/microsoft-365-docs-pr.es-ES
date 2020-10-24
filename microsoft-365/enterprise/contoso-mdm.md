---
title: Administración de dispositivos móviles para Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo contoso usa Microsoft Intune en Microsoft 365 para empresas para administrar los dispositivos y las aplicaciones que se ejecutan en ellos.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754002"
---
# <a name="mobile-device-management-for-contoso"></a>Administración de dispositivos móviles para Contoso

Microsoft 365 para empresas incluye Intune y un conjunto de servicios de Azure compatibles con la administración y seguridad de dispositivos móviles y aplicaciones.

Contoso tiene muchos empleados con movilidad habilitada. Algunas tienen oficinas en las ubicaciones de Contoso y otras no tienen oficinas. Contoso necesitaba una forma de habilitar la productividad de los empleados y mantener seguros los dispositivos, los datos de Contoso almacenados en dichos dispositivos y el comportamiento de la aplicación.

## <a name="plan"></a>Planear

Contoso identificó los siguientes casos de uso de Intune de la administración de dispositivos móviles para Microsoft 365 para empresas:

- Proteger los datos y el correo electrónico de Exchange Online para que los dispositivos móviles puedan acceder a ellos de forma segura.
- Implemente un programa traer a su propio dispositivo (BYOD) para los empleados de contoso.
- Emitir teléfonos de propiedad de organización y tabletas compartidas de uso limitado a los empleados de contoso.

Contoso no usa Intune para:

- Permitir a los empleados tener acceso seguro a Microsoft 365 desde un quiosco público no administrado.
- Proteger el correo electrónico y los datos locales para que los dispositivos móviles puedan acceder a ellos de forma segura, ya que no hay servidores de Microsoft Exchange locales.

## <a name="deploy"></a>Implementación

Contoso configuró la infraestructura de administración de sus dispositivos móviles de la siguiente manera:

- Establezca Intune como la entidad de administración de dispositivos móviles (MDM) y use Intune en Azure para administrar el contenido y administrar los dispositivos.
- Grupos de Azure Active Directory (Azure AD) creados para dispositivos para la configuración de Intune e Intune y las directivas de acceso condicional basadas en dispositivos

  Para obtener más información, consulte [directivas de acceso condicional de Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).

- Se ha habilitado la plataforma de dispositivos de Apple para admitir empleados con iPad, iMacs y iPhone y iPhones de propiedad corporativa.
- Creó directivas de términos y condiciones específicas para Contoso, que se muestran durante la instalación del Portal de empresa de Contoso en dispositivos móviles.
- Para los dispositivos que no están inscritos, implementó un conjunto de directivas de administración de aplicaciones móviles (MAM) para exigir la autenticación para obtener acceso a los servicios de Microsoft 365
- Creó directivas de Intune que determinan lo siguiente:
  - Aplicaciones permitidas.
  - Cifrado del dispositivo para ayudar a evitar el acceso no autorizado.
  - Un PIN de seis dígitos o una contraseña.
  - Un período de tiempo de espera de inactividad.
  - Protección antivirus y contra malware, y actualizaciones de firmas con Windows Defender en dispositivos Windows 10.
  - Actualizaciones automáticas en dispositivos con Windows 10 que incluyen las actualizaciones de seguridad más recientes.
  - Insertar certificados en los dispositivos administrados.
  - Una separación clara entre los datos personales y empresariales. Los usuarios o administradores pueden borrar datos corporativos desde el dispositivo, dejando intactos los datos personales, como, por ejemplo, imágenes, cuentas de correo electrónico personales y archivos personales.

Contoso inscribió los equipos implementados y smartphones y tabletas de propiedad de la empresa agregándolos a los grupos de dispositivos de Intune adecuados. También establecieron un programa BYOD para que los empleados inscriban sus dispositivos personales. Los dispositivos inscritos reciben directivas de Intune, que tienen como resultado los dispositivos administrados y protegidos y sus aplicaciones. Los dispositivos que no están inscritos tienen directivas de administración de aplicaciones móviles (MAM) que especifican las aplicaciones permitidas.

Esta es la arquitectura de implementación de administración de dispositivos móviles de contoso.

![Infraestructura de implementación de administración de dispositivos móviles de Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo contoso usa las [capacidades de protección](contoso-info-protect.md) de la información de Microsoft 365 para empresas para clasificar, identificar y proteger activos digitales fundamentales en toda su organización.

## <a name="see-also"></a>Recursos adicionales

[Administración de dispositivos para Microsoft 365](device-management-roadmap-microsoft-365.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)

