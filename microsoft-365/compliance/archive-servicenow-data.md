---
title: Configurar un conector para archivar datos de ServiceNow en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de ServiceNow de Veritas a Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 8f1f56f79d3cdd0e198f03d948837249d3e0ff3b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164045"
---
# <a name="set-up-a-connector-to-archive-servicenow-data"></a>Configurar un conector para archivar datos de ServiceNow

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos desde la plataforma ServiceNow a buzones de usuario de su organización de Microsoft 365. Veritas proporciona un [conector ServiceNow](https://globanet.com/servicenow/) que captura elementos del origen de datos de terceros e importa esos elementos a Microsoft 365. El conector convierte el contenido como mensajes dinámicos, datos adjuntos y publicaciones de ServiceNow a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Después de almacenar los datos de ServiceNow en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector ServiceNow para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-servicenow-data"></a>Información general sobre el archivado de datos de ServiceNow

En la siguiente introducción se explica el proceso de uso de un conector para archivar los datos de ServiceNow en Microsoft 365.

![Flujo de trabajo de archivado para datos de ServiceNow](../media/ServiceNowConnectorWorkflow.png)

1. Su organización trabaja con ServiceNow para configurar y configurar un sitio de ServiceNow.

2. Una vez cada 24 horas, los elementos de ServiceNow se copian en el sitio Veritas Merge1. El conector también convierte elementos de ServiceNow a un formato de mensaje de correo electrónico.

3. El conector servicenow que cree en el centro de cumplimiento de Microsoft 365 se conecta al sitio veritas merge1 todos los días y transfiere el contenido de ServiceNow a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **ServiceNow** en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento ServiceNow contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Crear una cuenta Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://www.veritas.com/content/support/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- Cree una aplicación ServiceNow para capturar datos de su cuenta de ServiceNow. Para obtener instrucciones paso a paso sobre cómo crear la aplicación, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).

- El usuario que crea el conector ServiceNow en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol Importar exportación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores de datos** del Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-servicenow-connector"></a>Paso 1: Configurar el conector de ServiceNow

El primer paso es obtener acceso a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector para los datos de ServiceNow.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos**  >  **ServiceNow**.

2. En la **página Descripción del producto ServiceNow,** haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-servicenow-on-the-veritas-merge1-site"></a>Paso 2: Configurar ServiceNow en el sitio Veritas Merge1

El segundo paso es configurar el conector ServiceNow en el sitio Veritas Merge1. Para obtener información sobre cómo configurar el conector ServiceNow, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).

Después de hacer clic en  Guardar **& finalizar,** se muestra la página Asignación de usuario en el asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la página Asignar usuarios de ServiceNow a usuarios de **Microsoft 365,** habilite la asignación automática de usuarios. Los elementos de ServiceNow incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-servicenow-connector"></a>Paso 4: Supervisar el conector de ServiceNow

Después de crear el conector ServiceNow, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **ServiceNow** para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.