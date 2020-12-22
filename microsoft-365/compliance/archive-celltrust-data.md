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
localization_priority: Normal
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos de CellTrust de Globanet a Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar las características de cumplimiento, como directivas de retención legal, búsqueda de contenido y retención para administrar datos de terceros.
ms.openlocfilehash: 5870e823562f86b8b984e81fd03eeebd1b01f0ff
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722917"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a>Configurar un conector para archivar datos de CellTrust

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos desde la plataforma CellTrust a los buzones de usuario de la organización 365 de Microsoft. Globanet proporciona un conector [CellTrust](https://globanet.com/celltrust/) que captura elementos del origen de datos de terceros e importa esos elementos a Microsoft 365. El conector convierte el contenido de los mensajes SMS de las cuentas de CellTrust en un formato de mensaje de correo electrónico y, a continuación, importa dichos elementos en el buzón del usuario en Microsoft 365.

Una vez que los datos de CellTrust se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención, y cumplimiento de la comunicación. El uso de un conector de CellTrust para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-celltrust-data"></a>Información general sobre el archivado de datos de CellTrust

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de CellTrust en Microsoft 365.

![Flujo de trabajo de archivado para datos de CellTrust](../media/CellTrustConnectorWorkflow.png)

1. Su organización trabaja con CellTrust para instalar y configurar un sitio de CellTrust.

2. Una vez cada 24 horas, los elementos de CellTrust se copian en el sitio Merge1 de Globanet. El conector también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.

3. El conector CellTrust que se crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. La asignación automática de usuarios como conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *email* del que se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **CellTrust** en los buzones de usuario y los elementos de mensaje se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la propiedad *email* . Cada elemento CellTrust contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Merge1 para Microsoft Connectors. Para crear una cuenta, póngase en contacto [con el soporte técnico de Globanet](https://globanet.com/contact-us/). Debe iniciar sesión en esta cuenta cuando cree el conector en el paso 1.

- El usuario que crea el conector CellTrust en el paso 1 (y lo completa en el paso 3) debe estar asignado a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-celltrust-connector"></a>Paso 1: configurar el conector de CellTrust

El primer paso es obtener acceso a los **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector para los datos de CellTrust.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **conectores de datos** \> **CellTrust**.

2. En la página Descripción del producto de **CellTrust** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-celltrust-connector-on-the-globanet-merge1-site"></a>Paso 2: configurar el conector de CellTrust en el sitio de Merge1 de Globanet

El segundo paso consiste en configurar el conector de CellTrust en el sitio de Merge1 de Globanet. Para obtener información acerca de cómo configurar el conector de CellTrust, consulte [Merge1 guía del usuario de conectores de terceros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se muestra la página **asignación de usuarios** en el Asistente para conectores del centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar el conector configurado en el centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la página **asignar CellTrust usuarios a Microsoft 365 usuarios** , habilite la asignación automática de usuarios. Los elementos CellTrust incluyen una propiedad denominada *email*, que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. Haga clic en **siguiente**, revise la configuración y vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-celltrust-connector"></a>Paso 4: supervisar el conector de CellTrust

Después de crear el conector de CellTrust, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y, a continuación, seleccione el conector de **CellTrust** para mostrar la página de flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
