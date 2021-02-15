---
title: Configurar un conector para archivar datos Jive en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos Jive de Globanet en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: e89404362505dbe276e351e95ebd30a0c0bdf88c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620397"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a>Configurar un conector para archivar datos Jive

Use un conector Globanet en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de la plataforma de colaboración a los buzones de usuario de su organización de Microsoft 365. Globanet proporciona un conector [Jive](https://globanet.com/jive/) que está configurado para capturar elementos del origen de datos de terceros (de forma periódica) y, a continuación, importar esos elementos a Microsoft 365. El conector convierte contenido como mensajes de correo electrónico, chats y datos adjuntos de la cuenta Jive de un usuario a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de almacenar los datos Jive en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención, y cumplimiento de comunicaciones. El uso de un conector Jive para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-jive-data"></a>Información general sobre el archivado de datos Jive

En la siguiente introducción se explica el proceso de uso de un conector para archivar los datos Jive en Microsoft 365.

![Flujo de trabajo de archivado para datos Jive](../media/JiveConnectorWorkflow.png)

1. Su organización trabaja con Jive para configurar y configurar un sitio Jive.

2. Una vez cada 24 horas, los elementos de Jive se copian en el sitio de Globanet Merge1. El conector también convierte el contenido de los elementos Jive en un formato de mensaje de correo electrónico.

3. El conector Jive que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de Globanet Merge1 todos los días y transfiere el contenido a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta nueva en la carpeta Bandeja de entrada denominada **Jive** en los buzones de usuario y los elementos se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email.* Cada elemento Jive contiene esta propiedad, que se rellena con la dirección de correo electrónico de todos los participantes del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto [con el servicio de soporte al cliente de globanet.](https://globanet.com/ms-connectors-contact/) Inicie sesión en esta cuenta cuando cree el conector en el paso 1.

- El usuario que crea el conector Jive en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De importación y exportación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-jive-connector"></a>Paso 1: Configurar el conector Jive

El primer paso es acceder a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector para datos Jive.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) Y, a continuación, **haga clic en Conectores de** datos  >  **Jive**.

2. En la página **Descripción del producto Jive,** haga clic **en Agregar conector.**

3. En la **página Términos de** servicio, haga clic **en Aceptar.**

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-jive-connector"></a>Paso 2: Configurar el conector Jive

El segundo paso es configurar el conector Jive en el sitio Merge1. Para obtener información acerca de cómo configurar el conector Jive, vea la Guía del usuario de Conectores de [terceros Merge1.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)

Después de hacer clic en &  **finalizar,** se muestra la página Asignación de usuarios en el Asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga los pasos siguientes:

1. En la página Asignar usuarios de Jive a **usuarios de Microsoft 365,** habilite la asignación automática de usuarios. Los elementos Jive incluyen una propiedad denominada *Correo* electrónico, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise  la configuración y vaya a la página Conectores de datos para ver el progreso del proceso de importación para el nuevo conector.

## <a name="step-4-monitor-the-jive-connector"></a>Paso 4: Supervisar el conector Jive

Después de crear el conector Jive, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) conectores de **datos y haga clic en** conectores de datos en el panel de navegación izquierdo.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el **conector Jive** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En Estado del conector  **con origen,** haga clic en el vínculo Descargar registro para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
