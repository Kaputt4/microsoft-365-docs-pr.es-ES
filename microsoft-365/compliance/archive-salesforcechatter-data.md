---
title: Configurar un conector para archivar datos de Salesforce Chatter en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Salesforce Chatter de Veritas a Microsoft 365. Este conector permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: c04dc3026eaa5abb23b332dbae826c052344da31
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164064"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a>Configurar un conector para archivar datos de Salesforce Chatter

Use un conector Veritas en el centro de cumplimiento Microsoft 365 para importar y archivar datos de la plataforma Salesforce Chatter a buzones de usuario de su Microsoft 365 organización. Veritas proporciona un conector [de Salesforce Chatter](http://globanet.com/chatter/) que captura elementos del origen de datos de terceros e importa esos elementos a Microsoft 365. El conector convierte el contenido como chats, datos adjuntos y publicaciones de Salesforce Chatter a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de almacenar los datos de Salesforce Chatter en buzones de usuario, puede aplicar Microsoft 365 de cumplimiento, como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector de Salesforce Chatter para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-salesforce-chatter-data"></a>Información general sobre el archivado de datos de Salesforce Chatter

En la siguiente introducción se explica el proceso de uso de un conector para archivar los datos de Salesforce Chatter en Microsoft 365.

![Flujo de trabajo de archivado para datos de Salesforce Chatter](../media/SalesforceChatterConnectorWorkflow.png)

1. Su organización trabaja con Salesforce Chatter para configurar y configurar un sitio de Salesforce Chatter.

2. Una vez cada 24 horas, los elementos de Salesforce Chatter se copian en el sitio Veritas Merge1. El conector también incluye elementos de Salesforce Chatter en un formato de mensaje de correo electrónico.

3. El conector de Salesforce Chatter que crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido de Chatter a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Salesforce Chatter** en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de Chatter contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Crear una cuenta Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://www.veritas.com/content/support/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- Cree una aplicación de Salesforce y adquiera un token en [https://salesforce.com](https://salesforce.com) . Deberá iniciar sesión en la cuenta de Salesforce como administrador y obtener un token personal de usuario para importar datos. Además, los desencadenadores deben publicarse en el sitio de Chatter para capturar actualizaciones, eliminaciones y ediciones. Estos desencadenadores crearán una publicación en un canal y Merge1 capturará la información del canal. Para obtener instrucciones paso a paso sobre cómo crear la aplicación y adquirir el token, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

- El usuario que crea el conector de Salesforce Chatter en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol Importar exportación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos del centro de Microsoft 365 cumplimiento. De forma predeterminada, este rol no se asigna a ningún grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>Paso 1: Configurar el conector de Salesforce Chatter

El primer paso es obtener acceso a la página **Conectores** de datos en el centro de Microsoft 365 cumplimiento y crear un conector para datos de Chatter.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos** Salesforce  >  **Chatter**.

2. En la página **Descripción del producto de Salesforce Chatter,** haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-salesforce-chatter-on-the-veritas-merge1-site"></a>Paso 2: Configurar Salesforce Chatter en el sitio Veritas Merge1

El segundo paso es configurar el conector de Salesforce Chatter en el sitio Veritas Merge1. Para obtener información sobre cómo configurar el conector de Salesforce Chatter, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  **& finalizar,** se muestra la página Asignación de usuario en el asistente para conectores en Microsoft 365 centro de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de Microsoft 365 cumplimiento, siga estos pasos:

1. En la **página Asignar usuarios de Salesforce Chatter Microsoft 365 usuarios,** habilite la asignación automática de usuarios. Los elementos de Salesforce Chatter incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. haga **clic en Siguiente,** revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>Paso 4: Supervisar el conector de Salesforce Chatter

Después de crear el conector de Salesforce Chatter, puede ver el estado del conector en el centro de Microsoft 365 cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **Conectores de datos** en la navegación izquierda.

2. haga clic en **la pestaña Conectores** y, a continuación, haga clic en el conector **de Salesforce Chatter** para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.