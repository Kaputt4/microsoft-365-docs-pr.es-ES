---
title: Evaluar y piloto Microsoft 365 Defender, una solución XDR
description: ¿Qué es la seguridad XDR? ¿Cómo puede evaluar un XDR de Microsoft en Microsoft 365 Defender? Use esta serie de blogs para planear Microsoft 365 Defender laboratorio de prueba o entorno piloto para probar y probar una solución de seguridad diseñada para proteger dispositivos, identidad, datos y aplicaciones. Inicia aquí tu viaje de seguridad cibernética de XDR y lleva esa prueba a la producción.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 06/25/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f7830bb25f2572c43d665d059e0a36bc1fdaa172
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500791"
---
# <a name="evaluate-and-pilot-microsoft-365-defender"></a>Evaluar Microsoft 365 Defender y realizar una prueba piloto

**Se aplica a:**

- Microsoft 365 Defender

## <a name="how-this-article-series-works"></a>Cómo funciona esta serie de artículos

Esta serie de artículos está diseñada para pasar por todo el proceso de configuración de un entorno XDR de *prueba, de* un extremo a otro, para que pueda evaluar las características y capacidades de Microsoft 365 Defender e incluso promover el entorno de evaluación directamente a la producción cuando y si está listo.

Si es nuevo en pensar en XDR, puede examinar estos 7 artículos vinculados para obtener una idea de lo completa que es la solución.

- [Cómo crear el entorno](eval-create-eval-environment.md)
- Configurar o aprender sobre cada tecnología de este XDR de Microsoft
  - [Microsoft Defender for Identity](eval-defender-identity-overview.md)
  - [Microsoft Defender para Office](eval-defender-office-365-overview.md)
  - [Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)
  - [Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)
- [Cómo investigar y responder con este XDR](eval-defender-investigate-respond.md)
- [Promover el entorno de prueba a la producción](eval-defender-promote-to-production.md)

## <a name="microsoft-365-defender-is-a-microsoft-xdr-cyber-security-solution"></a>Microsoft 365 Defender es una solución de seguridad cibernética de Microsoft XDR

Microsoft 365 Defender es una solución de detección y respuesta **de eXtended (XDR)** que recopila, correlaciona y analiza automáticamente datos de señales, amenazas y alertas de todo el entorno  de Microsoft 365, incluidos puntos de conexión, correo electrónico *,* aplicaciones e identidades. Aprovecha la inteligencia artificial (IA) y la automatización para  detener automáticamente los ataques y corregir los activos afectados en un estado seguro.

Piense en XDR como el siguiente paso en seguridad, unificando punto de conexión (detección y respuesta de puntos de conexión o EDR), correo electrónico, aplicación e identidad en un solo lugar.

## <a name="microsoft-recommendations-for-evaluating-microsoft-365-defender"></a>Recomendaciones de Microsoft para evaluar Microsoft 365 Defender

Microsoft recomienda crear la evaluación en una suscripción de producción existente de Office 365. De esta forma obtendrá información del mundo real inmediatamente y podrá ajustar la configuración para que funcione contra las amenazas actuales en su entorno. Una vez que haya adquirido experiencia y se sienta cómodo con la plataforma, simplemente promueva cada componente, uno a la vez, a la producción.

## <a name="the-anatomy-of-a-cyber-security-attack"></a>La anatomía de un ataque de ciberseguridad

Microsoft 365 Defender es un conjunto de defensa empresarial basado en la nube, unificado, previo y posterior a la infracción. Coordina *prevención*, *detección*, *investigación* y  respuesta entre puntos de conexión, identidades, aplicaciones, correo electrónico, aplicaciones de colaboración y todos sus datos.

En esta ilustración se está en curso un ataque. El correo electrónico de suplantación de identidad (phishing) llega a la Bandeja de entrada de un empleado de la organización, que abre sin conocimiento los datos adjuntos del correo electrónico. Esto instala malware, lo que lleva a una cadena de eventos que podrían terminar con el robo de datos confidenciales. Pero en este caso, Defender para Office 365 está en funcionamiento.

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="Los distintos intentos de ataque" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

En la ilustración:

- **Exchange Online Protection**, parte de Microsoft Defender para Office 365, puede detectar el correo electrónico de suplantación de identidad y usar reglas de flujo de correo para asegurarse de que nunca llega a la Bandeja de entrada.
- **Defender for Office 365** safe attachments tests the attachment and determines it is harmful, so the mail that arrives either isn't actionable by the user, or policies prevent the mail from arriving at all.
- **Defender for Endpoint** administra los dispositivos que se conectan a la red corporativa y detectan vulnerabilidades de dispositivo y red que de otro modo podrían aprovecharse.
- **Defender for Identity toma nota de** los cambios repentinos en la cuenta, como la escalada de privilegios o el movimiento lateral de alto riesgo. También informa sobre problemas de identidad explotados fácilmente, como la delegación Kerberos sin restricciones, para su corrección por parte del equipo de seguridad.
- **Microsoft Defender para Aplicaciones** en la nube observa comportamientos anómalos como viajes imposibles, acceso a credenciales y descarga inusual, recurso compartido de archivos o actividad de reenvío de correo e informa al equipo de seguridad.

