---
title: 'Paso 5: Configurar la prevención de pérdida de datos de Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprender e implementar la prevención de pérdida de datos de Office 365 en Microsoft 365.
ms.openlocfilehash: dbe88885812e51b0daefa89dae123af5907c60a8
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047253"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>Paso 5: Configurar la prevención de pérdida de datos de Office 365

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Con directivas de prevención de pérdida de datos (DLP) del Centro de seguridad y cumplimiento de Office 365, puede identificar, supervisar y proteger automáticamente información confidencial en todo Microsoft 365. Con las directivas DLP, puede:

- Identificar información confidencial en varias ubicaciones, como Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
- Evitar el uso compartido accidental de información confidencial, bloqueando el acceso a un documento o el correo electrónico que lo contiene.
- Supervisar y proteger información confidencial en las versiones de escritorio de Excel, PowerPoint y Word.
- Ayudar a los usuarios a aprender a cumplir las directivas sin interrumpir el flujo de trabajo con notificaciones por correo electrónico y sugerencias de directivas. 
- Ver informes de DLP con contenido que coincida con las directivas DLP de su organización.

Una directiva DLP especifica:

- **Dónde:** ubicaciones, como los sitios de Exchange Online, SharePoint Online y OneDrive para la Empresa, así como chats y canales de Microsoft Teams.
- **Cuándo:** condiciones que debe cumplir el contenido dentro de una regla de directiva específica.
- **Cómo:** acciones dentro de esa regla coincidente de directiva para realizar automáticamente cuando se cumplan las condiciones.

Dicho de otra manera:

- Para un documento en esta ubicación (dónde), si el contenido coincide con las condiciones de una regla (cuándo), automáticamente realizar las acciones especificadas en la regla (cómo).

Para determinar el conjunto de directivas DLP que necesita, debe analizar sus documentos y los tipos de datos dentro de los mismos que necesitan protección contra la pérdida de datos. Por ejemplo, si tiene una organización financiera en Estados Unidos, podría crear una directiva DLP que impide que los documentos con los números de la seguridad social se compartan fuera de la organización o se envíen por correo electrónico a ubicaciones fuera de la organización.

Después, configurar y comprobar las directivas con ubicaciones de prueba para garantizar el comportamiento DLP correcto y minimizar los falsos positivos.

Por último, implementarla en su organización para informar a los empleados de las nuevas directivas y su comportamiento deseado y ampliar el ámbito de las ubicaciones.

Para obtener información, consulte [Introducción a las recomendaciones de la directiva DLP](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).

Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step5) correspondientes a este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[Configurar el cifrado de correo electrónico](infoprotect-email-encryption.md)|


