---
title: Evaluación y Microsoft 365 Defender piloto, una solución XDR
description: ¿Qué es la seguridad de XDR? ¿Cómo puede evaluar un XDR de Microsoft en Microsoft 365 Defender? Use esta serie de blogs para planear su Microsoft 365 Defender laboratorio de prueba o entorno piloto para probar y probar una solución de seguridad diseñada para proteger dispositivos, identidades, datos y aplicaciones. Inicie su viaje de ciberseguridad de XDR aquí y realice esa prueba a producción.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 09/15/2022
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: d7e2a6e68f91be81bd53638c16f50ed250555217
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67741486"
---
# <a name="evaluate-and-pilot-microsoft-365-defender"></a>Evaluar Microsoft 365 Defender y realizar una prueba piloto

**Se aplica a:**

- Microsoft 365 Defender

## <a name="how-this-article-series-works"></a>Funcionamiento de esta serie de artículos

Esta serie de artículos está diseñada para guiarle en todo el proceso de configuración de un entorno XDR de prueba, de *un extremo a otro, para* que pueda evaluar las características y funcionalidades de Microsoft 365 Defender e incluso promover el entorno de evaluación directamente a producción cuando y si está listo.

Si no está familiarizado con la idea de XDR, puede examinar estos 7 artículos vinculados para hacerse una idea de lo completa que es la solución.

- [Creación del entorno](eval-create-eval-environment.md)
- Configuración o información sobre cada tecnología de este XDR de Microsoft
  - [Microsoft Defender for Identity](eval-defender-identity-overview.md)
  - [Microsoft Defender para Office](eval-defender-office-365-overview.md)
  - [Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)
  - [Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)
- [Cómo investigar y responder con este XDR](eval-defender-investigate-respond.md)
- [Promover el entorno de prueba a producción](eval-defender-promote-to-production.md)

## <a name="microsoft-365-defender-is-a-microsoft-xdr-cyber-security-solution"></a>Microsoft 365 Defender es una solución de ciberseguridad de Microsoft XDR

Microsoft 365 Defender es una solución de **detección y respuesta (XDR) eXtended** que recopila, correlaciona y analiza automáticamente datos de señal, amenaza y alerta de *todo* el entorno de Microsoft 365, incluidos los puntos de *conexión, el correo electrónico, las aplicaciones y las identidades*. Aprovecha la inteligencia artificial (IA) y la automatización para detener *automáticamente* los ataques y corregir los recursos afectados en un estado seguro.

Piense en XDR como el siguiente paso en seguridad, unificar el punto de conexión (detección y respuesta de puntos de conexión o EDR), el correo electrónico, la aplicación y la seguridad de identidad en un solo lugar.

## <a name="microsoft-recommendations-for-evaluating-microsoft-365-defender"></a>Recomendaciones de Microsoft para evaluar Microsoft 365 Defender

Microsoft recomienda crear la evaluación en una suscripción de producción existente de Office 365. De este modo, obtendrá información real inmediatamente y podrá ajustar la configuración para que funcione frente a las amenazas actuales en su entorno. Una vez que haya adquirido experiencia y esté cómodo con la plataforma, simplemente promueva cada componente, de uno en uno, a producción.

## <a name="the-anatomy-of-a-cyber-security-attack"></a>La anatomía de un ataque de ciberseguridad

Microsoft 365 Defender es un conjunto de defensa empresarial basado en la nube, unificado, previo y posterior a la vulneración. Coordina la *prevención*, *la detección*, *la investigación* y la *respuesta* entre puntos de conexión, identidades, aplicaciones, correo electrónico, aplicaciones de colaboración y todos sus datos.

En esta ilustración se está realizando un ataque. El correo electrónico de suplantación de identidad llega a la Bandeja de entrada de un empleado de su organización, que abre sin saberlo los datos adjuntos del correo electrónico. Esto instala malware, lo que conduce a una cadena de eventos que podrían terminar con el robo de datos confidenciales. Pero en este caso, Defender para Office 365 está en funcionamiento.

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="Los distintos intentos de ataque" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

En la ilustración:

- **Exchange Online Protection**, parte de Microsoft Defender para Office 365, puede detectar el correo electrónico de suplantación de identidad y usar reglas de flujo de correo para asegurarse de que nunca llega a la Bandeja de entrada.
- **Defender para Office 365** datos adjuntos seguros prueba los datos adjuntos y determina que son dañinos, por lo que el correo que llega no es accionable por el usuario o las directivas impiden que llegue el correo.
- **Defender para punto de conexión** administra los dispositivos que se conectan a la red corporativa y detectan vulnerabilidades de dispositivo y red que, de lo contrario, podrían aprovecharse.
- **Defender for Identity** toma nota de cambios repentinos en la cuenta, como la elevación de privilegios o el movimiento lateral de alto riesgo. También informa sobre problemas de identidad fácilmente explotados, como la delegación de Kerberos sin restricciones, para que el equipo de seguridad lo corrija.
- **Microsoft Defender for Cloud Apps** observa un comportamiento anómalo, como un viaje imposible, acceso a credenciales y una descarga inusual, un recurso compartido de archivos o una actividad de reenvío de correo, y los notifica al equipo de seguridad.

