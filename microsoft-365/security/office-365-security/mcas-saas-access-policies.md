---
title: 'Directivas recomendadas de Microsoft Cloud App Security para aplicaciones SaaS: Microsoft 365 Enterprise | Microsoft Docs'
description: Describe las directivas recomendadas para la integración con Microsoft Cloud App Security.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 414d6ae0586078551c737e45763ea665d5eec4e6
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939559"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a>Directivas recomendadas de Microsoft Cloud App Security para aplicaciones SaaS
Microsoft Cloud App Security se basa en directivas de acceso condicional de Azure AD para permitir la supervisión y el control en tiempo real de acciones granulares con aplicaciones SaaS, como bloquear descargas, cargas, copiar y pegar e imprimir. Esta característica agrega seguridad a las sesiones que conllevan riesgos inherentes, como cuando se accede a los recursos corporativos desde dispositivos no administrados o por usuarios invitados.

Microsoft Cloud App Security también se integra de forma nativa con Microsoft Information Protection, lo que proporciona inspección de contenido en tiempo real para buscar datos confidenciales basados en tipos de información confidencial y etiquetas de confidencialidad y tomar las medidas adecuadas.

Esta guía incluye recomendaciones para estos escenarios:

- Llevar aplicaciones SaaS a la administración de IT
- Ajustar la protección para aplicaciones SaaS específicas
- Configurar la prevención de pérdida de datos (DLP) para ayudar a cumplir con las normativas de protección de datos

## <a name="bring-saas-apps-into-it-management"></a>Llevar aplicaciones SaaS a la administración de IT

El primer paso para usar Microsoft Cloud App Security para administrar aplicaciones SaaS es descubrirlas y luego agregarlas al inquilino de Azure AD. Si necesitas ayuda con la detección, consulta [Descubrir y administrar aplicaciones SaaS en la red.](/cloud-app-security/tutorial-shadow-it) Después de descubrir aplicaciones, [agrégrelos a su inquilino de Azure AD](/azure/active-directory/manage-apps/add-application-portal).

Puede empezar a administrarlos haciendo lo siguiente:

1. En primer lugar, en Azure AD, cree una nueva directiva de acceso condicional y configúrela para "Usar control de aplicaciones de acceso condicional". Esto redirige la solicitud a Cloud App Security. Puedes crear una directiva y agregar todas las aplicaciones SaaS a esta directiva.
1. A continuación, en Cloud App Security, cree directivas de sesión. Cree una directiva para cada control que desee aplicar.

Los permisos para aplicaciones SaaS suelen basarse en la necesidad empresarial de acceso a la aplicación. Estos permisos pueden ser muy dinámicos. El uso de directivas de Cloud App Security garantiza la protección de los datos de la aplicación, independientemente de si los usuarios están asignados a un grupo de Azure AD asociado con la protección de línea base, confidencial o altamente regulada.

Para proteger los datos en toda la colección de aplicaciones SaaS, en el siguiente diagrama se muestra la directiva de acceso condicional de Azure AD necesaria y las directivas sugeridas que puede crear en Cloud App Security. En este ejemplo, las directivas creadas en Cloud App Security se aplican a todas las aplicaciones SaaS que se administran. Están diseñados para aplicar controles adecuados en función de si los dispositivos se administran, así como de las etiquetas de confidencialidad que ya se aplican a los archivos.

