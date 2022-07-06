---
title: Uso de directivas DLP para aplicaciones en la nube que no son de Microsoft
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
description: Obtenga información sobre cómo usar directivas dlp para aplicaciones en la nube que no son de Microsoft.
ms.openlocfilehash: a50849b53819a7c5872c3ec8cb279ffa8d14e27f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634407"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a>Uso de directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft

Puede definir el ámbito de las directivas DLP para Microsoft Defender for Cloud Apps para supervisar, detectar y realizar acciones cuando se usan y comparten elementos confidenciales a través de aplicaciones en la nube que no son de Microsoft.

## <a name="before-you-begin"></a>Antes de empezar

### <a name="skusubscriptions-licensing"></a>Licencias de SKU/suscripciones

Antes de empezar a usar las directivas DLP, confirme su [suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y cualquier complemento. Para acceder a esta funcionalidad y usarla, debe tener una de estas suscripciones o complementos:

- Microsoft 365 E5
- Cumplimiento de Microsoft 365 E5
- Seguridad de Microsoft 365 E5

### <a name="permissions"></a>Permisos
El usuario que crea la directiva DLP debe ser:

- Administrador global
- Administrador de cumplimiento: asignación en Azure AD
- Administrador de datos de cumplimiento: asignación en Azure AD

### <a name="prepare-your-defender-for-cloud-apps-environment"></a>Preparación del entorno de Defender for Cloud Apps

Antes de configurar directivas DLP con ámbito de Microsoft Defender for Cloud Apps, debe preparar el entorno de Defender for Cloud Apps. Para obtener instrucciones, consulte [Inicio rápido: Introducción a Microsoft Defender for Cloud Apps](/defender-cloud-apps/get-started).

### <a name="connect-a-non-microsoft-cloud-app"></a>Conexión de una aplicación en la nube que no es de Microsoft

Para usar una directiva DLP con el ámbito de una aplicación en la nube específica que no sea de Microsoft, la aplicación debe estar conectada a Defender for Cloud Apps. Para obtener información, consulte:

- [Connect Box](/defender-cloud-apps/connect-box)
- [Conexión de Dropbox](/defender-cloud-apps/connect-dropbox)
- [Conexión al área de trabajo de Google](/defender-cloud-apps/connect-google-workspace)
- [Conexión de Salesforce](/defender-cloud-apps/connect-salesforce)
- [Conexión de Cisco Webex](/defender-cloud-apps/connect-webex)

Después de conectar las aplicaciones en la nube a Defender for Cloud Apps, puede crear directivas DLP para ellas.

## <a name="create-a-dlp-policy-scoped-to-a-non-microsoft-cloud-app"></a>Creación de una directiva DLP con ámbito de aplicación en la nube que no es de Microsoft

Consulte [Creación, prueba y ajuste de una directiva DLP](create-test-tune-dlp-policy.md) para conocer los procedimientos para crear una directiva DLP. Tenga en cuenta estos puntos a medida que configure la directiva.

- Seleccione la opción activar la ubicación **de Microsoft Defender for Cloud Apps**.
- Para seleccionar una aplicación o instancia específica, seleccione **Elegir instancia**. Si no selecciona una instancia, la directiva se limitará a todas las aplicaciones conectadas del inquilino de Microsoft Defender for Cloud Apps.
- Puede seleccionar entre varias **acciones** para aplicarlas en aplicaciones de terceros. Para restringir aplicaciones de terceros, seleccione **Restringir aplicaciones de terceros** y, a continuación, seleccione las acciones específicas.

![lista de acciones que se aplicarán en aplicaciones en la nube conectadas](../media/dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> Al crear una directiva DLP con el ámbito Microsoft Defender for Cloud Apps, la misma directiva se creará automáticamente en Microsoft Defender for Cloud Apps.

## <a name="see-also"></a>Consulta también

- [Creación de una prueba y optimización de una directiva DLP](./create-test-tune-dlp-policy.md)
- [Introducción a la directiva predeterminada de DLP](./get-started-with-the-default-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](./create-a-dlp-policy-from-a-template.md)
