---
title: Configurar un conector para archivar datos de LinkedIn
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 04/06/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo los administradores pueden configurar & usar un conector nativo para importar datos de una página de empresa de LinkedIn a Microsoft 365.
ms.openlocfilehash: 890ae9e618728cded8035dc69afe23b95a33d526
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67822273"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Configurar un conector para archivar datos de LinkedIn

Use un conector en el portal de cumplimiento Microsoft Purview para importar y archivar datos de páginas de LinkedIn Company. Después de configurar y configurar un conector, se conecta a la cuenta de la página específica de LinkedIn Company una vez cada 24 horas. El conector convierte los mensajes publicados en la página Empresa en un mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón en Microsoft 365.

Después de almacenar los datos de la página De la empresa de LinkedIn en un buzón de correo, puede aplicar las características de Microsoft Purview, como la suspensión por juicio, la búsqueda de contenido, el archivado de In-Place, la auditoría y las directivas de retención de Microsoft 365 a los datos de LinkedIn. Por ejemplo, puede buscar estos elementos mediante búsqueda de contenido o asociar el buzón de almacenamiento a un custodio en un caso de Microsoft Purview eDiscovery (Premium). La creación de un conector para importar y archivar datos de LinkedIn en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Al usuario que crea un conector de página de empresa de LinkedIn se le debe asignar el rol Administración conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Debe tener las credenciales de inicio de sesión (dirección de correo electrónico, número de teléfono y contraseña) de una cuenta de usuario de LinkedIn que sea administrador de la página de empresa de LinkedIn que desea archivar. Estas credenciales se usan para iniciar sesión en LinkedIn al configurar el conector.

- El conector de LinkedIn puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de LinkedIn en un día, ninguno de esos elementos se importará a Microsoft 365.

## <a name="create-a-linkedin-connector"></a>Creación de un conector de LinkedIn

1. Vaya a y, a <https://compliance.microsoft.com> continuación, haga clic en **Páginas de linkedIn Company** **de conectores** >  de datos.

2. En la página de producto de **las páginas de empresa de LinkedIn** , haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. En la página **Iniciar sesión con LinkedIn** , haga clic **en Iniciar sesión con LinkedIn**.

   Se muestra la página de inicio de sesión de LinkedIn.

   ![Página de inicio de sesión de LinkedIn.](../media/LinkedInSigninPage.png)

5. En la página de inicio de sesión de LinkedIn, escriba la dirección de correo electrónico (o el número de teléfono) y la contraseña de la cuenta de LinkedIn asociada a la página de empresa que desea archivar y, a continuación, haga clic **en Iniciar sesión**.

   Se muestra una página del asistente con una lista de todas las páginas de empresa de LinkedIn asociadas a la cuenta en la que inició sesión. Un conector solo se puede configurar para una página de empresa. Si su organización tiene varias páginas de empresa de LinkedIn, debe crear un conector para cada una de ellas.

   ![Se muestra una página con una lista de páginas de empresa de LinkedIn.](../media/LinkedInSelectCompanyPage.png)

6. Seleccione la página de empresa desde la que desea archivar elementos y, a continuación, haga clic en **Siguiente**.

7. En la página **Elegir ubicación de almacenamiento** , haga clic en el cuadro, seleccione la dirección de correo electrónico de un buzón de Microsoft 365 al que se importarán los elementos de LinkedIn y, a continuación, haga clic en **Siguiente**. Los elementos se importan a la carpeta bandeja de entrada de este buzón. El buzón usado debe tener una licencia Exchange Online plan 1 o plan 2.

8. Haga clic en **Siguiente** para revisar la configuración del conector y, a continuación, haga clic en **Finalizar** para completar la configuración del conector.

Después de crear el conector, puede volver a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector (seleccione **Actualizar** si es necesario para actualizar la lista de conectores). El valor de la columna **Estado** es **Esperando a iniciarse**. El proceso de importación inicial tarda hasta 24 horas en iniciarse. Después de la primera vez que el conector se ejecuta e importa los elementos de LinkedIn, el conector se ejecutará una vez cada 24 horas e importará los nuevos elementos creados en la página de empresa de LinkedIn en las 24 horas anteriores.

Para ver más detalles, seleccione el conector en la lista de la página **Conectores de datos** para mostrar la página de control flotante. En **Estado**, el intervalo de fechas que se muestra indica el filtro de antigüedad que se seleccionó cuando se creó el conector.

## <a name="more-information"></a>Más información

Los elementos de LinkedIn se importan a la subcarpeta LinkedIn de la bandeja de entrada del buzón de almacenamiento de Microsoft 365. Aparecen como mensajes de correo electrónico.
