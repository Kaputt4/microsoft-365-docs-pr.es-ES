---
title: Configurar un conector para archivar datos EML en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos EML de Veritas en Microsoft 365. Este conector permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 5261c30097cf571062d3c125841ac112e0552822
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164363"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a>Configurar un conector para archivar datos EML

Use un conector Veritas en el centro de Microsoft 365 de cumplimiento para importar y archivar datos eml a buzones de usuario de la Microsoft 365 organización. EML es la extensión de archivo de un mensaje de correo electrónico guardado en un archivo. El conector convierte el contenido de un elemento del formato de origen a un formato de mensaje de correo electrónico y, a continuación, importa el elemento a un buzón de usuario.

Una vez que los mensajes EML se almacenan en buzones de usuario, puede aplicar Microsoft 365 de cumplimiento, como retención por juicio, exhibición de documentos electrónicos y directivas de retención y etiquetas de retención. El uso de un conector EML para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-eml-data"></a>Información general sobre el archivado de datos EML

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos eml en Microsoft 365.

![Flujo de trabajo de archivado para datos EML](../media/EMLConnectorWorkflow.png)

1. Su organización trabaja con el origen eml para configurar y configurar un sitio EML.

2. Una vez cada 24 horas, los elementos de contenido del origen eml se copian en el sitio Veritas Merge1. Durante este proceso, el contenido de un archivo EML se convierte a un formato de mensaje de correo electrónico.

3. El conector EML que cree en el centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos de mensaje convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* del proceso de asignación automática de usuarios que se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Durante este proceso, se crea una subcarpeta en la carpeta Bandeja de entrada denominada **EML** en los buzones de usuario y los elementos eml se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada mensaje contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento de contenido.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector EML en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol Importar exportación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos del centro de Microsoft 365 cumplimiento. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-an-eml-connector"></a>Paso 1: Configurar un conector EML

El primer paso es obtener acceso a la página **Conectores** de datos en el centro de Microsoft 365 de cumplimiento y crear un conector para datos EML.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos**  >  **EML**.

2. En la **página descripción del producto EML,** haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-eml-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector EML en el sitio de Veritas Merge1

El segundo paso es configurar el conector EML en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar el conector EML, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en Microsoft 365 centro de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de Microsoft 365 cumplimiento, siga estos pasos:

1. En la **página Asignar usuarios externos Microsoft 365 usuarios,** habilite la asignación automática de usuarios. Los elementos de origen de EML incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos eml se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-eml-connector"></a>Paso 4: Supervisar el conector EML

Después de crear el conector EML, puede ver el estado del conector en el Microsoft 365 de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **EML** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.