### <a name="microsoft-365-defender-components-secure-devices-identity-data-and-applications"></a>Microsoft 365 Defender protegen dispositivos, identidad, datos y aplicaciones

Microsoft 365 Defender está hecho de estas tecnologías de seguridad, que funcionan en tándem. No necesita todos estos componentes para beneficiarse de las capacidades de XDR y Microsoft 365 Defender. También se obtienen ganancias y eficiencias mediante el uso de uno o dos.

|Componente|Descripción|Material de referencia|
|---|---|---|
|Microsoft Defender for Identity|Microsoft Defender for Identity usa señales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones malintencionadas dirigidas a su organización.|[¿Qué es Microsoft Defender for Identity?](/defender-for-identity/what-is)|
|Exchange Online Protection|Exchange Online Protection es el servicio de filtrado y retransmisión SMTP basado en la nube nativo que ayuda a proteger su organización contra correo no deseado y malware.|[Exchange Online Protection (EOP): Office 365](../office-365-security/overview.md)|
|Microsoft Defender para Office 365|Microsoft Defender para Office 365 protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración.|[Microsoft Defender para Office 365: Office 365](../office-365-security/overview.md)|
|Microsoft Defender para punto de conexión|Microsoft Defender para endpoint es una plataforma unificada para la protección de dispositivos, la detección posterior a la infracción, la investigación automatizada y la respuesta recomendada.|[Microsoft Defender para endpoint: Windows seguridad](../defender-endpoint/microsoft-defender-endpoint.md)|
|Microsoft Defender for Cloud Apps|Microsoft Defender para aplicaciones en la nube es una solución completa entre SaaS que ofrece una visibilidad profunda, controles de datos sólidos y una protección contra amenazas mejorada para las aplicaciones en la nube.|[¿Qué es Defender for Cloud Apps?](/cloud-app-security/what-is-cloud-app-security)|
|Azure AD Identity Protection|Azure AD Identity Protection evalúa los datos de riesgo de miles de millones de intentos de inicio de sesión y usa estos datos para evaluar el riesgo de cada inicio de sesión en el entorno. Estos datos los usa Azure AD permitir o impedir el acceso a la cuenta, en función de cómo se configuren las directivas de acceso condicional. Azure AD Identity Protection se concede una licencia independiente de Microsoft 365 Defender. Se incluye con Azure Active Directory Premium P2.|[¿Qué es la protección de identidades?](/azure/active-directory/identity-protection/overview-identity-protection)|
||||

## <a name="microsoft-365-defender-architecture"></a>Microsoft 365 Defender arquitectura

En el siguiente diagrama se muestra la arquitectura de alto nivel para las Microsoft 365 Defender componentes e integraciones clave. *La arquitectura* detallada de cada componente de Defender y los escenarios de caso de uso se dan a lo largo de esta serie de artículos.

:::image type="content" source="../../media/defender/m365-defender-eval-architecture.png" alt-text="Una arquitectura de alto nivel del portal Microsoft 365 Defender web" lightbox="../../media/defender/m365-defender-eval-architecture.png":::

En esta ilustración:

- Microsoft 365 Defender combina las señales de todos los componentes de Defender para proporcionar una detección y respuesta extendidas (XDR) entre dominios. Esto incluye una cola de incidentes unificada, respuesta automatizada para detener ataques, recuperación automática (para dispositivos en peligro, identidades de usuario y buzones), búsqueda entre amenazas y análisis de amenazas.
- Microsoft Defender para Office 365 protege su organización contra las amenazas malintencionadas ocultas en mensajes de correo electrónico, vínculos (direcciones URL) y herramientas de colaboración. Comparte las señales resultantes de estas actividades con Microsoft 365 Defender. Exchange Online Protection (EOP) se integra para proporcionar protección de extremo a extremo para correos electrónicos y datos adjuntos entrantes.
- Microsoft Defender for Identity recopila señales de servidores que ejecutan servicios federados de Active Directory (AD FS) y servicios de dominio de Active Directory locales (AD DS). Usa estas señales para proteger su entorno de identidad híbrida, incluida la protección contra los hackers que usan cuentas comprometidas para moverse lateralmente entre las estaciones de trabajo del entorno local.
- Microsoft Defender para endpoint recopila señales de y protege los dispositivos usados por la organización.
- Microsoft Defender para aplicaciones en la nube recopila señales del uso de aplicaciones en la nube por parte de la organización y protege los datos que fluyen entre el entorno y estas aplicaciones, incluidas las aplicaciones en la nube sancionadas y no aprobadas.
- Azure AD Identity Protection evalúa los datos de riesgo de miles de millones de intentos de inicio de sesión y usa estos datos para evaluar el riesgo de cada inicio de sesión en el entorno. Estos datos los usa Azure AD permitir o impedir el acceso a la cuenta, en función de cómo se configuren las directivas de acceso condicional. Azure AD Identity Protection se concede una licencia independiente de Microsoft 365 Defender. Se incluye con Azure Active Directory Premium P2.

