---
title: Aumentar la protección contra amenazas para Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configure las características de cumplimiento para evitar la pérdida de datos y ayudar a proteger la información confidencial de sus clientes y sus clientes.
ms.openlocfilehash: 245a27c53951940f340dbb56c1b05a74d5dce249
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635452"
---
# <a name="set-up-compliance-features"></a>Configurar las características de cumplimiento

Su Microsoft 365 Business Premium incluye características de cumplimiento y privacidad. Estas funcionalidades ayudan a proteger los datos de su empresa y a proteger la información confidencial de sus clientes y sus clientes. Este artículo está diseñado para ayudarle a empezar con las características de cumplimiento.

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que tiene uno de los siguientes roles asignados en Azure Active Directory:

- Administrador global
- Administrador de cumplimiento

Para obtener más información, [vea Comenzar con la página roles](../admin/add-users/admin-roles-page.md).

## <a name="use-compliance-manager-to-get-started"></a>Usar el Administrador de cumplimiento para empezar

:::image type="content" source="./media/m365bp-compliancemanager.png" alt-text="Captura de pantalla del Administrador de cumplimiento en Microsoft 365 Business Premium.":::

Microsoft 365 Business Premium incluye el Administrador de cumplimiento, lo que puede ayudarle a empezar a configurar las características de cumplimiento. Estas características incluyen la prevención de pérdida de datos, el gobierno de la información y la administración de riesgos de información interna, por nombrar algunas. El Administrador de cumplimiento puede ahorrar tiempo resaltando recomendaciones, una puntuación de cumplimiento y formas de mejorar la puntuación.

Este es el modo de empezar:

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión.

2. En el panel de navegación, elija **Administrador de cumplimiento**.

3. En la **pestaña Información** general, revise la información. Seleccione un elemento o vínculo para ver más información o para realizar acciones, como configurar una directiva de prevención de pérdida de datos (DLP). Por ejemplo, en la **sección Soluciones que afectan a la puntuación** , puede seleccionar el vínculo en la **columna Acciones restantes** .

   :::image type="content" source="./media/m365bp-compliancesolutions.png" alt-text="Captura de pantalla de soluciones que afectan al panel puntuación.":::

   Esa acción te lleva a la pestaña **Acciones de** mejora, que se filtra para el elemento seleccionado. En este ejemplo, estamos viendo las directivas de DLP que se van a configurar.

   :::image type="content" source="./media/m365bp-dlppoliciestoconfigure.png" alt-text="Captura de pantalla de las directivas DLP que se configurarán.":::

4. En la **pestaña Acciones de** mejora, seleccione un elemento. En nuestro ejemplo, hemos seleccionado Crear directivas DLP personalizadas **o información de identificación personal**. Se carga una página que proporciona más información sobre la directiva que se debe configurar.

   :::image type="content" source="./media/m365bp-dlppolicyinfo.png" alt-text="Captura de pantalla de información sobre la directiva DLP para el contenido del cliente.":::

   Siga la información de la pantalla para configurar la directiva DLP.

Para obtener más información acerca de las características de cumplimiento en Microsoft 365 para empresas, [consulte Microsoft 365 documentación de cumplimiento normativo](../compliance/index.yml).

## <a name="use-sensitivity-labels"></a>Usar etiquetas de confidencialidad

Las etiquetas de confidencialidad están Office aplicaciones (como Outlook, Word, Excel y PowerPoint). Algunos ejemplos de etiquetas son:

- Normal
- Personal
- Private
- Confidencial

Sin embargo, también puede definir otras etiquetas para su empresa.

Use los siguientes artículos para empezar a usar etiquetas de confidencialidad:

1. [Obtenga información sobre las etiquetas de confidencialidad](../compliance/sensitivity-labels.md).

2. [Comenzar etiquetas de confidencialidad](../compliance/get-started-with-sensitivity-labels.md).

3. [Cree y configure etiquetas de confidencialidad y sus directivas](../compliance/create-sensitivity-labels.md).

4. [Mostrar a las personas de su empresa cómo usar etiquetas de confidencialidad](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)