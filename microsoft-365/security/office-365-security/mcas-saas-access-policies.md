---
title: 'Directivas de Microsoft Defender for Cloud Apps recomendadas para aplicaciones SaaS: Microsoft 365 Enterprise | Microsoft Docs'
description: Describe las directivas recomendadas para la integración con Microsoft Defender for Cloud Apps.
author: BrendaCarter
manager: laurawi
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- zerotrust-solution
ms.prod: m365-security
ms.openlocfilehash: 3a0c5b3cbc34bf24c04a476091e3dc08b0655a74
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "66750262"
---
# <a name="recommended-microsoft-defender-for-cloud-apps-policies-for-saas-apps"></a>Directivas recomendadas de Microsoft Defender for Cloud Apps para aplicaciones SaaS

Microsoft Defender for Cloud Apps se basa en directivas de acceso condicional de Azure AD para permitir la supervisión y el control en tiempo real de acciones granulares con aplicaciones SaaS, como bloquear descargas, cargas, copiar y pegar e imprimir. Esta característica agrega seguridad a las sesiones que conllevan riesgos inherentes, como cuando se accede a los recursos corporativos desde dispositivos no administrados o usuarios invitados.

Defender for Cloud Apps también se integra de forma nativa con Microsoft Purview Information Protection, lo que proporciona inspección de contenido en tiempo real para buscar datos confidenciales basados en tipos de información confidencial y etiquetas de confidencialidad y para tomar las medidas adecuadas.

En esta guía se incluyen recomendaciones para estos escenarios:

- Incorporación de aplicaciones SaaS a la administración de TI
- Ajuste de la protección para aplicaciones SaaS específicas
- Configuración de la prevención de pérdida de datos (DLP) de Microsoft Purview para ayudar a cumplir con las normativas de protección de datos

## <a name="bring-saas-apps-into-it-management"></a>Incorporación de aplicaciones SaaS a la administración de TI

El primer paso para usar Defender for Cloud Apps para administrar aplicaciones SaaS es detectarlas y agregarlas a su inquilino de Azure AD. Si necesita ayuda con la detección, consulte [Detección y administración de aplicaciones SaaS en la red](/cloud-app-security/tutorial-shadow-it). Una vez que haya detectado aplicaciones, [agréguelas al inquilino de Azure AD](/azure/active-directory/manage-apps/add-application-portal).

Puede empezar a administrarlos haciendo lo siguiente:

1. En primer lugar, en Azure AD, cree una nueva directiva de acceso condicional y configúrela para "Usar el control de aplicaciones de acceso condicional". Esto redirige la solicitud a Defender for Cloud Apps. Puede crear una directiva y agregar todas las aplicaciones SaaS a esta directiva.
1. A continuación, en Defender for Cloud Apps, cree directivas de sesión. Cree una directiva para cada control que quiera aplicar.

Los permisos para las aplicaciones SaaS suelen basarse en la necesidad empresarial de acceso a la aplicación. Estos permisos pueden ser muy dinámicos. El uso de directivas de Defender for Cloud Apps garantiza la protección de los datos de la aplicación, independientemente de si los usuarios están asignados a un grupo de Azure AD asociado con el punto de partida, la empresa o la protección de seguridad especializada.

Para proteger los datos de la colección de aplicaciones SaaS, en el diagrama siguiente se muestra la directiva de acceso condicional de Azure AD necesaria y las directivas sugeridas que puede crear en Defender for Cloud Apps. En este ejemplo, las directivas creadas en Defender for Cloud Apps se aplican a todas las aplicaciones SaaS que administra. Están diseñados para aplicar los controles adecuados en función de si los dispositivos se administran, así como las etiquetas de confidencialidad que ya se aplican a los archivos.

:::image type="content" source="../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png" alt-text="Directivas para administrar aplicaciones SaaS en Defender for Cloud Apps" lightbox="../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png":::

En la tabla siguiente se muestra la nueva directiva de acceso condicional que debe crear en Azure AD.

