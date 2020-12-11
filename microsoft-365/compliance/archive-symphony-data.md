---
title: Configurar un conector para archivar datos de Symphony en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Globanet Symphony en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar las características de cumplimiento, como directivas de retención legal, búsqueda de contenido y retención para administrar datos de terceros.
ms.openlocfilehash: 94bd9bb8f2b7586e685769af389d6cd0a0ea18ac
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619836"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a>Configurar un conector para archivar datos de Symphony

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de Symphony a los buzones de usuario de la organización 365 de Microsoft. Symphony es una plataforma de mensajería y colaboración que se usa en la industria de servicios financieros. Globanet proporciona un conector de datos [Symphony](https://globanet.com/symphony) en el centro de cumplimiento de Microsoft 365 que puede configurar para capturar elementos del origen de datos de terceros (de forma regular) y, a continuación, importar dichos elementos a los buzones de usuario. El conector convierte el contenido de un elemento de la cuenta Symphony a un formato de mensaje de correo electrónico y, a continuación, importa el elemento a un buzón en Microsoft 365.

Una vez que se almacenan las comunicaciones de los Symphony en los buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención y cumplimiento de la comunicación. El uso de un conector Symphony para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-symphony-data"></a>Información general sobre el archivado de datos Symphony

La información general siguiente explica el proceso de uso de un conector de datos para archivar las comunicaciones de Symphony en Microsoft 365.

![Flujo de trabajo de archivado de Symphony](../media/SymphonyConnectorWorkflow.png)

1. La organización trabaja con Symphony para configurar y configurar un sitio Symphony.

2. Una vez cada 24 horas, los mensajes de chat de Symphony se copian en el sitio de Merge1 de Globanet. El conector también convierte el contenido de un mensaje de chat en un formato de mensaje de correo electrónico.

3. El conector Symphony que crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa los elementos de mensaje convertidos a los buzones de usuarios específicos usando el valor de la propiedad *email* de la asignación automática de usuarios, como se describe en el paso 3. Se crea una subcarpeta nueva en la carpeta Bandeja de entrada denominada **Symphony** en los buzones de usuario y los elementos de mensaje se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la propiedad *email* . Todos los mensajes de chat contienen esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para Microsoft Connectors. Para crear una cuenta, póngase en contacto [con el soporte técnico de Globanet](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta cuando cree el conector en el paso 1.

- El usuario que crea el conector Symphony en el paso 1 (y lo completa en el paso 3) debe asignarse a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a un grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-symphony-connector"></a>Paso 1: configurar el conector Symphony

El primer paso es obtener acceso a la página **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector para datos de Symphony.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **conectores de datos**  >  **Symphony**.

2. En la página Descripción del producto **Symphony** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a>Configurar el conector Symphony en el sitio de Merge1 de Globanet

El segundo paso consiste en configurar el conector Symphony en el sitio de Merge1. Para obtener información sobre cómo configurar el conector Symphony en el sitio de Merge1 de Globanet, consulte [Merge1 guía del usuario de conectores de terceros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se muestra la página **asignación de usuarios** en el Asistente para conectores del centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la página **asignar usuarios externos a Microsoft 365 usuarios** , habilite la asignación automática de usuarios. Los elementos de Symphony incluyen una propiedad denominada *email*, que contiene las direcciones de correo electrónico de los usuarios de su organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. Haga clic en **siguiente**, revise la configuración y, después, vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-symphony-connector"></a>Paso 4: supervisar el conector Symphony

Después de crear el conector Symphony, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y, a continuación, seleccione el conector **Symphony** para mostrar la página de flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
