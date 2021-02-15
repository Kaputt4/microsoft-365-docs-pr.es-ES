---
title: Configurar un conector para archivar datos de Reuniones de Zoom en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Globanet Zoom Meetings en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: c61c9a40d85b3bea266df9b1f2dba32301e54e08
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620206"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Configurar un conector para archivar datos de Reuniones de Zoom

Use un conector Globanet en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de Reuniones de Zoom a buzones de usuario de su organización de Microsoft 365. Globanet proporciona un conector de reuniones de [Zoom](https://globanet.com/zoom/) que está configurado para capturar elementos del origen de datos de terceros (de forma periódica) e importar esos elementos a Microsoft 365. El conector convierte el contenido de las reuniones (incluidos chats, archivos grabados y metadatos) de la cuenta de Zoom Meetings a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Después de almacenar los datos de Reuniones de Zoom en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de Reuniones de Zoom para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Información general sobre el archivado de datos de reuniones de zoom

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Reuniones de Zoom en Microsoft 365.

![Flujo de trabajo de archivado de Zoom Meetings](../media/ZoomMeetingsConnectorWorkflow.png)

1. Su organización trabaja con Reuniones de Zoom para configurar y configurar un sitio de Reuniones de Zoom.

2. Una vez cada 24 horas, los elementos de reunión de Reuniones de Zoom se copian en el sitio de Globanet Merge1. El conector también convierte el contenido de las reuniones a un formato de mensaje de correo electrónico.

3. El conector de Reuniones de Zoom que crea en el Centro de cumplimiento de Microsoft 365, se conecta a Globanet Merge1 todos los días y transfiere los mensajes de reunión a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos de reunión convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* y la asignación automática de usuarios, como se describe en el paso 3. Se crea una subcarpeta nueva en la carpeta Bandeja de entrada denominada **Zoom Meetings** en los buzones de usuario y los elementos de reunión se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email.* Cada elemento de reunión contiene esta propiedad, que se rellena con la dirección de correo electrónico de todos los participantes de la reunión.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto [con el servicio de soporte al cliente de Globanet.](https://globanet.com/ms-connectors-contact) Inicie sesión en esta cuenta cuando cree el conector en el paso 1.

- Obtenga el nombre de usuario y la contraseña de la cuenta Zoom Business o Zoom Enterprise de su organización. Deberá iniciar sesión en esta cuenta en el paso 2 cuando configure el conector de reuniones de Zoom.

- Cree las siguientes aplicaciones en [Zoom Marketplace:](https://marketplace.zoom.us)

  - Aplicación OAuth

  - Aplicación JWT

  Después de crear estas aplicaciones, la plataforma zoom genera un conjunto de credenciales únicas que se usan para generar los tokens. Estos tokens se usan para autenticar el conector cuando se conecta a su cuenta de Zoom y copia elementos en el sitio Merge1. Usará estos tokens al configurar el conector de zoom en el paso 2.

  Para obtener instrucciones paso a paso sobre cómo crear las aplicaciones OAuth y JWT, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- El usuario que crea el conector de reuniones de Zoom en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol importar o exportar buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Paso 1: Configurar el conector de reuniones de Zoom

El primer paso es obtener acceso a **los** conectores de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector de reuniones de Zoom.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, **haga clic en Conectores de datos**  >  **Acercar reuniones.**

2. En la página Descripción del producto Reuniones de **Zoom,** haga clic **en Agregar conector.**

3. En la **página Términos de** servicio, haga clic **en Aceptar.**

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Paso 2: Configurar el conector de reuniones de Zoom

El segundo paso es configurar el conector de reuniones de Zoom en el sitio Merge1. Para obtener más información acerca de cómo configurar el conector de reuniones de Zoom en el sitio de Globanet Merge1, vea la Guía del usuario de Conectores [de terceros Merge1.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)

Después de hacer clic en &  **finalizar,** se muestra la página Asignación de usuarios en el Asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

1. En la **página Asignar usuarios externos a usuarios de Microsoft 365,** habilite la asignación automática de usuarios.

   Los elementos de Acercar reuniones incluyen una propiedad denominada *Correo* electrónico que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario

2. Haga **clic en** Siguiente, revise  la configuración y vaya a la página Conectores de datos para ver el progreso del proceso de importación para el nuevo conector.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Paso 4: Supervisar el conector de reuniones de Zoom

Después de crear el conector de reuniones de Zoom, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) conectores de **datos y haga clic en** conectores de datos en el panel de navegación izquierdo.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **Reuniones de Zoom** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En Estado del conector  **con origen,** haga clic en el vínculo Descargar registro para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.

- Para que el conector reuniones de Zoom funcione, debe habilitar las grabaciones al configurar Reuniones de Zoom.
