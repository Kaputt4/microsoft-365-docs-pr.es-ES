---
title: Uso de la protección contra amenazas, dispositivos y identidades para la regulación de privacidad de datos
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
description: Evite vulneraciones de datos personales con los servicios de protección contra amenazas, dispositivos y identidades de Microsoft 365.
ms.openlocfilehash: 1769f67d9815a1a7a3e556e9078aace6366fbf4c
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731560"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Uso de la protección contra amenazas, dispositivos y identidades para la regulación de privacidad de datos

Microsoft 365 proporciona una serie de funcionalidades de protección contra amenazas, dispositivos y identidades que las organizaciones pueden emplear para ayudar a cumplir con las regulaciones de cumplimiento relacionadas con la privacidad de los datos. En este artículo se describe lo que requieren las regulaciones de privacidad de datos en estas áreas y se proporciona una lista de las características y servicios relacionados de Microsoft 365 con vínculos a más información para ayudarle a abordar los requisitos de implementación.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Relación entre la identidad, el dispositivo y la protección contra amenazas con la regulación de privacidad de datos

Aunque las regulaciones de privacidad de datos varían en su especificidad, la esencia de lo que piden se incluye en el artículo 5(1)(f) del RGPD, que establece que:

- Los datos personales se procesarán de forma que garantice la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra la pérdida accidental, la destrucción o el daño, utilizando las medidas técnicas u organizativas adecuadas («integridad y confidencialidad»).

Dado que las infracciones de datos personales suelen deberse a riesgos administrativos o de cuentas de usuario final y acceso malintencionado al sistema. Por ejemplo, un hack de cuenta de administrador puede dar lugar a la filtración de números de tarjeta de crédito del cliente u otra información personal. Se debe implementar toda la protección contra amenazas, dispositivo y identidad generalmente aconsejable disponible con Microsoft 365, que se reflejará en la puntuación de cumplimiento, que se encuentra en el Administrador de cumplimiento.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Uso de los resultados del trabajo de evaluación y el Administrador de cumplimiento

El Administrador de cumplimiento incluye la protección contra amenazas, dispositivos y identidades mediante estas categorías:

- La identidad corresponde a la categoría **Control Access**
- El dispositivo corresponde a la categoría **Administrar dispositivos**
- Protección contra amenazas corresponde a la categoría **Proteger contra amenazas**
 
Si se seleccionan en nuestro conjunto de ejemplo de cuatro regulaciones principales de privacidad de datos, el Administrador de cumplimiento especifica 90 acciones de mejora, la mayoría de las cuales se puntúan como "27". Dado que el Administrador de cumplimiento llama a un número tan grande para estas categorías, aquí se enumeran algunas de las más comunes, como referencia.

Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para la identidad y la categoría **Control Access** , con la que puede:

- Implementación de la autenticación resistente a la reproducción (para evitar ataques de tipo "Man in the middle")
- Bloquear la autenticación heredada.
- Configure las directivas de riesgo de inicio de sesión de usuario y riesgo de usuario.
- Habilite el acceso condicional y la autenticación multifactor (MFA) para administradores y no administradores.
- Configurar y aplicar directivas de contraseña.
- Restringir el acceso a cuentas con privilegios con Azure AD Privileged Identity Management.
- Deshabilite el acceso tras la terminación.
- Audite las cuentas de usuario y los cambios de estado.
- Revise los cambios administrativos y del grupo de roles.

Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) para dispositivos y la categoría **Administrar dispositivos**, con la que puede:

- Bloquear dispositivos móviles rotos y rooteados.
- Configure Intune para la administración de dispositivos móviles.
- Cree directivas de cumplimiento para dispositivos Android, iOS, macOS y Windows.
- Cree un perfil de configuración de dispositivo para dispositivos Android, iOS, macOS y Windows.
- Cree directivas de protección de aplicaciones para iOS y Windows.
- Ocultar información con pantalla de bloqueo.
- Implemente directivas de contraseña para dispositivos móviles.
- Requerir que los dispositivos móviles se bloqueen ante la inactividad.
- Requerir que los dispositivos móviles borren varios errores de inicio de sesión.

Use [Exchange Online Protection y Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md) para la categoría **Proteger contra amenazas**, con la que puede:

- Habilitar la autenticación del remitente (SPF, DMARC y DKIM).
- Configure Microsoft Defender para Office 365 directivas contra phishing.
- Implementar datos adjuntos seguros.
- Implementar vínculos seguros.
- Implementar directivas de detección y respuesta de malware.
- Implementar directivas de correo no deseado entrante y saliente.

### <a name="references"></a>Referencias:

- [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)
- [Protección contra amenazas en Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Archivos adjuntos seguros](../security/office-365-security/safe-attachments.md)
- [Vínculos seguros](../security/office-365-security/safe-links.md)
- [Documentos seguros](../security/office-365-security/safe-docs.md)
