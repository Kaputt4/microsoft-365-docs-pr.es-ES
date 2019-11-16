---
title: Administración de dispositivos móviles para Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Conozca cómo Contoso utiliza Microsoft Intune en Microsoft 365 Enterprise para administrar los dispositivos y las aplicaciones que se ejecutan en ellos.
ms.openlocfilehash: c486c9ef338ab1bd8959266183da6b79d62b3311
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673186"
---
# <a name="mobile-device-management-for-contoso"></a>Administración de dispositivos móviles para Contoso

Microsoft 365 Enterprise incluye Intune y un conjunto de servicios de Azure para respaldar la administración y la seguridad de dispositivos móviles y aplicaciones.

Contoso tiene muchos empleados con servicios móviles habilitados. Algunos de ellos tienen oficinas en ubicaciones y otros no tienen oficinas. Contoso necesitaba una forma de facilitar la productividad de los empleados y, a la vez, proteger los dispositivos, los datos de Contoso almacenados en esos dispositivos y el comportamiento de la aplicación.

## <a name="plan"></a>Plan

En las primeras fases del análisis de la administración de dispositivos móviles para Microsoft 365 Enterprise, Contoso identificó los siguientes casos de uso de Intune:

- Proteger los datos y el correo electrónico de Exchange Online para que se pueda acceder a los mismos de forma segura
- Implementar un programa Bring your own device (BYOD) para los empleados de Contoso
- Dar a los empleados de Contoso tabletas de uso compartido y limitado y teléfonos propiedad de la organización

Contoso no va a usar Intune para:

- Permitir a los empleados que accedan de forma segura a Office 365 desde un quiosco público no administrado.
- Proteger los datos y el correo electrónico locales para que se pueda acceder a los mismos desde dispositivos móviles, porque ya no hay servidores de Microsoft Exchange locales.

## <a name="deploy"></a>Implementación

Contoso configuró la infraestructura de administración de sus dispositivos móviles de la siguiente manera:

- Configuró Intune como entidad de administración de dispositivos móviles (MDM) y está usando Intune en Azure para administrar el contenido y los dispositivos
- Grupos de Azure AD creados para dispositivos para las configuraciones de inscripción e Intune y las directivas de acceso condicional basadas en dispositivos

  Vea las [Directivas de acceso condicional de Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) para obtener más información.

- Habilitó la plataforma de dispositivos de Apple para dar soporte a los empleados con iPads, iMacs, iPhones y teléfonos de propiedad corporativa basados en iPhone.
- Creó directivas de términos y condiciones específicas para Contoso, que se muestran durante la instalación del Portal de empresa de Contoso en dispositivos móviles.
- Para los dispositivos que no están inscritos, un conjunto de directivas de administración de aplicaciones móviles (MAM) para exigir la autenticación para acceder a los servicios de Office 365.
- Creó directivas de Intune que determinan lo siguiente:
  - Aplicaciones permitidas
  - Cifrado del dispositivo para ayudar a evitar accesos no autorizados
  - Una contraseña o un PIN de seis dígitos
  - Un período de tiempo de espera de inactividad
  - Protección antivirus y contra malware, y actualizaciones de firma con Windows Defender en dispositivos con Windows 10
  - Actualizaciones automáticas en dispositivos con Windows 10, en las que se incluyen las actualizaciones de seguridad más recientes
  - Inserción de certificados en los dispositivos administrados
  - Una separación clara entre los datos personales y empresariales. Los usuarios o administradores pueden borrar datos corporativos desde el dispositivo, dejando intactos los datos personales, como, por ejemplo, imágenes, cuentas de correo electrónico personales y archivos personales.

Una vez realizada la implementación, Contoso inscribió equipos y dispositivos y tabletas propiedad de la empresa, agregándolos a los correspondientes grupos de dispositivos de Intune, y desarrolló un programa BYOD para que los empleados inscribieran sus dispositivos personales. Se aplicaron directivas de Intune a los dispositivos inscritos, con lo que se garantizó la administración y la protección de los dispositivos y sus aplicaciones. Los dispositivos no inscritos tienen directivas de administración de aplicaciones móviles (MAM) que establecen las aplicaciones permitidas.

Esta es la arquitectura de implementación de la administración de dispositivos móviles de Contoso.

![Infraestructura de implementación de la administración de dispositivos móviles de Contoso](./media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Siguiente paso

[Obtenga más información](contoso-info-protect.md) sobre cómo usa Contoso las funcionalidades de protección de la información de Microsoft 365 Enterprise para clasificar, identificar y proteger activos digitales cruciales en su organización.

## <a name="see-also"></a>Vea también

[Administración de dispositivos móviles para Microsoft 365 Enterprise](mobility-infrastructure.md)

[Guía de implementación](deploy-microsoft-365-enterprise.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)

