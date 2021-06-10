---
title: Habilitar el acceso condicional para proteger mejor a los usuarios, dispositivos y datos
description: Habilite el acceso condicional para evitar que las aplicaciones se ejecuten si un dispositivo se considera en riesgo y se determina que una aplicación no es compatible.
keywords: acceso condicional, bloquear aplicaciones, nivel de seguridad, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166202"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>Habilitar el acceso condicional para proteger mejor a los usuarios, dispositivos y datos 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

El acceso condicional es una funcionalidad que te ayuda a proteger mejor la información de los usuarios y de la empresa al asegurarte de que solo los dispositivos seguros tienen acceso a las aplicaciones.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

Con el acceso condicional, puedes controlar el acceso a la información empresarial en función del nivel de riesgo de un dispositivo. Esto ayuda a mantener los usuarios de confianza en dispositivos de confianza con aplicaciones de confianza.

Puedes definir las condiciones de seguridad en las que los dispositivos y las aplicaciones pueden ejecutarse y acceder a la información desde la red aplicando directivas para impedir que las aplicaciones se ejecuten hasta que un dispositivo vuelva a un estado compatible. 

La implementación del acceso condicional en Defender para endpoint se basa en directivas de cumplimiento de dispositivos de Microsoft Intune (Intune) y directivas de acceso condicional Azure Active Directory (Azure AD). 

La directiva de cumplimiento se usa con acceso condicional para permitir que solo los dispositivos que cumplan una o más reglas de directiva de cumplimiento de dispositivos puedan acceder a las aplicaciones. 

## <a name="understand-the-conditional-access-flow"></a>Comprender el flujo de acceso condicional
El acceso condicional se pone en marcha para que, cuando se ve una amenaza en un dispositivo, se bloquee el acceso al contenido confidencial hasta que se corrija la amenaza. 

El flujo comienza con dispositivos que se ven con un riesgo bajo, medio o alto. A continuación, estas determinaciones de riesgos se envían a Intune. 

Según cómo configure las directivas en Intune, se puede configurar el acceso condicional para que, cuando se cumplen determinadas condiciones, se aplique la directiva.

Por ejemplo, puede configurar Intune para aplicar el acceso condicional a dispositivos con un alto riesgo.

En Intune, se usa una directiva de cumplimiento de dispositivos junto con el acceso condicional de Azure AD para bloquear el acceso a las aplicaciones. En paralelo, se inicia un proceso automatizado de investigación y corrección.

 Un usuario todavía puede usar el dispositivo mientras se lleva a cabo la investigación automatizada y la corrección, pero el acceso a los datos de la empresa se bloquea hasta que la amenaza se corrija por completo. 

Para resolver el riesgo encontrado en un dispositivo, tendrás que devolver el dispositivo a un estado compatible. Un dispositivo vuelve a un estado de cumplimiento cuando no se ve ningún riesgo en él. 

Hay tres formas de abordar un riesgo:
1. Use la corrección manual o automatizada.
2. Resolver alertas activas en el dispositivo. Esto eliminará el riesgo del dispositivo.
3. Puedes quitar el dispositivo de las directivas activas y, por lo tanto, el acceso condicional no se aplicará en el dispositivo. 

La corrección manual requiere que un administrador de secops investigue una alerta y solucione el riesgo que se ve en el dispositivo. La corrección automatizada se configura a través de las opciones de configuración proporcionadas en la siguiente sección, [Configurar el acceso condicional](configure-conditional-access.md).

Cuando se quita el riesgo a través de la corrección manual o automatizada, el dispositivo vuelve a un estado compatible y se concede acceso a las aplicaciones.

La siguiente secuencia de eventos de ejemplo explica el acceso condicional en acción:

1. Un usuario abre un archivo malintencionado y Defender para endpoint marca el dispositivo como de alto riesgo.
2. La evaluación de alto riesgo se pasa a Intune. En paralelo, se inicia una investigación automatizada para corregir la amenaza identificada. También se puede realizar una corrección manual para corregir la amenaza identificada.
3. Según la directiva creada en Intune, el dispositivo se marca como no compatible. A continuación, la directiva de acceso condicional de Intune comunica la evaluación a Azure AD. En Azure AD, la directiva correspondiente se aplica para bloquear el acceso a las aplicaciones.
4. La investigación y corrección manual o automatizada se completa y se elimina la amenaza. Defender for Endpoint ve que no hay ningún riesgo en el dispositivo e Intune evalúa que el dispositivo está en un estado de cumplimiento. Azure AD aplica la directiva que permite el acceso a las aplicaciones.
5. Los usuarios ahora pueden acceder a las aplicaciones.

 
## <a name="related-topic"></a>Tema relacionado
- [Configurar el acceso condicional en Microsoft Defender para el extremo](configure-conditional-access.md)
