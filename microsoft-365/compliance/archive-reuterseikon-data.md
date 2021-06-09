---
title: Configurar un conector para archivar datos de Reuters Eikon en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Reuters Eikon de Veritas en Microsoft 365. Este conector permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: f3e0c9d542f54a46703b4acd0c1f154d3ab84cb8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164105"
---
# <a name="set-up-a-connector-to-archive-reuters-eikon-data"></a>Configurar un conector para archivar datos de Reuters Eikon

Use un conector Veritas en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de la plataforma Reuters Eikon a buzones de usuario de su Microsoft 365 organización. Veritas proporciona un conector Eikon de [Reuters](https://globanet.com/eikon/) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido, como mensajes de persona a persona, chats de grupo, datos adjuntos y declinaciones de responsabilidades de la cuenta Eikon de Reuters de un usuario a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de Reuters Eikon se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector Eikon de Reuters para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-reuters-eikon-data"></a>Información general sobre el archivado de datos de Reuters Eikon

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Reuters Eikon en Microsoft 365.

![Flujo de trabajo de archivado para datos eikon de Reuters](../media/ReutersEikonConnectorWorkflow.png)

1. Su organización trabaja con Reuters Eikon para configurar y configurar un sitio de Reuters Eikon.

2. Una vez cada 24 horas, los elementos de Reuters Eikon se copian en el sitio Veritas Merge1. El conector también convierte los elementos de Reuters Eikon a un formato de mensaje de correo electrónico.

3. El conector Eikon de Reuters que cree en el centro de cumplimiento de Microsoft 365 se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Reuters Eikon** en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de Reuters Eikon contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector Reuters Eikon en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De importación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos del centro de Microsoft 365 cumplimiento. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-reuters-eikon-connector"></a>Paso 1: Configurar el conector Reuters Eikon

El primer paso es obtener acceso a la página **Conectores** de datos del centro de Microsoft 365 de cumplimiento y crear un conector para los datos eikon de Reuters.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **Conectores de**  >  **datos Reuters Eikon**.

2. En la **página Descripción del producto Reuters Eikon,** haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-reuters-eikon-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector Reuters Eikon en el sitio Veritas Merge1

El segundo paso es configurar el conector Reuters Eikon en el sitio Merge1. Para obtener información sobre cómo configurar el conector Reuters Eikon en el sitio Veritas Merge1, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en Microsoft 365 centro de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de Microsoft 365 cumplimiento, siga estos pasos:

1. En la **página Asignar usuarios externos Microsoft 365 usuarios,** habilite la asignación automática de usuarios. Los elementos Eikon de Reuters incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-reuters-eikon-connector"></a>Paso 4: Supervisar el conector Reuters Eikon

Después de crear el conector Reuters Eikon, puede ver el estado del conector en el centro de Microsoft 365 cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña** Conectores y, a continuación, seleccione el conector **Reuters Eikon** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.