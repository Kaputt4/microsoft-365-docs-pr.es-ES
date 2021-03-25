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
description: Los administradores pueden configurar un conector para importar y archivar datos delimitados por texto de Veritas en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 9a8265766dd08a78c3f218710a3bc4b623f7f670
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163944"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>Configurar un conector para archivar datos delimitados por texto

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos delimitados por texto en buzones de usuario de su organización de Microsoft 365. Veritas proporciona un [conector](https://globanet.com/text-delimited) delimitado por texto que está configurado para capturar elementos de un origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido del origen de datos delimitado por texto a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos delimitados por texto se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos y directivas de retención y etiquetas de retención. El uso de un conector de datos delimitado por texto para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-the-text-delimited-data"></a>Información general sobre el archivado de los datos delimitados por texto

En la siguiente introducción se explica el proceso de uso de un conector para archivar información de origen delimitada por texto en Microsoft 365.

![Flujo de trabajo de archivado para datos delimitados por texto](../media/TextDelimitedConnectorWorkflow.png)

1. La organización trabaja con el origen delimitado por texto para configurar y configurar un sitio delimitado por texto.

2. Una vez cada 24 horas, los mensajes de chat del origen delimitado por texto se copian en el sitio Veritas Merge1. El conector también convierte el contenido en un formato de mensaje de correo electrónico.

3. El conector delimitado por texto que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio veritas Merge1 todos los días y transfiere los mensajes a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos de mensaje convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en el paso 3. Se crea una nueva subcarpeta en la carpeta Bandeja de entrada denominada **Text- Delimited** en los buzones de usuario y los elementos del mensaje se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada mensaje contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de soporte al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector delimitado por texto en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores de datos** del Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-text-delimited-connector"></a>Paso 1: Configurar el conector delimitado por texto

El primer paso es obtener acceso a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector para datos delimitados por texto.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **Conectores** de datos  >  **Delimitado por texto**.

2. En la página de descripción del producto **delimitada por** texto, haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-text-delimited-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector delimitado por texto en el sitio Veritas Merge1

El segundo paso es configurar el conector delimitado por texto en el sitio Merge1. Para obtener información sobre cómo configurar el conector delimitado por texto en el sitio de Veritas Merge1, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar usuarios externos a usuarios de Microsoft 365,** habilite la asignación automática de usuarios. Los elementos de origen delimitados por texto incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-text-delimited-connector"></a>Paso 4: Supervisar el conector delimitado por texto

Después de crear el conector delimitado por texto, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector delimitado **por** texto para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.