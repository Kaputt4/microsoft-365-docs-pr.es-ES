---
title: Usar la protección de identidad, dispositivo y amenazas para la regulación de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Evitar infracciones de datos personales con los servicios de protección de identidades, dispositivos y amenazas de Microsoft 365.
ms.openlocfilehash: 145b8a59f7eafb95adf71dc24613ee15ef1c2cca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052355"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Usar la protección de identidad, dispositivo y amenazas para la regulación de privacidad de datos

Microsoft 365 proporciona una serie de capacidades de protección de identidades, dispositivos y amenazas que las organizaciones pueden usar para ayudar a cumplir con las normativas de cumplimiento relacionadas con la privacidad de datos. En este artículo se describe lo que requieren las normativas de privacidad de datos en estas áreas y se proporciona una lista de características y servicios relacionados de Microsoft 365 con vínculos a más información para ayudarle a abordar los requisitos de implementación.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Cómo se relaciona la protección de identidades, dispositivos y amenazas con la regulación de privacidad de datos

Aunque los reglamentos de privacidad de datos varían en su especificidad, la esencia de lo que llaman se incluye en el artículo 5(1) f del RGPD, que establece que:

- Los datos personales se procesarán de manera que se garantice la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra pérdidas, destrucción o daños accidentales, mediante medidas técnicas o organizativas apropiadas ("integridad y confidencialidad").

Debido a que las infracciones de datos personales suelen deberse a un riesgo administrativo o a una cuenta de usuario final y al acceso malintencionado al sistema. Por ejemplo, un hackeo de una cuenta de administrador puede provocar la filtración de números de tarjeta de crédito del cliente u otra información personal. Toda la identidad, dispositivo y protección contra amenazas generalmente recomendables disponibles con Microsoft 365 potencialmente debe implementarse, lo que se reflejará en la puntuación de cumplimiento, que se encuentra en el Administrador de cumplimiento.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Uso de los resultados del trabajo de evaluación y el Administrador de cumplimiento

El Administrador de cumplimiento incluye la identidad, el dispositivo y la protección contra amenazas mediante estas categorías:

- Identity corresponde a la categoría **Control Access**
- El dispositivo corresponde a la **categoría Administrar dispositivos**
- La protección contra amenazas corresponde a la **categoría Proteger contra** amenazas
 
Si se seleccionan en nuestro conjunto de ejemplo de cuatro normativas principales de privacidad de datos, el Administrador de cumplimiento especifica 90 acciones de mejora, la mayoría de las cuales se puntuan como "27". Dado que el Administrador de cumplimiento llama a un número tan grande para estas categorías, algunos de los más comunes se enumeran aquí, como referencia.

Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para la identidad y la categoría Control **Access,** con la que puede:

- Implementar la autenticación resistente a la reproducción (para evitar ataques "Man in the middle")
- Bloquear la autenticación heredada.
- Configurar directivas de riesgo de usuario y de inicio de sesión de usuario.
- Habilitar el acceso condicional y la autenticación multifactor (MFA) para administradores y no administradores.
- Configurar y aplicar directivas de contraseña.
- Restringir el acceso a cuentas con privilegios con Azure AD Privileged Identity Management.
- Deshabilite el acceso al finalizar.
- Auditar cuentas de usuario y cambios de estado.
- Revise los cambios administrativos y del grupo de roles.

Usa [Microsoft Endpoint Manager para](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) dispositivos y la categoría Administrar **dispositivos,** con la que puedes:

- Bloquear la cárcel de dispositivos móviles rotos y arraigados.
- Configurar Intune para la administración de dispositivos móviles.
- Crea directivas de cumplimiento para dispositivos Android, iOS, macOS y Windows.
- Crea un perfil de configuración de dispositivos para dispositivos Android, iOS, macOS y Windows.
- Crear directivas de protección de aplicaciones para iOS y Windows.
- Ocultar información con pantalla de bloqueo.
- Implementar directivas de contraseña para dispositivos móviles.
- Requerir que los dispositivos móviles bloquee la inactividad.
- Requerir que los dispositivos móviles borren varios errores de inicio de sesión.

Use [Exchange Online Protection y Microsoft Defender para Office 365](../security/defender-365-security/defender-for-office-365.md) para la categoría **Proteger** contra amenazas, con la que puede:

- Habilitar la autenticación del remitente (SPF, DMARC y DKIM).
- Configurar Las directivas contra suplantación de identidad de Microsoft Defender para Office 365.
- Implementar datos adjuntos seguros.
- Implementar vínculos seguros.
- Implementar directivas de detección y respuesta de malware.
- Implementar directivas de correo no deseado salientes y entrantes.

### <a name="references"></a>Referencias:

- [Directivas comunes de acceso a dispositivos e identidades](../security/defender-365-security/identity-access-policies.md)
- [Proteger contra amenazas en Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Archivos adjuntos seguros](../security/defender-365-security/safe-attachments.md)
- [Vínculos seguros](../security/defender-365-security/safe-links.md)
- [Documentos seguros](../security/defender-365-security/safe-docs.md)
