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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo los administradores pueden configurar & un conector nativo para importar datos de una página de empresa de LinkedIn a Microsoft 365.
ms.openlocfilehash: 944a8bcbd06a07653ccf5e98e28807d279b66023
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322203"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Configurar un conector para archivar datos de LinkedIn

Use un conector en el Centro de cumplimiento de Microsoft 365 importar y archivar datos de páginas de linkedin company. Después de configurar y configurar un conector, se conecta a la cuenta de la página específica de linkedin company una vez cada 24 horas. El conector convierte los mensajes publicados en la página Empresa en un mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón de correo en Microsoft 365.

Después de almacenar los datos de la página de linkedin company en un buzón de correo, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría y directivas de retención Microsoft 365 a los datos de LinkedIn. Por ejemplo, puede buscar estos elementos mediante búsqueda de contenido o asociar el buzón de almacenamiento con un custodio en un Advanced eDiscovery caso. La creación de un conector para importar y archivar datos de LinkedIn en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- El usuario que crea un conector de página de la compañía linkedin debe tener asignado el rol de administrador de Conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Debe tener las credenciales de inicio de sesión (dirección de correo electrónico o número de teléfono y contraseña) de una cuenta de usuario de LinkedIn que sea administrador de la página de la compañía de LinkedIn que desea archivar. Estas credenciales se usan para iniciar sesión en LinkedIn al configurar el conector.

- El conector de LinkedIn puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de LinkedIn en un día, ninguno de esos elementos se importará a Microsoft 365.

## <a name="create-a-linkedin-connector"></a>Crear un conector de LinkedIn

1. Vaya a y<https://compliance.microsoft.com>, a continuación, **haga clic en Conectores** de datosLinkedIn  > **Páginas de la compañía**.

2. En la **página de producto Páginas de empresa de LinkedIn** , haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, seleccione **Aceptar**.

4. En la página **Iniciar sesión con LinkedIn** , haga clic **en Iniciar sesión con LinkedIn**.

   Se muestra la página de inicio de sesión de LinkedIn.

   ![Página de inicio de sesión de LinkedIn.](../media/LinkedInSigninPage.png)

5. En la página De inicio de sesión de LinkedIn, escriba la dirección de correo electrónico (o número de teléfono) y la contraseña de la cuenta de LinkedIn asociada a la página de la empresa que desea archivar y, a continuación, haga clic en **Iniciar sesión**.

   Se muestra una página del asistente con una lista de todas las páginas de empresa de LinkedIn asociadas con la cuenta en la que ha iniciado sesión. Un conector solo se puede configurar para una página de empresa. Si su organización tiene varias páginas de empresa de LinkedIn, debe crear un conector para cada una.

   ![Se muestra una página con una lista de páginas de empresa de LinkedIn.](../media/LinkedInSelectCompanyPage.png)

6. Seleccione la página de empresa desde la que desea archivar elementos y, a continuación, haga clic en **Siguiente**.

7. En **la página** Elegir ubicación de almacenamiento, haga clic en el cuadro, seleccione la dirección de correo electrónico de un buzón de Microsoft 365 al que se importarán los elementos de LinkedIn y, a continuación, haga clic en **Siguiente**. Los elementos se importan a la carpeta de bandeja de entrada de este buzón.

8. Haga **clic en** Siguiente para revisar la configuración del conector y, a continuación, haga clic **en Finalizar** para completar la configuración del conector.

Después de crear el conector, puede volver a la página Conectores de datos para ver el progreso del proceso de importación del nuevo conector (seleccione Actualizar si  es necesario para actualizar la lista de conectores). El valor de la **columna Estado** es **Waiting to start**. El proceso de importación inicial tarda hasta 24 horas en iniciarse. Después de la primera vez que el conector ejecute e importe los elementos de LinkedIn, el conector se ejecutará una vez cada 24 horas e importará los elementos nuevos que se crean en la página de la empresa de LinkedIn en las 24 horas anteriores.

Para ver más detalles, seleccione el conector en la lista de la página **Conectores** de datos para mostrar la página desplegable. En **Estado**, el intervalo de fechas que se muestra indica el filtro de antigüedad que se seleccionó cuando se creó el conector.

## <a name="more-information"></a>Más información

Los elementos de LinkedIn se importan a la subcarpeta LinkedIn de la bandeja de entrada del buzón de almacenamiento en Microsoft 365. Aparecen como mensajes de correo electrónico.