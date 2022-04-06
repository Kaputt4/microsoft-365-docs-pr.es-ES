---
title: 'Directivas recomendadas de Microsoft Defender para aplicaciones en la nube para aplicaciones SaaS: Microsoft 365 Enterprise | Microsoft Docs'
description: Describe las directivas recomendadas para la integración con Microsoft Defender para Aplicaciones en la nube.
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
ms.prod: m365-security
ms.openlocfilehash: 95b46e1c92354015ce6f8d9c5b1fa4b6e9642785
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683327"
---
# <a name="recommended-microsoft-defender-for-cloud-apps-policies-for-saas-apps"></a>Directivas recomendadas de Microsoft Defender for Cloud Apps para aplicaciones SaaS

Microsoft Defender para Aplicaciones en la nube se basa en directivas de acceso condicional de Azure AD para permitir la supervisión y el control en tiempo real de acciones granulares con aplicaciones SaaS, como bloquear descargas, cargas, copiar y pegar e imprimir. Esta característica agrega seguridad a las sesiones que conllevan riesgos inherentes, como cuando se accede a los recursos corporativos desde dispositivos no administrados o por usuarios invitados.

Defender for Cloud Apps también se integra de forma nativa con Microsoft Information Protection, lo que proporciona inspección de contenido en tiempo real para buscar datos confidenciales basados en tipos de información confidencial y etiquetas de confidencialidad y tomar las medidas adecuadas.

Esta guía incluye recomendaciones para estos escenarios:

- Llevar aplicaciones SaaS a la administración de IT
- Ajustar la protección para aplicaciones SaaS específicas
- Configurar la prevención de pérdida de datos (DLP) para ayudar a cumplir con las normativas de protección de datos

## <a name="bring-saas-apps-into-it-management"></a>Llevar aplicaciones SaaS a la administración de IT

El primer paso para usar Defender para aplicaciones en la nube para administrar aplicaciones SaaS consiste en detectarlas y, a continuación, agregarlas a Azure AD inquilino. Si necesitas ayuda con la detección, consulta [Descubrir y administrar aplicaciones SaaS en la red](/cloud-app-security/tutorial-shadow-it). Después de descubrir aplicaciones, [agrégrelos a su Azure AD inquilino](/azure/active-directory/manage-apps/add-application-portal).

Puede empezar a administrarlos haciendo lo siguiente:

1. Primero, en Azure AD, cree una nueva directiva de acceso condicional y configúrela para "Usar control de aplicaciones de acceso condicional". Esto redirige la solicitud a Defender para aplicaciones en la nube. Puedes crear una directiva y agregar todas las aplicaciones SaaS a esta directiva.
1. A continuación, en Defender para aplicaciones en la nube, cree directivas de sesión. Cree una directiva para cada control que desee aplicar.

Los permisos para aplicaciones SaaS suelen basarse en la necesidad empresarial de acceso a la aplicación. Estos permisos pueden ser muy dinámicos. El uso de directivas de Defender para aplicaciones en la nube garantiza la protección de los datos de la aplicación, independientemente de si los usuarios están asignados Azure AD un grupo asociado con la protección de seguridad especializada, empresarial o de punto de partida.

Para proteger los datos en toda la colección de aplicaciones SaaS, en el siguiente diagrama se muestra la directiva de acceso condicional Azure AD y las directivas sugeridas que puede crear en Defender for Cloud Apps. En este ejemplo, las directivas creadas en Defender para aplicaciones en la nube se aplican a todas las aplicaciones SaaS que se administran. Están diseñados para aplicar controles adecuados en función de si los dispositivos se administran, así como de las etiquetas de confidencialidad que ya se aplican a los archivos.

:::image type="content" source="../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png" alt-text="Directivas para administrar aplicaciones SaaS en Defender para aplicaciones en la nube." lightbox="../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png":::

En la tabla siguiente se muestra la nueva directiva de acceso condicional que debe crear en Azure AD.