### <a name="microsoft-365-defender-components-secure-devices-identity-data-and-applications"></a>Microsoft 365 Defender componentes protegen dispositivos, identidades, datos y aplicaciones

Microsoft 365 Defender se compone de estas tecnologías de seguridad, que funcionan en tándem. No necesita todos estos componentes para beneficiarse de las funcionalidades de XDR y Microsoft 365 Defender. También obtendrá ganancias y eficiencias mediante el uso de uno o dos.

|Componente|Descripción|Material de referencia|
|---|---|---|
|Microsoft Defender for Identity|Microsoft Defender for Identity usa señales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades en peligro y acciones internas malintencionadas dirigidas a su organización.|[¿Qué es Microsoft Defender for Identity?](/defender-for-identity/what-is)|
|Exchange Online Protection|Exchange Online Protection es el servicio de filtrado y retransmisión SMTP basado en la nube nativo que ayuda a proteger su organización contra el correo no deseado y el malware.|[Introducción a Exchange Online Protection (EOP): Office 365](/microsoft-365/office-365-security/overview.md)|
|Microsoft Defender para Office 365|Microsoft Defender para Office 365 protege a su organización frente a amenazas malintencionadas planteadas por mensajes de correo electrónico, vínculos (DIRECCIONES URL) y herramientas de colaboración.|[Microsoft Defender para Office 365: Office 365](/microsoft-365/office-365-security/overview.md)|
|Microsoft Defender para punto de conexión|Microsoft Defender para punto de conexión es una plataforma unificada para la protección de dispositivos, la detección posterior a la vulneración, la investigación automatizada y la respuesta recomendada.|[Microsoft Defender para punto de conexión: seguridad de Windows](../defender-endpoint/microsoft-defender-endpoint.md)|
|Microsoft Defender for Cloud Apps|Microsoft Defender for Cloud Apps es una solución completa entre SaaS que ofrece visibilidad profunda, controles de datos seguros y protección contra amenazas mejorada para las aplicaciones en la nube.|[¿Qué es Defender for Cloud Apps?](/cloud-app-security/what-is-cloud-app-security)|
|Azure AD Identity Protection|Azure AD Identity Protection evalúa los datos de riesgo de miles de millones de intentos de inicio de sesión y usa estos datos para evaluar el riesgo de cada inicio de sesión en su entorno. Azure AD usa estos datos para permitir o impedir el acceso a la cuenta, en función de cómo se configuren las directivas de acceso condicional. Azure AD Identity Protection tiene licencia independiente de Microsoft 365 Defender. Se incluye con Azure Active Directory Premium P2.|[¿Qué es Identity Protection?](/azure/active-directory/identity-protection/overview-identity-protection)|
||||

## <a name="microsoft-365-defender-architecture"></a>arquitectura de Microsoft 365 Defender

En el diagrama siguiente se muestra la arquitectura de alto nivel para componentes clave Microsoft 365 Defender e integraciones. *A* lo largo de esta serie de artículos se proporciona una arquitectura detallada para cada componente de Defender y escenarios de casos de uso.

:::image type="content" source="../../media/defender/m365-defender-eval-architecture.png" alt-text="Una arquitectura de alto nivel del portal de Microsoft 365 Defender" lightbox="../../media/defender/m365-defender-eval-architecture.png":::

En esta ilustración:

- Microsoft 365 Defender combina las señales de todos los componentes de Defender para proporcionar una detección y respuesta extendidas (XDR) entre dominios. Esto incluye una cola de incidentes unificada, respuesta automatizada para detener ataques, recuperación automática (para dispositivos en peligro, identidades de usuario y buzones), búsqueda entre amenazas y análisis de amenazas.
- Microsoft Defender para Office 365 protege su organización contra las amenazas malintencionadas ocultas en mensajes de correo electrónico, vínculos (direcciones URL) y herramientas de colaboración. Comparte señales resultantes de estas actividades con Microsoft 365 Defender. Exchange Online Protection (EOP) está integrado para proporcionar protección de un extremo a otro para los correos electrónicos y datos adjuntos entrantes.
- Microsoft Defender for Identity recopila señales de servidores que ejecutan Servicios federados de Active Directory (AD FS) y Active Directory local Domain Services (AD DS). Usa estas señales para proteger el entorno de identidad híbrida, incluida la protección contra los hackers que usan cuentas en peligro para moverse lateralmente entre estaciones de trabajo en el entorno local.
- Microsoft Defender para punto de conexión recopila señales de y protege los dispositivos utilizados por su organización.
- Microsoft Defender for Cloud Apps recopila señales del uso que hace su organización de las aplicaciones en la nube y protege los datos que fluyen entre su entorno y estas aplicaciones, incluidas las aplicaciones en la nube autorizadas y no autorizadas.
- Azure AD Identity Protection evalúa los datos de riesgo de miles de millones de intentos de inicio de sesión y usa estos datos para evaluar el riesgo de cada inicio de sesión en su entorno. Azure AD usa estos datos para permitir o impedir el acceso a la cuenta, en función de cómo se configuren las directivas de acceso condicional. Azure AD Identity Protection tiene licencia independiente de Microsoft 365 Defender. Se incluye con Azure Active Directory Premium P2.