![Directivas para administrar aplicaciones SaaS en Cloud App Security](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

En la tabla siguiente se muestra la nueva directiva de acceso condicional que debe crear en Azure AD.

|Nivel de protección|Policy|Más información|
|---|---|---|
|Todos los niveles de protección|[Usar el control de aplicaciones de acceso condicional en Cloud App Security](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|Esto configura el IdP (Azure AD) para que funcione con Cloud App Security.|
||||

En esta tabla siguiente se enumeran las directivas de ejemplo ilustradas anteriormente que puede crear para proteger todas las aplicaciones SaaS. Asegúrese de evaluar sus propios objetivos de negocio, seguridad y cumplimiento y, a continuación, cree directivas que proporcionen la protección más adecuada para su entorno.

|Nivel de protección|Policy|
|---|---|
|Línea base|Supervisar el tráfico desde dispositivos no administrados <p> Agregar protección a descargas de archivos desde dispositivos no administrados|
|Confidencial|Bloquear la descarga de archivos etiquetados con dispositivos confidenciales o clasificados desde dispositivos no administrados (esto solo proporciona acceso al explorador)|
|Extremadamente regulado|Bloquear la descarga de archivos etiquetados con clasificados desde todos los dispositivos (esto solo proporciona acceso al explorador)|
|||

Para obtener instrucciones de extremo a extremo para configurar el control de aplicaciones de acceso condicional, vea [Deploy Conditional Access App Control for featured apps](/cloud-app-security/proxy-deployment-aad). En este artículo se explica el proceso de creación de la directiva de acceso condicional necesaria en Azure AD y la prueba de las aplicaciones SaaS.

Para obtener más información, vea [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).

## <a name="tune-protection-for-specific-saas-apps"></a>Ajustar la protección para aplicaciones SaaS específicas

Es posible que quieras aplicar controles y supervisión adicionales a aplicaciones SaaS específicas de tu entorno. Cloud App Security te permite hacerlo. Por ejemplo, si una aplicación como Box se usa en gran medida en el entorno, tiene sentido aplicar controles adicionales. O bien, si tu departamento jurídico o financiero usa una aplicación SaaS específica para datos empresariales confidenciales, puedes dirigirte a protección adicional a estas aplicaciones.

Por ejemplo, puede proteger el entorno box con estos tipos de plantillas de directiva de detección de anomalías integradas:

- Actividad desde direcciones IP anónimas
- Actividad de un país poco frecuente
- Actividad desde direcciones IP sospechosas
- Desplazamiento imposible
- Actividad realizada por el usuario terminado (requiere AAD como IdP)
- Detección de malware
- Varios intentos de inicio de sesión con errores
- Actividad ransomware
- Risky Oauth App
- Actividad de recurso compartido de archivos inusual

Estos son ejemplos. Las plantillas de directiva adicionales se agregan de forma regular. Para obtener ejemplos de cómo aplicar protección adicional a aplicaciones específicas, consulta [Protección de aplicaciones conectadas.](/cloud-app-security/protect-connected-apps)

[La forma en](/cloud-app-security/protect-box) que Cloud App Security ayuda a proteger el entorno de Box muestra los tipos de controles que pueden ayudarle a proteger los datos empresariales en Box y otras aplicaciones con datos confidenciales.

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a>Configurar la prevención de pérdida de datos (DLP) para ayudar a cumplir con las normativas de protección de datos

Cloud App Security puede ser una herramienta valiosa para configurar la protección de las normativas de cumplimiento. En este caso, se crean directivas específicas para buscar datos específicos a los que se aplica un reglamento y configurar cada directiva para que tome las medidas adecuadas.

En la siguiente ilustración y tabla se proporcionan varios ejemplos de directivas que se pueden configurar para ayudar a cumplir con el Reglamento general de protección de datos (RGPD). En estos ejemplos, las directivas buscan datos específicos. En función de la confidencialidad de los datos, cada directiva está configurada para realizar las acciones adecuadas.

![Ejemplo de directivas de Cloud App Security para la prevención de pérdida de datos](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|Nivel de protección|Directivas de ejemplo|
|---|---|
|Línea base|Alerta cuando los archivos que contienen este tipo de información confidencial ("Número de tarjeta de crédito") se comparten fuera de la organización <p> >bloquear las descargas de archivos que contienen este tipo de información confidencial ("Número de tarjeta de crédito") a dispositivos no administrados|
|Confidencial|Proteger las descargas de archivos que contienen este tipo de información confidencial ("Número de tarjeta de crédito") en dispositivos administrados <p> Bloquear descargas de archivos que contengan este tipo de información confidencial ("Número de tarjeta de crédito") en dispositivos no administrados <p> Alerta cuando se carga un archivo con estas etiquetas en OneDrive para la Empresa o Box (datos del cliente, recursos humanos: datos de salario, recursos humanos, datos de empleados)|
|Extremadamente regulado|Alerta cuando los archivos con esta etiqueta ("Altamente clasificados") se descargan en dispositivos administrados <p> Bloquear descargas de archivos con esta etiqueta ("Altamente clasificados") en dispositivos no administrados|
|||

## <a name="next-steps"></a>Siguientes pasos

Para obtener más información acerca del uso de Cloud App Security, consulte [la documentación de Microsoft Cloud App Security](//cloud-app-security/).
