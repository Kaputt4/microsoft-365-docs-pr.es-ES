---
title: Configurar un conector para archivar datos delimitados por texto en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos delimitados por texto de Globanet a Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 1c06a1220e597dbf8e278222347a5a5e9c46567e
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619906"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>Configurar un conector para archivar datos delimitados por texto

Use un conector Globanet en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos delimitados por texto en los buzones de usuario de su organización de Microsoft 365. Globanet proporciona [](https://globanet.com/text-delimited) un conector delimitado por texto que está configurado para capturar elementos de un origen de datos de terceros (de forma periódica) e importar esos elementos a Microsoft 365. El conector convierte el contenido del origen de datos delimitado por texto en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de almacenar los datos delimitados por texto en los buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, exhibición de documentos electrónicos y directivas de retención y etiquetas de retención. El uso de un conector de datos delimitado por texto para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-the-text-delimited-data"></a>Información general sobre el archivado de los datos delimitados por texto

En la siguiente introducción se explica el proceso de uso de un conector para archivar información de origen delimitada por texto en Microsoft 365.

![Flujo de trabajo de archivado para datos delimitados por texto](../media/TextDelimitedConnectorWorkflow.png)

1. Su organización trabaja con el origen delimitado por texto para configurar y configurar un sitio delimitado por texto.

2. Una vez cada 24 horas, los mensajes de chat del origen delimitado por texto se copian en el sitio de Globanet Merge1. El conector también convierte el contenido en un formato de mensaje de correo electrónico.

3. El conector delimitado por texto que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos de mensaje convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en el paso 3. Se crea una subcarpeta nueva en la carpeta Bandeja de entrada denominada **Texto delimitado** en los buzones de usuario y los elementos del mensaje se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada mensaje contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto [con el servicio de soporte al cliente de Globanet.](https://globanet.com/ms-connectors-contact) Inicie sesión en esta cuenta cuando cree el conector en el paso 1.

- El usuario que crea el conector delimitado por texto en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De importación y exportación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-text-delimited-connector"></a>Paso 1: Configurar el conector delimitado por texto

El primer paso es obtener acceso a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector para datos delimitados por texto.

1. Vaya a conectores de datos y, a continuación, haga [https://compliance.microsoft.com](https://compliance.microsoft.com/) **clic**  >  **en Conectores de datos delimitados por texto.**

2. En la **página de descripción del** producto delimitado por texto, haga clic en Agregar **conector.**

3. En la **página Términos de** servicio, haga clic **en Aceptar.**

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a>Paso 2: Configurar el conector delimitado por texto en el sitio de Globanet Merge1

El segundo paso es configurar el conector delimitado por texto en el sitio Merge1. Para obtener información acerca de cómo configurar el conector delimitado por texto en el sitio de Globanet Merge1, vea la Guía del usuario de Conectores de [terceros Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf).

Después de hacer clic en &  **finalizar,** se muestra la página Asignación de usuarios en el Asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar usuarios externos a usuarios de Microsoft 365,** habilite la asignación automática de usuarios. Los elementos de origen delimitados por texto incluyen una propiedad denominada *Correo* electrónico, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la  configuración y, a continuación, vaya a la página Conectores de datos para ver el progreso del proceso de importación para el nuevo conector.

## <a name="step-4-monitor-the-text-delimited-connector"></a>Paso 4: Supervisar el conector delimitado por texto

Después de crear el conector delimitado por texto, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) conectores de **datos y haga clic en** conectores de datos en el panel de navegación izquierdo.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **delimitado por** texto para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En Estado del conector  **con origen,** haga clic en el vínculo Descargar registro para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
