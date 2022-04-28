---
title: Administración de dispositivos móviles para Contoso
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo Contoso usa Microsoft Intune en Microsoft 365 para empresas para administrar sus dispositivos y las aplicaciones que se ejecutan en ellos.
ms.openlocfilehash: c321fc9bdaf27577e32d934aa771c92d1a0bdd79
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092699"
---
# <a name="mobile-device-management-for-contoso"></a>Administración de dispositivos móviles para Contoso

Microsoft 365 para empresas incluye Intune y un conjunto de servicios de Azure que admiten la administración y la seguridad de dispositivos móviles y aplicaciones.

Contoso tiene muchos empleados habilitados para dispositivos móviles. Algunas tienen oficinas en ubicaciones de Contoso y otras no tienen oficinas. Contoso necesitaba una manera de habilitar la productividad de los empleados, pero mantener seguros los dispositivos, los datos de Contoso almacenados en esos dispositivos y el comportamiento de la aplicación.

## <a name="plan"></a>Plan

Contoso identificó los siguientes casos de uso de Intune de administración de dispositivos móviles para Microsoft 365 para empresas:

- Proteja Exchange Online correo electrónico y datos para que los dispositivos móviles puedan acceder a ellos de forma segura.
- Implemente un programa bring-your-own-device (BYOD) para los empleados de Contoso.
- Emita teléfonos propiedad de la organización y tabletas compartidas de uso limitado a los empleados de Contoso.

Contoso no usa Intune para:

- Permitir que los empleados accedan de forma segura a Microsoft 365 desde un quiosco público no administrado.
- Proteja el correo electrónico y los datos locales para que los dispositivos móviles puedan acceder a ellos de forma segura, ya que no hay servidores de Microsoft Exchange locales.

## <a name="deploy"></a>Implementación

Contoso configuró la infraestructura de administración de sus dispositivos móviles de la siguiente manera:

- Establezca Intune como entidad de Administración de dispositivos móvil (MDM) y use Intune en Azure para administrar el contenido y administrar los dispositivos.
- Se han creado grupos de Azure Active Directory (Azure AD) para dispositivos para la inscripción y la configuración de Intune y las directivas de acceso condicional basadas en dispositivos

  Para obtener más información, consulte [Directivas de acceso condicional de Contoso](contoso-identity.md#conditional-access-policies-for-zero-trust-identity-and-device-access).

- Se ha habilitado la plataforma de dispositivos de Apple para admitir a los empleados con iPads, iMacs y iPhone, y iPhones corporativos.
- Creó directivas de términos y condiciones específicas para Contoso, que se muestran durante la instalación del Portal de empresa de Contoso en dispositivos móviles.
- Para los dispositivos que no están inscritos, implementó un conjunto de directivas de administración de aplicaciones móviles (MAM) para requerir autenticación para el acceso a Microsoft 365 servicios.
- Creó directivas de Intune que determinan lo siguiente:
  - Aplicaciones permitidas.
  - Cifrado de dispositivos para ayudar a evitar el acceso no autorizado.
  - Pin o contraseña de seis dígitos.
  - Un período de tiempo de espera de inactividad.
  - Protección antivirus y malware, y actualizaciones de firmas con Windows Defender en dispositivos Windows 10.
  - Actualizaciones automáticas en dispositivos Windows 10 que incluyen las actualizaciones de seguridad más recientes.
  - Inserción de certificados en dispositivos administrados.
  - Una separación clara entre los datos personales y empresariales. Los usuarios o administradores pueden borrar datos corporativos desde el dispositivo, dejando intactos los datos personales, como, por ejemplo, imágenes, cuentas de correo electrónico personales y archivos personales.

Contoso inscribió equipos implementados y smartphones y tabletas propiedad de la empresa agregándolos a los grupos de dispositivos Intune adecuados. También establecieron un programa BYOD para que los empleados inscriban sus dispositivos personales. Los dispositivos inscritos reciben directivas de Intune, lo que da como resultado dispositivos administrados y protegidos y sus aplicaciones. Los dispositivos que no están inscritos tienen directivas de administración de aplicaciones móviles (MAM) que especifican las aplicaciones permitidas.

Esta es la arquitectura de implementación de administración de dispositivos móviles de Contoso.

![Infraestructura de implementación de administración de dispositivos móviles de Contoso.](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso usa las [funcionalidades de protección de la información](contoso-info-protect.md) de Microsoft 365 para empresas con el fin de clasificar, identificar y proteger recursos digitales cruciales en toda su organización.

## <a name="see-also"></a>Vea también

[Administración de dispositivos para Microsoft 365](device-management-roadmap-microsoft-365.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)

