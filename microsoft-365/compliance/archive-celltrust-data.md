---
title: Configurar un conector para archivar datos de CellTrust en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos de CellTrust de Veritas a Microsoft 365. Este conector permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 89d19be7b23d76c5edbfe6949ba6b6b0166458a4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195718"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a>Configurar un conector para archivar datos de CellTrust

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 importar y archivar datos de la plataforma CellTrust a los buzones de usuario de su Microsoft 365 organización. Veritas proporciona un conector [CellTrust](https://globanet.com/celltrust/) que captura elementos del origen de datos de terceros e importa esos elementos a Microsoft 365. El conector convierte el contenido de los mensajes SMS de las cuentas de CellTrust a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de CellTrust se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector CellTrust para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-celltrust-data"></a>Información general sobre el archivado de datos de CellTrust

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de CellTrust en Microsoft 365.

![Flujo de trabajo de archivado para datos cellTrust.](../media/CellTrustConnectorWorkflow.png)

1. Su organización trabaja con CellTrust para configurar y configurar un sitio de CellTrust.

2. Una vez cada 24 horas, los elementos CellTrust se copian en el sitio Veritas Merge1. El conector también convierte el contenido de un mensaje a un formato de mensaje de correo electrónico.

3. El conector CellTrust que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio Veritas Merge1 todos los días y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.

4. La asignación automática de usuarios como conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* del descrito en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **CellTrust** en los buzones de usuario y los elementos del mensaje se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento CellTrust contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Crear una cuenta Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://www.veritas.com/content/support/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector CellTrust en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-celltrust-connector"></a>Paso 1: Configurar el conector CellTrust

El primer paso es obtener acceso a **los** conectores de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector para los datos de CellTrust.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos** \> **CellTrust**.

2. En la página **Descripción del producto CellTrust,** haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-celltrust-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector CellTrust en el sitio veritas merge1

El segundo paso es configurar el conector CellTrust en el sitio Veritas Merge1. Para obtener información sobre cómo configurar el conector CellTrust, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conector en Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar usuarios de CellTrust Microsoft 365 usuarios,** habilite la asignación automática de usuarios. Los elementos cellTrust incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-celltrust-connector"></a>Paso 4: Supervisar el conector CellTrust

Después de crear el conector CellTrust, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **CellTrust** para mostrar la página desplegable, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.