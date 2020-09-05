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
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden configurar un conector para importar y archivar datos delimitados por texto de Globanet a Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: e57e9693da77a246bafcdf30561fd1414761355f
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399301"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data-preview"></a>Configurar un conector para archivar datos delimitados por texto (versión preliminar)

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos delimitados por texto a los buzones de usuario de la organización 365 de Microsoft. [Globanet](https://globanet.com/merge1/) proporciona un conector delimitado por texto que está configurado para capturar elementos de un origen de datos de terceros (de forma regular) e importar los elementos a Microsoft 365. El conector convierte el contenido del origen de datos delimitados por texto a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de almacenar datos delimitados por texto en los buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención y cumplimiento de la comunicación. El uso de un conector de reuniones de zoom para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

Una vez archivadas, las comunicaciones de origen delimitadas por texto pueden conservarse, supervisarse para cumplir el cumplimiento y recuperarse para la exhibición de documentos electrónicos y el gobierno de información interno.

## <a name="overview-of-archiving-the-text-delimited-source"></a>Información general sobre el archivado del origen delimitado por texto

En la siguiente introducción se explica el proceso de uso de un conector para archivar la información de origen delimitada por texto en Microsoft 365.

![Flujo de trabajo de archivado para datos delimitados por texto](../media/TextDelimitedConnectorWorkflow.png)

1. La organización trabaja con el origen de texto delimitado para configurar y configurar un sitio delimitado por texto.

2. Una vez cada 24 horas, los mensajes de chat desde el origen de texto delimitado se copian al sitio de Merge1 de Globanet. El conector también convierte el contenido en un formato de mensaje de correo electrónico.

3. El conector de texto delimitado que se crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa los elementos de mensaje convertidos a los buzones de usuarios específicos usando el valor de la propiedad *email* de la asignación automática de usuarios, como se describe en el paso 3. Se creará una nueva subcarpeta en la carpeta Bandeja de entrada denominada **texto delimitado por texto** en los buzones de usuario y los elementos del mensaje se importarán a esa carpeta. El conector lo hace mediante el valor de la propiedad *email* . Cada mensaje contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Merge1 de Globanet aceptando los términos y condiciones para el conector delimitado por texto. Para ello, póngase en contacto con el [soporte técnico de Globanet](https://globanet.com/contact-us). Debe iniciar sesión en esta cuenta cuando cree el conector en el paso 1.

- El usuario que crea el conector delimitado por texto en el paso 1 (y lo completa en el paso 3) debe estar asignado a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-text-delimited-connector"></a>Paso 1: configurar el conector delimitado por texto

El primer paso es obtener acceso a la página **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector para datos delimitados por texto.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **conectores**  >  **de datos delimitados por texto**.

2. En la página Descripción de producto **delimitado por texto** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a>Paso 2: configurar el conector de texto delimitado en el sitio de Merge1 de Globanet

El segundo paso consiste en configurar el conector de texto delimitado en el sitio Merge1. Para obtener información acerca de la configuración del conector de texto delimitado en el sitio de Merge1 de Globanet, consulte [Merge1 guía del usuario de conectores de terceros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Text-Delimited%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se le devolverá al centro de cumplimiento de Microsoft 365, a la página **asignación de usuarios** del Asistente para conector.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la página **asignar usuarios externos a Microsoft 365 usuarios** , habilite la asignación automática de usuarios. Los elementos de origen de texto delimitados incluyen una propiedad denominada *email*, que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. En la página **consentimiento del administrador** , haga clic en el botón **proporcionar consentimiento** . Se le redirigirá al sitio de Microsoft. Haga clic en **Aceptar** para proporcionar el consentimiento.

   La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Microsoft 365 y aceptar la solicitud de consentimiento. Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de administrador global para aceptar la solicitud.

3. Haga clic en **siguiente**, revise la configuración y, después, vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-text-delimited-connector"></a>Paso 4: supervisar el conector delimitado por texto

Después de crear el conector de texto delimitado, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y, a continuación, seleccione el conector **delimitado por texto** para mostrar la página de flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos de más de 10 MB, pero el soporte para elementos de mayor tamaño estará disponible en una fecha posterior.
