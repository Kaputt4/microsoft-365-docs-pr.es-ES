---
title: Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Puede Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos y poner una retención en el origen de datos. Los orígenes de datos que no son de Private se reindizan, de modo que todo el contenido que se considere indizado parcialmente se vuelve a procesar para que se pueda buscar de forma completa y rápida.
ms.openlocfilehash: 618d39bfb7be6cd260c88cdf4c57501747f440f1
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695509"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos

En los casos de eDiscovery avanzado, no siempre satisface sus necesidades de asociar un origen de datos de Microsoft 365 con un custodio en el caso. Pero es posible que tenga que asociar esos datos a un caso para que lo busque, agregue a un conjunto de revisión y lo revise. La nueva característica denominada *orígenes de datos que no son de Private* permite agregar datos a un caso sin tener que asociar los datos a un custodio. También aplica la misma funcionalidad avanzada de exhibición de documentos electrónicos a los datos que no son de Private y que están disponibles para los datos asociados con custodio. Dos de las características más útiles que se pueden aplicar a los datos que no son de Private son ponerla en suspensión y procesarla mediante una [indización avanzada](indexing-custodian-data.md).

## <a name="add-a-non-custodial-data-source"></a>Agregar un origen de datos que no sea de privación

Siga estos pasos para agregar y administrar orígenes de datos que no sean de Private en un caso de exhibición avanzada de documentos electrónicos.

1. En la Página principal de **EDiscovery avanzado** , haga clic en el caso al que desea agregar los datos.

2. En la página **orígenes** , haga clic en la ficha **ubicaciones de datos** y, a continuación, haga clic en **Agregar ubicación de datos**.

3. Haga clic en **Agregar ubicación de datos** y elija los orígenes de datos que desea agregar al caso. Puede agregar varios buzones y sitios.

4. En la página **elegir ubicaciones** del asistente, agregue buzones o sitios (o ambos) como orígenes de datos que no son de privación al caso.

5. Después de agregar los orígenes de datos, haga clic en **siguiente**.

6. En la página **poner suspensiones** , elija los orígenes de datos que desea poner en espera activando o desactivando la casilla de verificación asociada.

7. Compruebe las selecciones de retención y, a continuación, haga clic en **Enviar**.

   Cada origen de datos no de Private que agregó aparece en la lista de la página de **orígenes de datos** .

   Además, se crea un trabajo llamado *reindización de datos que no son de Private* y se muestra en la ficha **trabajos** del caso. Una vez creado el trabajo, el proceso de indización avanzado en iniciado y los orígenes de datos se vuelven a indizar.

## <a name="managing-the-hold-on-non-custodial-data-sources"></a>Administración de la retención en orígenes de datos que no son de Private

Después de poner una retención en un origen de datos que no sea de Private, se creará automáticamente una directiva de retención que contenga todos los orígenes de datos que no sean de privación para el caso. Cuando se colocan orígenes de datos adicionales que no son de conservación, se agregan a esta directiva de retención.

1. En la página **principal** del caso, haga clic en la pestaña **suspensiones** .

2. En la página **suspensiones** , haga clic en **NCDSHold- \<GUID\> **, donde el valor de GUID es único en el caso.

3. En la página de flotante, haga clic en **Editar suspensión** para ver todos los orígenes de datos que no son de Private que se encuentran en suspensión.

Puede realizar la siguiente tarea de administración en orígenes de datos que no sean de Private:

- Puede editar la retención para crear una suspensión basada en consulta que se aplique a todos los orígenes de datos que no sean de Private en el caso.

- Puede liberar un origen de datos que no sea de privación de la suspensión. Al liberar un origen de datos, no se quita del caso el origen de datos que no es de tipo Private. Solo quita la retención que se colocó en el origen de datos.
