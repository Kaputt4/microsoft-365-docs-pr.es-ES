---
title: Configuración de características de cumplimiento en Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 10/18/2022
ms.localizationpriority: high
ms.collection:
- m365-security
- tier1
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: Configure las características de cumplimiento para evitar la pérdida de datos y ayudar a proteger la información confidencial de sus clientes.
ms.openlocfilehash: ca37ff6d4fd9496bade037da9ac5ff9dd1da083a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68643655"
---
# <a name="set-up-compliance-features-in-microsoft-365-business-premium"></a>Configuración de características de cumplimiento en Microsoft 365 Empresa Premium


Consulte la [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

La suscripción Microsoft 365 Empresa Premium incluye características de cumplimiento y privacidad. Estas funcionalidades ayudan a proteger los datos de su empresa y a mantener segura su información confidencial y la de sus clientes. Este artículo está diseñado para ayudarle a comenzar con las características de cumplimiento.


## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que tiene uno de los siguientes roles asignados en Azure Active Directory:

- Administrador global
- Administrador de cumplimiento

Para obtener más información, consulte [Comenzar con la página roles](../admin/add-users/admin-roles-page.md).

## <a name="use-compliance-manager-to-get-started"></a>Uso del Administrador de cumplimiento para empezar

:::image type="content" source="./media/m365bp-compliancemanager.png" alt-text="Captura de pantalla del Administrador de cumplimiento en Microsoft 365 Empresa Premium.":::

Microsoft 365 Empresa Premium incluye el Administrador de cumplimiento, que puede ayudarle a empezar a configurar las características de cumplimiento. Estas características incluyen la prevención de pérdida de datos, la administración del ciclo de vida de los datos y la administración de riesgos internos, entre otros. El Administrador de cumplimiento puede ahorrarle tiempo resaltando recomendaciones, una puntuación de cumplimiento y formas de mejorar la puntuación.

A continuación se muestra cómo empezar:

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión.

2. En el panel de navegación, elija **Administrador de cumplimiento**.

3. En la pestaña **Información general**, revise la información. Seleccione un elemento o vínculo para ver más información o para realizar acciones, como configurar una directiva de prevención de pérdida de datos (DLP). Por ejemplo, en la sección **Soluciones que afectan a la puntuación**, puede seleccionar el vínculo en la columna **Acciones restantes**.

   :::image type="content" source="./media/m365bp-compliancesolutions.png" alt-text="Captura de pantalla del panel Soluciones que afectan a la puntuación.":::

   Esa acción le lleva a la pestaña **Acciones de mejora**, que está filtrada para el elemento que ha seleccionado. En este ejemplo se examinan las directivas DLP que se van a configurar.

   :::image type="content" source="./media/m365bp-dlppoliciestoconfigure.png" alt-text="Captura de pantalla de las directivas DLP que se van a configurar.":::

4. En la pestaña **Acciones de mejora**, seleccione un elemento. En nuestro ejemplo, hemos seleccionado **Crear directivas DLP personalizadas o información de identificación personal**. Se carga una página que proporciona más información sobre la directiva que se va a configurar.

   :::image type="content" source="./media/m365bp-dlppolicyinfo.png" alt-text="Captura de pantalla de información sobre la directiva DLP para el contenido del cliente.":::

   Siga la información que aparece en pantalla para configurar la directiva DLP.

Para obtener más información sobre las características de cumplimiento en Microsoft 365 para empresas, consulte la [documentación de Microsoft Purview](../compliance/index.yml).

## <a name="use-sensitivity-labels"></a>Usar etiquetas de confidencialidad

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198022).

Las etiquetas de confidencialidad están disponibles en aplicaciones de Microsoft 365 (como Outlook, Word, Excel y PowerPoint). Algunos ejemplos de etiquetas son:

- Normal
- Personal
- Private
- Confidencial

Sin embargo, también puede definir otras etiquetas para su empresa.

Use los artículos siguientes para empezar a usar etiquetas de confidencialidad:

1. [Obtener información sobre las etiquetas de confidencialidad](../compliance/sensitivity-labels.md).

2. [Introducción a las etiquetas de confidencialidad](../compliance/get-started-with-sensitivity-labels.md)

3. [Crear y configurar etiquetas de confidencialidad y sus directivas](../compliance/create-sensitivity-labels.md)

4. [Mostrar a los usuarios de su empresa cómo usar etiquetas de confidencialidad](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)