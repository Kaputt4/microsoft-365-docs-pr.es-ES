---
title: Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar directivas dlp para aplicaciones en la nube que no son de Microsoft.
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649661"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft (versión preliminar)

Las directivas de prevención de pérdida de datos (DLP) para aplicaciones en la nube que no son de Microsoft forman parte del conjunto de características dlp de Microsoft 365; con estas características, puede detectar y proteger elementos confidenciales en los servicios de Microsoft 365. Para obtener más información acerca de todas las ofertas de DLP de Microsoft, vea [Información general sobre la prevención de pérdida de datos.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)

Puede usar directivas DLP para aplicaciones en la nube que no son de Microsoft para supervisar y detectar cuándo se usan y comparten elementos confidenciales a través de aplicaciones en la nube que no son de Microsoft. El uso de estas directivas le proporciona la visibilidad y el control que necesita para asegurarse de que se usan y protegen correctamente, y ayuda a evitar comportamientos de riesgo que puedan ponerlas en peligro.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Antes de empezar a usar directivas DLP para aplicaciones en la nube que no son de Microsoft, confirme su suscripción a [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y cualquier complemento. Para acceder a esta funcionalidad y usarla, debes tener una de estas suscripciones o complementos:

- Microsoft 365 E5
- Cumplimiento de Microsoft 365 E5
- Seguridad de Microsoft 365 E5

### <a name="prepare-your-cloud-app-security-environment"></a>Preparar el entorno de Cloud App Security

Las directivas DLP para aplicaciones en la nube que no son de Microsoft usan funcionalidades dlp de Cloud App Security. Para usarlo, debe preparar el entorno de Cloud App Security. Para obtener instrucciones, consulta [Establecer la visibilidad instantánea, la protección](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)y las acciones de gobierno para tus aplicaciones.

### <a name="connect-a-non-microsoft-cloud-app"></a>Conectar una aplicación en la nube que no es de Microsoft

Para usar la directiva DLP en una aplicación en la nube específica que no sea de Microsoft, la aplicación debe estar conectada a Cloud App Security. Para obtener información, consulte:

- [Cuadro Conectar](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Conectar Dropbox](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Conectar G-Suite](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Conectar Salesforce](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Conectar Cisco Webex](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Después de conectar las aplicaciones en la nube a Cloud App Security, puede crear directivas DLP de Microsoft 365 para ellas.

>[!NOTE]
>También es posible usar Microsoft Cloud App Security para crear directivas DLP para las aplicaciones en la nube de Microsoft. Sin embargo, se recomienda usar Microsoft 365 para crear y administrar directivas DLP en aplicaciones en la nube de Microsoft.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Crear una directiva DLP para una aplicación en la nube que no es de Microsoft

Cuando seleccione una ubicación para la directiva DLP, active la ubicación **de Microsoft Cloud App Security.**

- Para seleccionar una aplicación o instancia específica, seleccione **Elegir instancia.**
- Si no selecciona una instancia, la directiva usa todas las aplicaciones conectadas en el inquilino de Microsoft Cloud App Security.

   ![Ubicaciones para aplicar la directiva](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US y Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Puedes elegir varias acciones para cada aplicación en la nube compatible que no es de Microsoft. Para cada aplicación, hay diferentes acciones posibles (depende de la API de la aplicación en la nube).

![Crear regla](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Al crear una regla en la directiva DLP, puede seleccionar una acción para aplicaciones en la nube que no son de Microsoft. Para restringir aplicaciones de terceros, seleccione **Restringir aplicaciones de terceros.**

![Restringir aplicaciones de terceros](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

Para obtener información sobre cómo crear y configurar directivas DLP, vea [Crear pruebas y ajustar una directiva DLP.](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)

## <a name="see-also"></a>Vea también

- [Crear pruebas y ajustar una directiva DLP](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [Introducción a la directiva predeterminada de DLP](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [Crear una directiva DLP desde una plantilla](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
