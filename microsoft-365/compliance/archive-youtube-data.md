---
title: Configurar un conector para archivar datos de YouTube en Microsoft 365
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
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos de YouTube de Veritas a Microsoft 365. Este conector permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, exhibición de documentos electrónicos y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 48354460a79cbb8c23086962d17482a3d3419044
ms.sourcegitcommit: 88c3b9758214936d283bad0321b826fb40a2e7e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2021
ms.locfileid: "60088246"
---
# <a name="set-up-a-connector-to-archive-youtube-data"></a>Configurar un conector para archivar datos de YouTube

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de YouTube a buzones de usuario de su Microsoft 365 organización. Veritas proporciona un conector configurado para capturar elementos de un origen de datos de terceros e importarlos a Microsoft 365. El conector convierte contenido como chats, datos adjuntos, tareas, notas y publicaciones de YouTube a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de usuario en Microsoft 365.

Después de almacenar los datos de YouTube en buzones de usuario, puedes aplicar Microsoft 365 de cumplimiento, como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector de YouTube para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-youtube-data"></a>Información general sobre el archivado de datos de YouTube

En la siguiente introducción se explica el proceso de uso de un conector para archivar los datos de YouTube en Microsoft 365.

![Flujo de trabajo de archivado para datos de YouTube.](../media/YouTubeConnectorWorkflow.png)

1. Tu organización trabaja con YouTube para configurar y configurar un sitio de YouTube.

2. Una vez cada 24 horas, los elementos de YouTube se copian en el sitio Veritas Merge1. El conector también convierte elementos de YouTube a un formato de mensaje de correo electrónico.

3. El conector de YouTube que creas en el Centro de cumplimiento de Microsoft 365 se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido de YouTube a una ubicación Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Una subcarpeta de la carpeta Bandeja de entrada denominada **YouTube** se crea en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de YouTube contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Crear una cuenta Merge1 para conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de soporte al cliente de Veritas](https://www.veritas.com/form/requestacall/ms-connectors-contact). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- Crea una aplicación de YouTube para capturar datos de tu cuenta de YouTube. Para obtener instrucciones paso a paso sobre cómo crear la aplicación, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf).

- El usuario que crea el conector de YouTube en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a ningún grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-youtube-connector"></a>Paso 1: Configurar el conector de YouTube

El primer paso es obtener acceso a la página **Conectores** de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector para datos de YouTube.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, haga clic **en Conectores de datos**  >  **youTube**.

2. En la página **Descripción del producto de YouTube,** haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-youtube-on-the-veritas-merge1-site"></a>Paso 2: Configurar YouTube en el sitio Veritas Merge1

El segundo paso es configurar el conector de YouTube en el sitio Veritas Merge1. Para obtener información sobre cómo configurar el conector de YouTube, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf).

Después de hacer clic en Guardar  **& finalizar,** se muestra la página Asignación de usuario en el asistente para conector en Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar usuarios de YouTube Microsoft 365 usuarios,** habilite la asignación automática de usuarios. Los elementos de YouTube incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-youtube-connector"></a>Paso 4: Supervisar el conector de YouTube

Después de crear el conector de YouTube, puedes ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com/> y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector de **YouTube** para mostrar la página desplegable, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