|Nivel de protección|Directiva|Más información|
|---|---|---|
|Todos los niveles de protección|[Usar el control de aplicaciones de acceso condicional en Defender para aplicaciones en la nube](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|Esto configura el IdP (Azure AD) para que funcione con Defender para aplicaciones en la nube.|
||||

En esta tabla siguiente se enumeran las directivas de ejemplo ilustradas anteriormente que puede crear para proteger todas las aplicaciones SaaS. Asegúrese de evaluar sus propios objetivos de negocio, seguridad y cumplimiento y, a continuación, cree directivas que proporcionen la protección más adecuada para su entorno.

|Nivel de protección|Directiva|
|---|---|
|Punto de inicio|Supervisar el tráfico desde dispositivos no administrados <p> Agregar protección a descargas de archivos desde dispositivos no administrados|
|Empresa|Bloquear la descarga de archivos etiquetados con dispositivos confidenciales o clasificados desde dispositivos no administrados (esto solo proporciona acceso al explorador)|
|Seguridad especializada|Bloquear la descarga de archivos etiquetados con clasificados desde todos los dispositivos (esto solo proporciona acceso al explorador)|
|||

Para obtener instrucciones completas para configurar el Control de aplicaciones de acceso condicional, consulta Implementar control de aplicaciones de acceso [condicional para aplicaciones características](/cloud-app-security/proxy-deployment-aad). En este artículo se explica el proceso de creación de la directiva de acceso condicional necesaria en Azure AD pruebas de las aplicaciones SaaS.

Para obtener más información, consulta [Proteger aplicaciones con Microsoft Defender para el control de aplicaciones de acceso condicional de Aplicaciones en la nube](/cloud-app-security/proxy-intro-aad).

## <a name="tune-protection-for-specific-saas-apps"></a>Ajustar la protección para aplicaciones SaaS específicas

Es posible que quieras aplicar controles y supervisión adicionales a aplicaciones SaaS específicas de tu entorno. Defender para aplicaciones en la nube te permite hacerlo. Por ejemplo, si una aplicación como Box se usa en gran medida en el entorno, tiene sentido aplicar controles adicionales. O bien, si tu departamento jurídico o financiero usa una aplicación SaaS específica para datos empresariales confidenciales, puedes dirigirte a protección adicional a estas aplicaciones.

Por ejemplo, puede proteger el entorno box con estos tipos de plantillas de directiva de detección de anomalías integradas:

- Actividad desde direcciones IP anónimas
- Actividad desde países o regiones poco frecuentes
- Actividad desde direcciones IP sospechosas
- Desplazamiento imposible
- Actividad realizada por el usuario terminado (requiere AAD como IdP)
- Detección de malware
- Intentos de varios inicios de sesión fallidos
- Actividad de ransomware
- Risky Oauth App
- Actividad de recurso compartido de archivos inusual

Estos son ejemplos. Las plantillas de directiva adicionales se agregan de forma regular. Para obtener ejemplos de cómo aplicar protección adicional a aplicaciones específicas, consulta [Protección de aplicaciones conectadas](/cloud-app-security/protect-connected-apps).

[El modo en que Defender para aplicaciones en](/cloud-app-security/protect-box) la nube ayuda a proteger el entorno de Box muestra los tipos de controles que pueden ayudarle a proteger los datos empresariales en Box y otras aplicaciones con datos confidenciales.

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a>Configurar la prevención de pérdida de datos (DLP) para ayudar a cumplir con las normativas de protección de datos

Defender for Cloud Apps puede ser una herramienta valiosa para configurar la protección de las normativas de cumplimiento. En este caso, se crean directivas específicas para buscar datos específicos a los que se aplica un reglamento y configurar cada directiva para que tome las medidas adecuadas.

En la siguiente ilustración y tabla se proporcionan varios ejemplos de directivas que se pueden configurar para ayudar a cumplir con el Reglamento general de protección de datos (RGPD). En estos ejemplos, las directivas buscan datos específicos. En función de la confidencialidad de los datos, cada directiva está configurada para realizar las acciones adecuadas.

:::image type="content" source="../../media/microsoft-365-policies-configurations/mcas-dlp.png" alt-text="Ejemplo de directivas de Defender para Aplicaciones en la nube para la prevención de pérdida de datos." lightbox="../../media/microsoft-365-policies-configurations/mcas-dlp.png":::

|Nivel de protección|Directivas de ejemplo|
|---|---|
|Punto de inicio|Alerta cuando los archivos que contienen este tipo de información confidencial ("Número de tarjeta de crédito") se comparten fuera de la organización <p> >bloquear las descargas de archivos que contienen este tipo de información confidencial ("Número de tarjeta de crédito") a dispositivos no administrados|
|Empresa|Proteger las descargas de archivos que contienen este tipo de información confidencial ("Número de tarjeta de crédito") en dispositivos administrados <p> Bloquear descargas de archivos que contengan este tipo de información confidencial ("Número de tarjeta de crédito") en dispositivos no administrados <p> Alerta cuando se carga un archivo con estas etiquetas en OneDrive para la Empresa o Box (datos del cliente, recursos humanos: datos de salario, recursos humanos, datos de empleados)|
|Seguridad especializada|Alerta cuando los archivos con esta etiqueta ("Altamente clasificados") se descargan en dispositivos administrados <p> Bloquear descargas de archivos con esta etiqueta ("Altamente clasificados") en dispositivos no administrados|
|||

## <a name="next-steps"></a>Siguientes pasos

Para obtener más información acerca del uso de Defender para aplicaciones en la nube, consulta [la documentación de Microsoft Defender para Aplicaciones en la nube](//cloud-app-security/).
