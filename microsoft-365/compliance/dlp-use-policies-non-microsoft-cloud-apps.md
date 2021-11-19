---
title: Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft
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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Aprende a usar directivas de dlp para aplicaciones en la nube que no son de Microsoft.
ms.openlocfilehash: b374f9b85d41b6dd6a5281e17347dffd414361da
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61109784"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a>Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft

Las directivas de prevención de pérdida de datos (DLP) para aplicaciones en la nube que no son de Microsoft forman parte del conjunto de características dlp de Microsoft 365; con estas características, puede detectar y proteger elementos confidenciales en Microsoft 365 servicios. Para obtener más información acerca de todas las ofertas de DLP de Microsoft, vea [Learn about data loss prevention](dlp-learn-about-dlp.md).

Puedes usar directivas DLP en aplicaciones en la nube que no son de Microsoft para supervisar y detectar cuándo se usan y comparten elementos confidenciales a través de aplicaciones en la nube que no son de Microsoft. El uso de estas directivas le proporciona la visibilidad y el control que necesita para asegurarse de que se usan y protegen correctamente, y ayuda a evitar comportamientos de riesgo que puedan ponerlas en peligro.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Antes de empezar a usar directivas DLP en aplicaciones en la nube que no son de Microsoft, confirme su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y los complementos. Para acceder y usar esta funcionalidad, debe tener una de estas suscripciones o complementos:

- Microsoft 365 E5
- Cumplimiento de Microsoft 365 E5
- Seguridad de Microsoft 365 E5

### <a name="permissions"></a>Permisos
El usuario que crea la directiva DLP debe ser:

- Administrador global
- Administrador de cumplimiento: asignar en Azure AD
- Administrador de datos de cumplimiento: asignar en Azure AD

### <a name="prepare-your-defender-for-cloud-apps-environment"></a>Preparar el entorno de Defender para Aplicaciones en la nube

Las directivas DLP para aplicaciones en la nube que no son de Microsoft usan las funcionalidades dlp de Defender para aplicaciones en la nube. Para usarlo, debes preparar el entorno de Defender para Aplicaciones en la nube. Para obtener instrucciones, consulta [Establecer acciones de visibilidad instantánea, protección](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)y gobierno para tus aplicaciones.

### <a name="connect-a-non-microsoft-cloud-app"></a>Conectar una aplicación en la nube que no es microsoft

Para usar la directiva DLP en una aplicación en la nube específica que no sea de Microsoft, la aplicación debe conectarse a Defender para aplicaciones en la nube. Para obtener información, consulte:

- [Conectar box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Conectar Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Conectar G-Workspace](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Conectar Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Conectar Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Después de conectar las aplicaciones en la nube a Defender para aplicaciones en la nube, puedes crear Microsoft 365 dlp para ellas.

> [!NOTE]
> También es posible usar Microsoft Defender para aplicaciones en la nube para crear directivas DLP en aplicaciones en la nube de Microsoft. Sin embargo, se recomienda usar Microsoft 365 para crear y administrar directivas DLP en aplicaciones en la nube de Microsoft.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Crear una directiva DLP en una aplicación en la nube que no es de Microsoft

Cuando seleccione una ubicación para la directiva DLP, active la ubicación de **Microsoft Defender para Aplicaciones en** la nube.

- Para seleccionar una aplicación o instancia específica, seleccione **Elegir instancia**.
- Si no selecciona una instancia, la directiva usa todas las aplicaciones conectadas en el inquilino de Microsoft Defender para Aplicaciones en la nube.

   ![Ubicaciones para aplicar la directiva.](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US y Box-General.](../media/2-dlp-non-microsoft-cloud-app-box.png)

Puedes elegir varias acciones para cada aplicación en la nube compatible que no es de Microsoft. Para cada aplicación, hay diferentes acciones posibles (depende de la API de la aplicación en la nube).

![Crear regla.](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Al crear una regla en la directiva DLP, puedes seleccionar una acción para aplicaciones en la nube que no son de Microsoft. Para restringir aplicaciones de terceros, selecciona **Restringir aplicaciones de terceros.**

![Restringir aplicaciones de terceros.](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> Las directivas DLP aplicadas a aplicaciones que no son de Microsoft usan Microsoft Defender para aplicaciones en la nube. Cuando se crea la directiva DLP para una aplicación que no es de Microsoft, la misma directiva se creará automáticamente en Microsoft Defender para aplicaciones en la nube.

Para obtener información sobre cómo crear y configurar directivas DLP, vea [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).

## <a name="see-also"></a>Consulte también

- [Crear pruebas y ajustar una directiva DLP](./create-test-tune-dlp-policy.md)
- [Introducción a la directiva predeterminada de DLP](./get-started-with-the-default-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](./create-a-dlp-policy-from-a-template.md)