## <a name="microsoft-siem-and-soar-can-use-data-from-microsoft-365-defender"></a>Microsoft SIEM y SOAR pueden usar datos de Microsoft 365 Defender

Otros componentes de arquitectura opcionales no incluidos en esta ilustración:

- **Los datos de señal** detallados de todos los componentes Microsoft 365 Defender se pueden integrar en Microsoft Sentinel y combinarse con otros orígenes de registro para ofrecer capacidades e información completas de SIEM y SOAR.
- Para obtener más información sobre el uso de **Microsoft Sentinel, un SIEM de Azure, con Microsoft 365 Defender** como XDR, echa un vistazo a [](/azure/sentinel/microsoft-365-defender-sentinel-integration) este artículo de información general y a los pasos de integración de Microsoft Sentinel y Microsoft 365 Defender [web](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE).
- Para obtener más información sobre SOAR en Microsoft Sentinel (incluidos los vínculos a libros de reproducción en el repositorio de microsoft sentinel GitHub), lea [este artículo](/azure/sentinel/automate-responses-with-playbooks).

## <a name="the-evaluation-process-for-microsoft-365-defender-cyber-security"></a>El proceso de evaluación para Microsoft 365 Defender ciberseguridad

Microsoft recomienda habilitar los componentes de Microsoft 365 en el orden ilustrado:

:::image type="content" source="../../media/defender/m365-defender-eval-process.png" alt-text="Un proceso de evaluación de alto nivel en el portal Microsoft 365 Defender web" lightbox="../../media/defender/m365-defender-eval-process.png":::

En la tabla siguiente se describe esta ilustración.

|  Número de serie   |Paso  |Descripción  |
|------|---------|---------|
|1     | [Crear el entorno de evaluación](eval-create-eval-environment.md)       |Este paso garantiza que tiene la licencia de prueba para Microsoft 365 Defender.         |
|2     | [Habilitar Defender para la identidad](eval-defender-identity-overview.md)        | Revise los requisitos de arquitectura, habilite la evaluación y consulte tutoriales para identificar y corregir diferentes tipos de ataques.   |
|3     | [Habilitar Defender para Office 365 ](eval-defender-office-365-overview.md)       | Asegúrese de que cumple los requisitos de arquitectura, habilite la evaluación y, a continuación, cree el entorno piloto. Este componente incluye Exchange Online Protection por lo que realmente evaluará *ambos* aquí.      |
|4     | [Habilitar Defender para el extremo ](eval-defender-endpoint-overview.md)       | Asegúrese de que cumple los requisitos de arquitectura, habilite la evaluación y, a continuación, cree el entorno piloto.         |
|5     | [Habilitar Microsoft Defender para aplicaciones en la nube](eval-defender-mcas-overview.md)        |  Asegúrese de que cumple los requisitos de arquitectura, habilite la evaluación y, a continuación, cree el entorno piloto.        |
|6      | [Investigar y responder a amenazas](eval-defender-investigate-respond.md)        |   Simular un ataque y empezar a usar las capacidades de respuesta a incidentes.      |
|7      | [Promover la versión de prueba a producción](eval-defender-promote-to-production.md)        | Promover los Microsoft 365 componentes de producción uno a uno.        |

Este es un orden comúnmente recomendado diseñado para aprovechar el valor de las capacidades rápidamente en función del esfuerzo que normalmente se requiere para implementar y configurar las capacidades. Por ejemplo, Defender para Office 365 puede configurarse en menos tiempo del necesario para inscribir dispositivos en Defender para endpoint. Por supuesto, debe priorizar los componentes para satisfacer sus necesidades empresariales y habilitar estos en un orden diferente.

## <a name="go-to-the-next-step"></a>Ir al paso siguiente

[Obtenga información sobre y/o cree el entorno Microsoft 365 Defender evaluación](eval-create-eval-environment.md)
