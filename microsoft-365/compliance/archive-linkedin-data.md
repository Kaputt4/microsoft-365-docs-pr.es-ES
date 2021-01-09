---
title: Configurar un conector para archivar datos de LinkedIn
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo los administradores & usar un conector nativo para importar datos de una página de empresa de LinkedIn a Microsoft 365.
ms.openlocfilehash: 9f6cb2c6d5c47559f1fda13b6d03bfed3afe6fa2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790184"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Configurar un conector para archivar datos de LinkedIn

Use un conector en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de páginas de LinkedIn Company. Después de configurar y configurar un conector, se conecta a la cuenta de la página específica de LinkedIn Company una vez cada 24 horas. El conector convierte los mensajes publicados en la página Compañía en un mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón de Microsoft 365.

Después de almacenar los datos de la página de LinkedIn Company en un buzón, puede aplicar las características de cumplimiento de Microsoft 365, como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría y directivas de retención de Microsoft 365 a los datos de LinkedIn. Por ejemplo, puede buscar estos elementos mediante la búsqueda de contenido o asociar el buzón de almacenamiento con un administrador en un caso de eDiscovery avanzado. La creación de un conector para importar y archivar datos de LinkedIn en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- El usuario que crea un conector de página de empresa de LinkedIn debe tener asignado el rol de importación y exportación de buzones en Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de** datos en el Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

- Debe tener las credenciales de inicio de sesión (dirección de correo electrónico o número de teléfono y contraseña) de una cuenta de usuario de LinkedIn que sea administrador de la página de la compañía de LinkedIn que desea archivar. Estas credenciales se usan para iniciar sesión en LinkedIn al configurar el conector.

- El conector de LinkedIn puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de LinkedIn en un día, ninguno de esos elementos se importará a Microsoft 365.

## <a name="create-a-linkedin-connector"></a>Crear un conector de LinkedIn

1. Vaya a las <https://compliance.microsoft.com> páginas de LinkedIn Company **de conectores** de datos y, a continuación, haga clic  >  **en Conectores de datos.**

2. En la página de productos de páginas de empresa de **LinkedIn,** haga clic **en Agregar conector.**

3. En la **página Términos de** servicio, seleccione **Aceptar**.

4. En la **página Iniciar sesión con LinkedIn,** haga clic en Iniciar sesión con **LinkedIn**.

   Se muestra la página de inicio de sesión de LinkedIn.

   ![Página de inicio de sesión de LinkedIn](../media/LinkedInSigninPage.png)

5. En la página de inicio de sesión de LinkedIn, escriba la dirección de correo electrónico (o número de teléfono) y la contraseña de la cuenta de LinkedIn asociada a la página de la empresa que desea archivar y, a continuación, haga clic en **Iniciar sesión.**

   Se muestra una página de asistente con una lista de todas las páginas de la compañía de LinkedIn asociadas con la cuenta en la que ha iniciado sesión. Un conector solo se puede configurar para una página de la empresa. Si su organización tiene varias páginas de empresa de LinkedIn, debe crear un conector para cada una.

   ![Se muestra una página con una lista de páginas de empresa de LinkedIn](../media/LinkedInSelectCompanyPage.png)

6. Seleccione la página de empresa desde la que desea archivar los elementos y, a continuación, haga clic en **Siguiente**.

7. En **la** página Elegir ubicación de almacenamiento, haga clic en el cuadro, seleccione la dirección de correo electrónico de un buzón de Microsoft 365 al que se importarán los elementos de LinkedIn y, a continuación, haga clic en **Siguiente.** Los elementos se importan a la carpeta bandeja de entrada de este buzón.

8. Haga **clic en Siguiente** para revisar la configuración del conector y, a continuación, haga clic en Finalizar para completar la configuración del conector. 

Después de crear el conector, puede  volver a la página Conectores de datos para  ver el progreso del proceso de importación para el nuevo conector (seleccione Actualizar si es necesario para actualizar la lista de conectores). El valor de la **columna Estado** está esperando **para iniciarse.** El proceso de importación inicial tarda hasta 24 horas en iniciarse. Después de la primera vez que el conector se ejecuta e importa los elementos de LinkedIn, el conector se ejecutará una vez cada 24 horas e importará los elementos nuevos que se crearon en la página de la compañía de LinkedIn en las 24 horas anteriores.

Para ver más detalles, seleccione el conector en la lista de la página **Conectores** de datos para mostrar la página desplegable. En **Estado,** el intervalo de fechas que se muestra indica el filtro de antigüedad que se seleccionó cuando se creó el conector.

## <a name="more-information"></a>Más información

Los elementos de LinkedIn se importan a la subcarpeta LinkedIn de la bandeja de entrada del buzón de almacenamiento en Microsoft 365. Aparecen como mensajes de correo electrónico.
