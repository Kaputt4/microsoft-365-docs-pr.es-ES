---
title: Aumento de la protección contra amenazas para Microsoft 365 Empresa Premium
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
ms.openlocfilehash: b3393ef1e3667ed4b82ad8ff525a9d78dd637435
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64950742"
---
# <a name="set-up-compliance-features"></a>Configurar las características de cumplimiento

La suscripción Microsoft 365 Empresa Premium incluye características de cumplimiento y privacidad. Estas funcionalidades ayudan a proteger los datos de su empresa y a proteger la información confidencial de sus clientes. Este artículo está diseñado para ayudarle a empezar a trabajar con las características de cumplimiento.

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que tiene uno de los siguientes roles asignados en Azure Active Directory:

- Administrador global
- Administrador de cumplimiento

Para obtener más información, consulte [Comenzar con la página roles](../admin/add-users/admin-roles-page.md).

## <a name="use-compliance-manager-to-get-started"></a>Uso del Administrador de cumplimiento para empezar

:::image type="content" source="./media/m365bp-compliancemanager.png" alt-text="Captura de pantalla del Administrador de cumplimiento en Microsoft 365 Empresa Premium.":::

Microsoft 365 Empresa Premium incluye el Administrador de cumplimiento, que puede ayudarle a empezar a configurar las características de cumplimiento. Estas características incluyen la prevención de pérdida de datos, la administración del ciclo de vida de los datos y la administración de riesgos internos, por nombrar algunas. El Administrador de cumplimiento puede ahorrarle tiempo resaltando recomendaciones, una puntuación de cumplimiento y formas de mejorar la puntuación.

A continuación se muestra cómo empezar a trabajar:

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión.

2. En el panel de navegación, elija **Administrador de cumplimiento**.

3. En la pestaña **Información general** , revise la información. Seleccione un elemento o vínculo para ver más información o para realizar acciones, como configurar una directiva de prevención de pérdida de datos (DLP). Por ejemplo, en la sección **Soluciones que afectan a la puntuación** , puede seleccionar el vínculo en la columna **Acciones restantes** .

   :::image type="content" source="./media/m365bp-compliancesolutions.png" alt-text="Captura de pantalla del panel Soluciones que afectan a la puntuación.":::

   Esa acción le lleva a la pestaña **Acciones de mejora** , que se filtra para el elemento seleccionado. En este ejemplo se examinan las directivas DLP que se van a configurar.

   :::image type="content" source="./media/m365bp-dlppoliciestoconfigure.png" alt-text="Captura de pantalla de las directivas DLP que se van a configurar.":::

4. En la pestaña **Acciones de mejora** , seleccione un elemento. En nuestro ejemplo, hemos seleccionado **Crear directivas DLP personalizadas o información de identificación personal**. Se carga una página que proporciona más información sobre la directiva que se va a configurar.

   :::image type="content" source="./media/m365bp-dlppolicyinfo.png" alt-text="Captura de pantalla de información sobre la directiva DLP para el contenido del cliente.":::

   Siga la información de la pantalla para configurar la directiva DLP.

Para obtener más información sobre las características de cumplimiento en Microsoft 365 para empresas, consulte [la documentación de Microsoft Purview](../compliance/index.yml).

## <a name="use-sensitivity-labels"></a>Uso de etiquetas de confidencialidad

Las etiquetas de confidencialidad están disponibles en aplicaciones Office (como Outlook, Word, Excel y PowerPoint). Algunos ejemplos de etiquetas son:

- Normal
- Personal
- Private
- Confidencial

Sin embargo, también puede definir otras etiquetas para su empresa.

Use los artículos siguientes para empezar a usar etiquetas de confidencialidad:

1. [Obtenga información sobre las etiquetas de confidencialidad](../compliance/sensitivity-labels.md).

2. [Comenzar con etiquetas de confidencialidad](../compliance/get-started-with-sensitivity-labels.md).

3. [Cree y configure etiquetas de confidencialidad y sus directivas](../compliance/create-sensitivity-labels.md).

4. [Mostrar a los usuarios de su empresa cómo usar etiquetas de confidencialidad](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)