## <a name="microsoft-siem-and-soar-can-use-data-from-microsoft-365-defender"></a>Microsoft SIEM y SOAR pueden usar datos de Microsoft 365 Defender

Componentes de arquitectura opcionales adicionales no incluidos en esta ilustración:

- **Los datos detallados de señales de todos los componentes de Microsoft 365 Defender se pueden integrar en Microsoft Sentinel y combinarse** con otros orígenes de registro para ofrecer funcionalidades e información completas de SIEM y SOAR.
- **Para obtener más información sobre el uso de Microsoft Sentinel, un SIEM de Azure, con Microsoft 365 Defender** como XDR, eche un vistazo a este [artículo de información general](/azure/sentinel/microsoft-365-defender-sentinel-integration) y a los pasos de [integración](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE) de Microsoft Sentinel y Microsoft 365 Defender.
- Para obtener más información sobre SOAR en Microsoft Sentinel (incluidos los vínculos a cuadernos de estrategias en el repositorio de GitHub de Microsoft Sentinel), lea [este artículo](/azure/sentinel/automate-responses-with-playbooks).

## <a name="the-evaluation-process-for-microsoft-365-defender-cyber-security"></a>Proceso de evaluación de Microsoft 365 Defender ciberseguridad

Microsoft recomienda habilitar los componentes de Microsoft 365 en el orden que se muestra:

:::image type="content" source="../../media/defender/m365-defender-eval-process.png" alt-text="Un proceso de evaluación de alto nivel en el portal de Microsoft 365 Defender" lightbox="../../media/defender/m365-defender-eval-process.png":::

En la tabla siguiente se describe esta ilustración.

|  Número de serie   |Paso  |Descripción  |
|------|---------|---------|
|1     | [Creación del entorno de evaluación](eval-create-eval-environment.md)       |Este paso garantiza que tiene la licencia de prueba para Microsoft 365 Defender.         |
|2     | [Habilitación de Defender for Identity](eval-defender-identity-overview.md)        | Revise los requisitos de arquitectura, habilite la evaluación y recorra tutoriales para identificar y corregir diferentes tipos de ataque.   |
|3     | [Habilitar Defender para Office 365 ](eval-defender-office-365-overview.md)       | Asegúrese de cumplir los requisitos de arquitectura, habilite la evaluación y, a continuación, cree el entorno piloto. Este componente incluye Exchange Online Protection, por lo que realmente evaluará *ambos* aquí.      |
|4     | [Habilitación de Defender para punto de conexión ](eval-defender-endpoint-overview.md)       | Asegúrese de cumplir los requisitos de arquitectura, habilite la evaluación y, a continuación, cree el entorno piloto.         |
|5     | [Habilitar Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)        |  Asegúrese de cumplir los requisitos de arquitectura, habilite la evaluación y, a continuación, cree el entorno piloto.        |
|6     | [Investigar y responder a amenazas](eval-defender-investigate-respond.md)        |   Simular un ataque y empezar a usar funcionalidades de respuesta a incidentes.      |
|7      | [Promover la versión de prueba a producción](eval-defender-promote-to-production.md)        | Promover los componentes de Microsoft 365 a producción uno a uno.        |

Este es un orden comúnmente recomendado diseñado para aprovechar el valor de las funcionalidades rápidamente en función de cuánto esfuerzo se requiere normalmente para implementar y configurar las funcionalidades. Por ejemplo, Defender para Office 365 se pueden configurar en menos tiempo del necesario para inscribir dispositivos en Defender para punto de conexión. Por supuesto, debe priorizar los componentes para satisfacer sus necesidades empresariales y puede habilitarlos en un orden diferente.

## <a name="go-to-the-next-step"></a>Vaya al paso siguiente.

[Obtenga información sobre y/o cree el entorno de evaluación de Microsoft 365 Defender](eval-create-eval-environment.md)
