---
title: Configurar un conector para archivar datos de Connect FX en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Globanet FX Connect en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: de358f3aef34754bd7b715f9294aff530fc917ae
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620007"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a>Configurar un conector para archivar datos de Connect FX

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos desde la plataforma de colaboración de FX Connect a los buzones de usuario de la organización 365 de Microsoft. Globanet proporciona un conector [FX Connect](https://globanet.com/fx-connect/) que está configurado para capturar los elementos de Connect de FX e importar dichos elementos a Microsoft 365. El conector convierte el contenido de FX Connect, como transacciones, mensajes y otros detalles de la cuenta de conexión de FX de su organización, a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de que los datos de FX Connect se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención y cumplimiento de la comunicación. El uso de un conector de FX Connect para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-fx-connect-data"></a>Información general sobre el archivado de datos de FX Connect

En la siguiente introducción se explica el proceso de uso de un conector para archivar la información de conexión de FX en Microsoft 365.

![Flujo de trabajo de archivado para datos de Connect FX](../media/FXConnectConnectorWorkflow.png)

1. La organización trabaja con FX Connect para configurar y configurar un sitio FX Connect.

2. Una vez cada 24 horas, los elementos de las cuentas de FX Connect se copian en el sitio de Merge1 de Globanet. El conector también convierte los elementos de conexión FX a un formato de mensaje de correo electrónico.

3. El conector de FX Connect que crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio de Globanet Merge1 todos los días y transfiere los elementos de Connect de FX a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *email* de la asignación automática de usuarios, como se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada llamada **FX Connect** en los buzones de usuario y los elementos se importan a esa carpeta. El conector lo hace mediante el valor de la propiedad *email* . Cada elemento de FX Connect contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para Microsoft Connectors.  Para crear una cuenta, póngase en contacto [con el soporte técnico de Globanet](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta cuando cree el conector en el paso 1.

- El usuario que crea el conector de FX Connect en el paso 1 (y lo completa en el paso 3) debe asignarse a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a un grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-fx-connect-connector"></a>Paso 1: configurar el conector de Connect FX

El primer paso es obtener acceso a la página **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector para los datos de Connect FX.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **conectores de datos**  >  **FX Connect**.

2. En la página de Descripción del producto **FX Connect** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-fx-connect-connector-on-the-globanet-merge1-site"></a>Paso 2: configurar el conector de FX Connect en el sitio de Merge1 de Globanet

El segundo paso consiste en configurar el conector de Connect FX en el sitio Merge1. Para obtener información acerca de cómo configurar el conector de Connect FX, consulte la [Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se muestra la página **asignación de usuarios** en el Asistente para conectores del centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la página **asignar usuarios de FX Connect a usuarios de Microsoft 365** , habilite la asignación automática de usuarios. Los elementos de conexión FX incluyen una propiedad denominada *email*, que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. Haga clic en **siguiente**, revise la configuración y, después, vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-fx-connect-connector"></a>Paso 4: supervisar el conector de Connect FX

Después de crear el conector de conexión de FX, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com/> y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y, a continuación, seleccione el conector de **conexión FX** para mostrar la página de flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
