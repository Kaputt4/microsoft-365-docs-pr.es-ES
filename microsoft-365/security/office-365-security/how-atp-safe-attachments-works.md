---
title: Cómo funcionan los datos adjuntos seguros de ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información acerca de cómo puede mantener su organización segura contra archivos malintencionados mediante datos adjuntos seguros de ATP para Office 365.
ms.openlocfilehash: d13674a5d3e769fc10a1f5fd2fd80a4f07c063de
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201482"
---
# <a name="how-atp-safe-attachments-works"></a>Cómo funcionan los datos adjuntos seguros de ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La característica de datos adjuntos seguros de ATP comprueba los datos adjuntos del correo electrónico de las personas de su organización. Cuando se implementa una directiva de datos adjuntos seguros de ATP y alguien que cubre esa Directiva ve su correo electrónico en Office 365, se comprueban los datos adjuntos del correo electrónico y se realizan las acciones adecuadas, según las directivas de datos adjuntos seguros de ATP. Según cómo se hayan definido las directivas, los usuarios pueden seguir trabajando sin saber nunca que se les enviaron archivos malintencionados.
  
A continuación se muestran dos ejemplos de datos adjuntos seguros de ATP en el trabajo.
  
- **Ejemplo 1: datos adjuntos de correo electrónico** Supongamos que lee recibe un mensaje de correo electrónico que tiene datos adjuntos. No es obvio si esos datos adjuntos son seguros o contiene malware diseñado para robar las credenciales de usuario de Lee. En la organización de Lee, un administrador de seguridad definió una directiva de datos adjuntos seguros de ATP hace unos días. Con la característica de datos adjuntos seguros de ATP, los datos adjuntos de correo electrónico se abren y se prueban en un entorno virtual antes de que Lucas los reciba. Si los datos adjuntos se determinan como malintencionados, se eliminarán automáticamente. Si los datos adjuntos son seguros, se abrirán como se esperaba cuando lee hace clic en él.

- **Ejemplo 2: archivo en SharePoint Online** Supongamos que Jean ha recibido un archivo y lo ha cargado en una biblioteca en SharePoint Online. Jean comparte el vínculo al archivo con el resto del equipo, sin saber que el archivo es realmente malintencionado. Afortunadamente, [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) detecta el archivo malintencionado y lo bloquea. Unos días más tarde, Carlos abrirá el documento. Aunque Carlos puede ver el archivo está allí, Carlos no puede abrirlo ni compartirlo, lo que protege al equipo de Cristina y a otros usuarios del archivo malintencionado.

Las directivas de datos adjuntos seguros de ATP se pueden aplicar a personas o grupos específicos de la organización o a todo el dominio. Además, las directivas de datos adjuntos seguros de ATP se pueden configurar para usar datos adjuntos de marcador de posición mientras se analizan los datos adjuntos reales. Para obtener más información, consulte **[configurar las directivas de datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)**.

> [!NOTE]
> El análisis de datos adjuntos seguros de ATP tiene lugar en la misma región en la que residen los datos. Para más información sobre la geografía de centros de datos, consulte [¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All) 

