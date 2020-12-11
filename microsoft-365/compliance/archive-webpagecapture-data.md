---
title: Configurar un conector para archivar datos de la página web en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de captura de páginas web de Globanet en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: 5d793bea8a22d9908551fff67c9d27afffdf1d86
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619826"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a>Configurar un conector para archivar datos de la página web

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de páginas web en buzones de usuario de la organización 365 de Microsoft. Globanet proporciona un conector de [captura de página web](https://globanet.com/webpage-capture) que captura páginas web específicas (y cualquier vínculo en las páginas) en un sitio web específico o en un dominio completo. El conector convierte el contenido de la página web en un formato de archivo PDF, PNG o personalizado y, a continuación, adjunta los archivos convertidos a un mensaje de correo electrónico y, a continuación, importa esos elementos de correo electrónico a los buzones de usuario en Microsoft 365.

Una vez que el contenido de las páginas web se almacena en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, exhibición de documentos electrónicos y etiquetas de retención. El uso de un conector de captura de página web para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-webpage-data"></a>Información general sobre el archivado de datos de páginas web

En la siguiente introducción se explica el proceso de uso de un conector para archivar contenido de la página web en Microsoft 365.

![Flujo de trabajo de archivado para datos de páginas web](../media/WebPageCaptureConnectorWorkflow.png)

1. La organización trabaja con el origen de la página web para configurar y configurar un sitio de captura de páginas Web.

2. Una vez cada 24 horas, los elementos de los orígenes de la página web se copian en el sitio de Merge1 de Globanet. El conector también convierte y adjunta el contenido de una página web a un mensaje de correo electrónico.

3. El conector de captura de página web que crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio de Globanet Merge1 todos los días y transfiere los elementos de la página web a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa los elementos convertidos de la página web a los buzones de usuarios específicos mediante el valor de la propiedad *email* de la asignación automática de usuarios, como se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **captura de página web** en los buzones de usuario y los elementos de la página web se importan a esa carpeta. El conector lo hace mediante el valor de la propiedad *email* . Cada elemento de la página web contiene esta propiedad, que se rellena con las direcciones de correo electrónico que se proporcionan al configurar el conector de captura de la página web en el [paso 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site).

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para Microsoft Connectors. Para crear esta cuenta, póngase en contacto [con el soporte técnico de Globanet](https://globanet.com/ms-connectors-contact/). Iniciará sesión en esta cuenta cuando cree el conector en el paso 1.

- Necesita trabajar con el soporte técnico de Globanet para configurar un formato de archivo personalizado para convertir los elementos de la página web en. Para obtener más información, consulte la guía del usuario de los conectores de terceros de Merge1 en 

- El usuario que crea el conector de captura de página web en el paso 1 (y lo completa en el paso 3) debe asignarse a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a un grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-webpage-capture-connector"></a>Paso 1: configurar el conector de captura de la página web

El primer paso es obtener acceso a los **conectores de datos** y crear un conector para los datos de origen de la Página Web.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en  >  **captura de página web** de conectores de datos.

2. En la página Descripción del producto de **captura de página web** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a>Paso 2: configurar el conector de captura de la página web en el sitio de Merge1 de Globanet

El segundo paso consiste en configurar el conector de captura de la página web en el sitio de Merge1 de Globanet. Para obtener información acerca de cómo configurar el conector de captura de página web, consulte la [Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se muestra la página **asignación de usuarios** en el Asistente para conectores del centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de cumplimiento de Microsoft 365, siga los pasos que se indican a continuación:

1. En la página **asignar usuarios de captura de página web a usuarios de Microsoft 365** , habilite la asignación automática de usuarios. Los elementos de captura de la página web incluyen una propiedad denominada *email*, que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. Haga clic en **siguiente**, revise la configuración y vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-webpage-capture-connector"></a>Paso 4: supervisar el conector de captura de la página web

Después de crear el conector de captura de la página web, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y seleccione el conector de **captura de página web** para mostrar la página de flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
