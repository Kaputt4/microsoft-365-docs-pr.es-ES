---
title: Usar la protección de identidades, dispositivos y amenazas para la regulación de privacidad de datos
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
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847183"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Usar la protección de identidades, dispositivos y amenazas para la regulación de privacidad de datos

Microsoft 365 proporciona una serie de funcionalidades de protección de identidades, dispositivos y amenazas que las organizaciones pueden emplear para ayudar a cumplir con las normativas de cumplimiento relacionadas con la privacidad de los datos. En este artículo se describe lo que las normativas de privacidad de datos requieren en estas áreas y se proporciona una lista de características y servicios relacionados de Microsoft 365 con vínculos a más información para ayudarle a cumplir los requisitos de implementación.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Modo en que la protección de identidades, dispositivos y amenazas se relaciona con la regulación de privacidad de datos

Aunque las normativas de privacidad de datos varían en su especificidad, la esencia de lo que llaman se incluye en el artículo 5(1) (f) del RGPD, que indica que: 

- Los datos personales se procesarán de manera que garanticen la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra la pérdida, destrucción o daños accidentales, mediante las medidas técnicas u organizativas adecuadas ("integridad y confidencialidad").

Dado que las infracciones de datos personales suelen deberse a la amenaza de la cuenta administrativa o del usuario final y al acceso malintencionado al sistema. Por ejemplo, un pirateo de la cuenta de administrador puede provocar la filtración de los números de tarjeta de crédito del cliente u otra información personal. Todas las identidades, dispositivos y protección contra amenazas generalmente recomendables disponibles con Microsoft 365 potencialmente deben implementarse, lo que se reflejará en la puntuación de cumplimiento, que se encuentra en el Administrador de cumplimiento.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Uso de los resultados del trabajo de evaluación y el Administrador de cumplimiento

El Administrador de cumplimiento incluye protección contra amenazas, dispositivos y identidades mediante estas categorías:

- La identidad corresponde a la categoría **Acceso de** control
- El dispositivo corresponde a la categoría **Administrar dispositivos**
- La protección contra amenazas corresponde a la categoría **Proteger contra amenazas**
 
Si se seleccionan en nuestro conjunto de ejemplo de cuatro normativas principales de privacidad de datos, el Administrador de cumplimiento especifica 90 acciones de mejora, la mayoría de las cuales se marcan como "27". Dado que el Administrador de cumplimiento llama a un número tan grande para estas categorías, algunos de los más comunes se enumeran aquí, como referencia.

Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para la identidad y la categoría De acceso de **control,** con la que puede:

- Implementar la autenticación resistente a la reproducción (para evitar ataques "Man in the middle")
- Bloquear la autenticación heredada.
- Configurar directivas de riesgo de usuario y riesgo de inicio de sesión de usuario.
- Habilite el acceso condicional y la autenticación multifactor (MFA) para administradores y no administradores.
- Configurar y aplicar directivas de contraseña.
- Restrinja el acceso a cuentas con privilegios con Azure AD Privileged Identity Management.
- Deshabilitar el acceso al finalizar.
- Auditar cuentas de usuario y cambios de estado.
- Revise los cambios administrativos y del grupo de roles.

Usa [Microsoft Endpoint Manager para](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) dispositivos y la categoría Administrar **dispositivos,** con la que puedes:

- Bloquear los dispositivos móviles rotos y con raíz de la celda.
- Configurar Intune para la administración de dispositivos móviles.
- Crear directivas de cumplimiento para dispositivos Android, iOS, macOS y Windows.
- Cree un perfil de configuración de dispositivos para dispositivos Android, iOS, macOS y Windows.
- Crear directivas de protección de aplicaciones para iOS y Windows.
- Ocultar información con la pantalla de bloqueo.
- Implementar directivas de contraseña para dispositivos móviles.
- Requerir que los dispositivos móviles se bloquee tras la inactividad.
- Requerir que los dispositivos móviles borren varios errores de inicio de sesión.

Use Exchange Online Protection y Microsoft Defender para  [Office 365](../security/office-365-security/office-365-atp.md) para la categoría Proteger contra amenazas, con la que puede:

- Habilitar la autenticación del remitente (SPF, DMARC y DKIM).
- Configurar Microsoft Defender para las directivas contra suplantación de identidad de Office 365.
- Implementar datos adjuntos seguros.
- Implementar vínculos seguros.
- Implementar directivas de detección y respuesta de malware.
- Implementar directivas de correo no deseado saliente y entrante.

### <a name="references"></a>Referencias:

- [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)
- [Protección contra amenazas en Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Archivos adjuntos seguros](../security/office-365-security/atp-safe-attachments.md)
- [Vínculos seguros](../security/office-365-security/atp-safe-links.md)
- [Documentos seguros](../security/office-365-security/safe-docs.md)
