---
title: Configuración de un conector para archivar datos de YouTube en Microsoft 365
description: Los administradores pueden configurar un conector para importar y archivar datos de YouTube desde Veritas a Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como la suspensión legal, la exhibición de documentos electrónicos y las directivas de retención para administrar datos de terceros.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: baa99959941483d5a81e68b66f54bcdb4ac67930
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68813645"
---
# <a name="set-up-a-connector-to-archive-youtube-data"></a>Configuración de un conector para archivar datos de YouTube

Use un conector veritas en el portal de cumplimiento Microsoft Purview para importar y archivar datos de YouTube en buzones de usuario de su organización de Microsoft 365. Veritas proporciona un conector configurado para capturar elementos de un origen de datos de terceros e importarlos a Microsoft 365. El conector convierte contenido como chats, datos adjuntos, tareas, notas y publicaciones de YouTube en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de usuario de Microsoft 365.

Una vez que los datos de YouTube se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview, como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector de YouTube para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-youtube-data"></a>Introducción al archivado de datos de YouTube

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de YouTube en Microsoft 365.

![Flujo de trabajo de archivado de datos de YouTube.](../media/YouTubeConnectorWorkflow.png)

1. Su organización trabaja con YouTube para configurar y configurar un sitio de YouTube.

2. Una vez cada 24 horas, los elementos de YouTube se copian en el sitio de Veritas Merge1. El conector también convierte los elementos de YouTube en un formato de mensaje de correo electrónico.

3. El conector de YouTube que se crea en el portal de cumplimiento se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido de YouTube a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **YouTube** en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se van a importar elementos mediante el valor de la propiedad *Email*. Cada elemento de YouTube contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Cree una cuenta de Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/form/requestacall/ms-connectors-contact). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- Crea una aplicación de YouTube para capturar datos de tu cuenta de YouTube. Para obtener instrucciones paso a paso sobre cómo crear la aplicación, consulte [La Guía del usuario de conectores de terceros Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf).

- Al usuario que crea el conector de YouTube en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="step-1-set-up-the-youtube-connector"></a>Paso 1: Configurar el conector de YouTube

El primer paso consiste en acceder a la página **Conectores de datos** del portal de cumplimiento y crear un conector para los datos de YouTube.

1. Vaya a y, a <https://compliance.microsoft.com> continuación, seleccione **Conectores** >  de datos **de YouTube**.

2. En la página de descripción del producto **de YouTube** , seleccione **Agregar conector**.

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, seleccione **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-youtube-on-the-veritas-merge1-site"></a>Paso 2: Configuración de YouTube en el sitio de Veritas Merge1

El segundo paso es configurar el conector de YouTube en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar el conector de YouTube, consulte [la Guía del usuario de Conectores de terceros Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf).

Después de seleccionar **Guardar & finalizar,** se muestra la página **Asignación** de usuarios en el asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En la página **Asignar usuarios de YouTube a usuarios de Microsoft 365** , habilite la asignación automática de usuarios. Los elementos de YouTube incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Seleccione **Siguiente**, revise la configuración y, a continuación, vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-youtube-connector"></a>Paso 4: Supervisión del conector de YouTube

Después de crear el conector de YouTube, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a <https://compliance.microsoft.com/> y seleccione **Conectores de datos** en el panel de navegación izquierdo.

2. Seleccione la pestaña **Conectores** y, a continuación, seleccione el conector de **YouTube** para mostrar la página de control flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, seleccione el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