|Nivel de protección|Policy|Más información|
|---|---|---|
|Todos los niveles de protección|[Uso del control de aplicaciones de acceso condicional en Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|Esto configura el IdP (Azure AD) para que funcione con Defender for Cloud Apps.|
||||

En esta tabla siguiente se enumeran las directivas de ejemplo mostradas anteriormente que puede crear para proteger todas las aplicaciones SaaS. Asegúrese de evaluar sus propios objetivos de negocio, seguridad y cumplimiento y, a continuación, cree directivas que proporcionen la protección más adecuada para su entorno.

|Nivel de protección|Policy|
|---|---|
|Punto de inicio|Supervisión del tráfico desde dispositivos no administrados <p> Adición de protección a las descargas de archivos desde dispositivos no administrados|
|Enterprise|Bloquear la descarga de archivos etiquetados con información confidencial o clasificada desde dispositivos no administrados (esto solo proporciona acceso al explorador)|
|Seguridad especializada|Bloquear la descarga de archivos etiquetados con clasificados desde todos los dispositivos (esto solo proporciona acceso al explorador)|
|||

Para obtener instrucciones de un extremo a otro para configurar el control de aplicaciones de acceso condicional, consulte [Implementación del control de aplicaciones de acceso condicional para aplicaciones destacadas](/cloud-app-security/proxy-deployment-aad). Este artículo le guiará a través del proceso de creación de la directiva de acceso condicional necesaria en Azure AD y pruebas de las aplicaciones SaaS.

Para obtener más información, consulte [Protección de aplicaciones con Microsoft Defender for Cloud Apps control de aplicaciones de acceso condicional](/cloud-app-security/proxy-intro-aad).

## <a name="tune-protection-for-specific-saas-apps"></a>Ajuste de la protección para aplicaciones SaaS específicas

Es posible que quiera aplicar controles y supervisión adicionales a aplicaciones SaaS específicas en su entorno. Defender for Cloud Apps le permite lograr esto. Por ejemplo, si una aplicación como Box se usa en gran medida en su entorno, tiene sentido aplicar controles adicionales. O bien, si el departamento jurídico o financiero usa una aplicación SaaS específica para datos empresariales confidenciales, puede destinar protección adicional a estas aplicaciones.

Por ejemplo, puede proteger el entorno de Box con estos tipos de plantillas de directivas de detección de anomalías integradas:

- Actividad desde direcciones IP anónimas
- Actividad desde países o regiones poco frecuentes
- Actividad desde direcciones IP sospechosas
- Desplazamiento imposible
- Actividad realizada por el usuario terminado (requiere AAD como IdP)
- Detección de malware
- Intentos de varios inicios de sesión fallidos
- Actividad de ransomware
- Aplicación de Oauth de riesgo
- Actividad de recurso compartido de archivos inusual

Estos son ejemplos. Las plantillas de directiva adicionales se agregan periódicamente. Para obtener ejemplos de cómo aplicar protección adicional a aplicaciones específicas, consulte [Protección de aplicaciones conectadas](/cloud-app-security/protect-connected-apps).

[Cómo Defender for Cloud Apps ayuda a proteger el entorno de Box](/cloud-app-security/protect-box) muestra los tipos de controles que pueden ayudarle a proteger los datos empresariales en Box y otras aplicaciones con datos confidenciales.

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a>Configuración de la prevención de pérdida de datos (DLP) para ayudar a cumplir con las normativas de protección de datos

Defender for Cloud Apps puede ser una herramienta valiosa para configurar la protección para las normativas de cumplimiento. En este caso, creará directivas específicas para buscar datos específicos a los que se aplica un reglamento y configurar cada directiva para que tome las medidas adecuadas.

En la siguiente ilustración y tabla se proporcionan varios ejemplos de directivas que se pueden configurar para ayudar a cumplir con el Reglamento general de protección de datos (RGPD). En estos ejemplos, las directivas buscan datos específicos. En función de la confidencialidad de los datos, cada directiva está configurada para realizar las acciones adecuadas.

:::image type="content" source="../../media/microsoft-365-policies-configurations/mcas-dlp.png" alt-text="Página Directivas de Defender for Cloud Apps para la prevención de pérdida de datos" lightbox="../../media/microsoft-365-policies-configurations/mcas-dlp.png":::

|Nivel de protección|Directivas de ejemplo|
|---|---|
|Punto de inicio|Alerta cuando los archivos que contienen este tipo de información confidencial ("Número de tarjeta de crédito") se comparten fuera de la organización <p> >Bloquear descargas de archivos que contienen este tipo de información confidencial ("Número de tarjeta de crédito") en dispositivos no administrados|
|Enterprise|Protección de descargas de archivos que contienen este tipo de información confidencial ("número de tarjeta de crédito") en dispositivos administrados <p> Bloquear las descargas de archivos que contienen este tipo de información confidencial ("número de tarjeta de crédito") en dispositivos no administrados <p> Alerta cuando se carga un archivo con en estas etiquetas en OneDrive para la Empresa o Box (datos de clientes, recursos humanos: datos de salarios, recursos humanos, datos de empleados)|
|Seguridad especializada|Alerta cuando los archivos con esta etiqueta ("Altamente clasificados") se descargan en dispositivos administrados <p> Bloquear descargas de archivos con esta etiqueta ("Altamente clasificados") en dispositivos no administrados|
|||

## <a name="next-steps"></a>Siguientes pasos

Para obtener más información sobre el uso de Defender for Cloud Apps, consulte [Microsoft Defender for Cloud Apps documentación](/defender-cloud-apps/).
