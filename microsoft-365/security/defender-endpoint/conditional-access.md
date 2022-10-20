---
title: Habilitación del acceso condicional para proteger mejor a los usuarios, dispositivos y datos
description: Habilite el acceso condicional para evitar que las aplicaciones se ejecuten si un dispositivo se considera en riesgo y se determina que una aplicación no es compatible.
keywords: acceso condicional, bloquear aplicaciones, nivel de seguridad, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 5a1570d63dd298dde2dd375a14dee8e1a36e71f4
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68629861"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>Habilitación del acceso condicional para proteger mejor a los usuarios, dispositivos y datos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

El acceso condicional es una funcionalidad que le ayuda a proteger mejor a los usuarios y a la información empresarial asegurándose de que solo los dispositivos seguros tengan acceso a las aplicaciones.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4byD1]

Con el acceso condicional, puede controlar el acceso a la información empresarial en función del nivel de riesgo de un dispositivo. Esto ayuda a mantener a los usuarios de confianza en dispositivos de confianza mediante aplicaciones de confianza.

Puede definir las condiciones de seguridad en las que los dispositivos y las aplicaciones pueden ejecutar y acceder a la información desde la red mediante la aplicación de directivas para impedir que las aplicaciones se ejecuten hasta que un dispositivo vuelva a un estado conforme.

La implementación del acceso condicional en Defender para punto de conexión se basa en directivas de cumplimiento de dispositivos Microsoft Intune (Intune) y directivas de acceso condicional de Azure Active Directory (Azure AD).

La directiva de cumplimiento se usa con el acceso condicional para permitir que solo los dispositivos que cumplan una o varias reglas de directiva de cumplimiento de dispositivos accedan a las aplicaciones.

## <a name="understand-the-conditional-access-flow"></a>Descripción del flujo de acceso condicional

El acceso condicional se establece para que cuando se vea una amenaza en un dispositivo, se bloquee el acceso al contenido confidencial hasta que se corrija la amenaza.

El flujo comienza con que se ve que los dispositivos tienen un riesgo bajo, medio o alto. Estas determinaciones de riesgo se envían a Intune.

En función de cómo configure las directivas en Intune, se puede configurar el acceso condicional para que, cuando se cumplan ciertas condiciones, se aplique la directiva.

Por ejemplo, puede configurar Intune para aplicar el acceso condicional en dispositivos que tienen un alto riesgo.

En Intune, se usa una directiva de cumplimiento de dispositivos junto con el acceso condicional de Azure AD para bloquear el acceso a las aplicaciones. En paralelo, se inicia un proceso de investigación y corrección automatizado.

 Un usuario puede seguir usando el dispositivo mientras se lleva a cabo la investigación y corrección automatizadas, pero el acceso a los datos empresariales se bloquea hasta que la amenaza se corrija por completo.

Para resolver el riesgo que se encuentra en un dispositivo, deberá devolver el dispositivo a un estado conforme. Un dispositivo vuelve a un estado conforme cuando no se ve ningún riesgo en él.

Hay tres maneras de abordar un riesgo:

1. Use la corrección manual o automatizada.
2. Resuelva las alertas activas en el dispositivo. Esto eliminará el riesgo del dispositivo.
3. Puede quitar el dispositivo de las directivas activas y, en consecuencia, el acceso condicional no se aplicará en el dispositivo.

La corrección manual requiere que un administrador de secops investigue una alerta y aborde el riesgo detectado en el dispositivo. La corrección automatizada se configura a través de los valores de configuración proporcionados en la sección siguiente, [Configuración del acceso condicional](configure-conditional-access.md).

Cuando el riesgo se elimina mediante una corrección manual o automatizada, el dispositivo vuelve a un estado conforme y se concede acceso a las aplicaciones.

En la siguiente secuencia de ejemplo de eventos se explica el acceso condicional en acción:

1. Un usuario abre un archivo malintencionado y Defender para punto de conexión marca el dispositivo como de alto riesgo.
2. La evaluación de alto riesgo se pasa a Intune. En paralelo, se inicia una investigación automatizada para corregir la amenaza identificada. También se puede realizar una corrección manual para corregir la amenaza identificada.
3. En función de la directiva creada en Intune, el dispositivo se marca como no compatible. A continuación, la directiva de acceso condicional de Intune comunica la evaluación a Azure AD. En Azure AD, la directiva correspondiente se aplica para bloquear el acceso a las aplicaciones.
4. La investigación y la corrección manuales o automatizadas se completan y se quita la amenaza. Defender para punto de conexión ve que no hay ningún riesgo en el dispositivo y Intune evalúa el dispositivo para que esté en un estado conforme. Azure AD aplica la directiva que permite el acceso a las aplicaciones.
5. Los usuarios ahora pueden acceder a las aplicaciones.

## <a name="related-topic"></a>Tema relacionado

- [Configuración del acceso condicional en Microsoft Defender para punto de conexión](configure-conditional-access.md)
