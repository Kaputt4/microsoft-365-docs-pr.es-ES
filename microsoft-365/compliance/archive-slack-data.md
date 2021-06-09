---
title: Configurar un conector para archivar datos de exhibición de documentos electrónicos de Slack en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de la exhibición de documentos electrónicos de Veritas Slack en Microsoft 365. Este conector permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 48b0a6d4d5e8f6eafaaf900aa5c773cf4f99fe72
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163964"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>Configurar un conector para archivar datos de exhibición de documentos electrónicos de Slack

Use un conector Veritas en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de terceros desde redes sociales, mensajería instantánea y plataformas de colaboración de documentos a buzones de correo de su Microsoft 365 organización. Veritas proporciona un conector [de Slack](https://globanet.com/slack/) configurado para capturar elementos del origen de datos de terceros (de forma regular) y, a continuación, importar esos elementos a Microsoft 365. Slack extrae mensajes y archivos de la API de Slack y los convierte en un formato de mensaje de correo electrónico y, a continuación, importa el elemento a buzones de usuario.

Una vez que los datos de exhibición de documentos electrónicos de Slack se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de Slack para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Información general sobre el archivado de datos de exhibición de documentos electrónicos de Slack

En la siguiente introducción se explica el proceso de uso de un conector para archivar la información de Slack en Microsoft 365.

![Flujo de trabajo de archivado de Slack](../media/SlackConnectorWorkflow.png)

1. Su organización trabaja con Slack para configurar y configurar un sitio de Slack.

2. Una vez cada 24 horas, los mensajes de chat de Slack eDiscovery se copian en el sitio Veritas Merge1. El conector también convierte el contenido de un mensaje de chat a un formato de mensaje de correo electrónico.

3. El conector de exhibición de documentos electrónicos de Slack que crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere los mensajes de chat a una ubicación Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos de mensaje de chat convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* y la asignación automática de usuarios, tal como se describe en el paso 3. Se crea una nueva subcarpeta en la carpeta Bandeja de entrada denominada **Exhibición** de documentos electrónicos de Slack en los buzones de usuario y los elementos del mensaje de chat se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada mensaje de chat contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de chat.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Obtenga el nombre de usuario y la contraseña de la cuenta de empresa de Slack de su organización. Tendrás que iniciar sesión en esta cuenta en el paso 2 al configurar Slack.

- El usuario que crea el conector de exhibición de documentos electrónicos de Slack en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol Exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos del centro de Microsoft 365 cumplimiento. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>Paso 1: Configurar el conector de exhibición de documentos electrónicos de Slack

El primer paso es obtener acceso a la página **Conectores** de datos en el centro de Microsoft 365 de cumplimiento y crear un conector para datos de Slack.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **Conectores de datos**  >  **Slack eDiscovery**.

2. En la página Descripción del producto **de exhibición** de documentos electrónicos de Slack, haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-slack-ediscovery"></a>Paso 2: Configurar la exhibición de documentos electrónicos de Slack

El segundo paso es configurar el conector de exhibición de documentos electrónicos de Slack en el sitio Merge1. Para obtener más información acerca de cómo configurar el conector de exhibición de documentos electrónicos de Slack en el sitio Veritas Merge1, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en Microsoft 365 centro de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

1. En la **página Asignar usuarios externos Microsoft 365 usuarios,** habilite la asignación automática de usuarios.

   Los elementos de exhibición de documentos electrónicos de Slack incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>Paso 4: Supervisar el conector de exhibición de documentos electrónicos de Slack

Después de crear el conector de exhibición de documentos electrónicos de Slack, puede ver el estado del conector en el centro de Microsoft 365 cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **de exhibición** de documentos electrónicos de Slack para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.