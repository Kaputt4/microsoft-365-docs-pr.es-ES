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
description: Los administradores pueden configurar un conector para importar y archivar datos EML desde Globanet a Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: c11d66774a61fa20a533b5c906b3c8601659c1fe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200223"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a>Configurar un conector para archivar datos EML

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos EML en buzones de usuario de la organización 365 de Microsoft. EML es la extensión de archivo de un mensaje de correo electrónico guardado en un archivo. El conector convierte el contenido de un elemento del formato de origen en un formato de mensaje de correo electrónico y, a continuación, importa el elemento a un buzón de usuario.

Una vez que los mensajes EML se almacenan en buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención y cumplimiento de la comunicación. El uso de un conector EML para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-eml-data"></a>Información general sobre el archivado de datos EML

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos EML en Microsoft 365.

![Flujo de trabajo de archivado para datos EML](../media/EMLConnectorWorkflow.png)

1. Su organización trabaja con el origen de EML para configurar y configurar un sitio EML.

2. Una vez cada 24 horas, los elementos de contenido del origen EML se copian en el sitio de Merge1 de Globanet. Durante este proceso, el contenido de un archivo EML se convierte en un formato de mensaje de correo electrónico.

3. El conector EML que crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa los elementos de mensaje convertidos a los buzones de usuarios específicos usando el valor de la propiedad *email* del proceso de asignación automática de usuarios que se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Durante este proceso, se crea una subcarpeta de la carpeta Bandeja de entrada denominada **EML**en los buzones de usuario y los elementos EML se importan a esa carpeta. El conector lo hace mediante el valor de la propiedad *email* . Cada mensaje contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento de contenido.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para Microsoft Connectors. Para ello, póngase en contacto con el [soporte técnico de Globanet](https://globanet.com/ms-connectors-contact). Debe iniciar sesión en esta cuenta cuando cree el conector en el paso 1.

- El usuario que crea el conector EML en el paso 1 (y lo completa en el paso 3) debe asignarse a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-an-eml-connector"></a>Paso 1: configurar un conector EML

El primer paso es obtener acceso a la página **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector para datos EML.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **conectores de datos**  >  **EML**.

2. En la página de descripción de producto **EML** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a>Paso 2: configurar el conector EML en el sitio de Merge1 de Globanet

El segundo paso consiste en configurar el conector EML en el sitio de Merge1 de Globanet. Para obtener información sobre cómo configurar el conector EML, consulte la [Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se le devolverá al centro de cumplimiento de Microsoft 365, a la página **asignación de usuarios** del Asistente para conector.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la página **asignar usuarios externos a Microsoft 365 usuarios** , habilite la asignación automática de usuarios. Los elementos de origen de EML incluyen una propiedad denominada *email*, que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de 365 de Microsoft, los elementos EML se importan al buzón de correo del usuario.

2. En la página **consentimiento del administrador** , haga clic en el botón **proporcionar consentimiento** . Se le redirigirá al sitio de Microsoft. Haga clic en **Aceptar** para proporcionar el consentimiento.

   La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Microsoft 365 y aceptar la solicitud de consentimiento. Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de administrador global para aceptar la solicitud.

3. Haga clic en **siguiente**, revise la configuración y, después, vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-eml-connector"></a>Paso 4: supervisar el conector EML

Después de crear el conector EML, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y, a continuación, seleccione el conector **EML** para mostrar la página de flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
