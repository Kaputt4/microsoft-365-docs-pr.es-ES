---
title: Configurar un conector para archivar los datos de Zoom Meetings en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos de Veritas Zoom Meetings en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 91414dd58cb8880b0900846c6dd106f14bae42f3
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095042"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Configuración de un conector para archivar los datos de Zoom Meetings

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Use un conector veritas en el portal de cumplimiento de Microsoft Purview para importar y archivar datos de Reuniones de Zoom a buzones de correo de usuario de la organización de Microsoft 365. Veritas proporciona un conector [de Reuniones de Zoom](https://globanet.com/zoom/) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importarlos a Microsoft 365. El conector convierte el contenido de las reuniones (incluidos chats, archivos grabados y metadatos) de la cuenta de Zoom Meetings a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Después de almacenar los datos de Zoom Meetings en buzones de usuario, puede aplicar características de Microsoft Purview como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de Zoom Meetings para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Información general sobre el archivado de datos de Zoom Meetings

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de Zoom Meetings en Microsoft 365.

![Zoom: flujo de trabajo de archivado de reuniones.](../media/ZoomMeetingsConnectorWorkflow.png)

1. Su organización trabaja con Reuniones de Zoom para configurar y configurar un sitio de reuniones de Zoom.

2. Una vez cada 24 horas, los elementos de reuniones de Zoom Meetings se copian en el sitio Veritas Merge1. El conector también convierte el contenido de las reuniones en un formato de mensaje de correo electrónico.

3. El conector zoom meetings que se crea en el portal de cumplimiento, se conecta a Veritas Merge1 todos los días y transfiere los mensajes de reunión a una ubicación segura Azure Storage en la nube de Microsoft.

4. El conector importa los elementos de reunión convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* y la asignación automática de usuarios, como se describe en el paso 3. Se crea una nueva subcarpeta en la carpeta Bandeja de entrada denominada **Reuniones de Zoom en los buzones** de usuario y los elementos de reunión se importan a esa carpeta. Para ello, el conector usa el valor de la propiedad *Email* . Cada elemento de reunión contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante de la reunión.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Obtenga el nombre de usuario y la contraseña de la cuenta de Zoom Business o Zoom Enterprise de su organización. Tendrá que iniciar sesión en esta cuenta en el paso 2 al configurar el conector de Zoom Meetings.

- Cree las siguientes aplicaciones en [Zoom Marketplace](https://marketplace.zoom.us):

  - Aplicación OAuth

  - Aplicación JWT

  Después de crear estas aplicaciones, la plataforma Zoom genera un conjunto de credenciales únicas que se usan para generar los tokens. Estos tokens se usan para autenticar el conector cuando se conecta a la cuenta de Zoom y copia los elementos en el sitio Merge1. Usará estos tokens al configurar el conector zoom en el paso 2.

  Para obtener instrucciones paso a paso sobre cómo crear las aplicaciones OAuth y JWT, consulte [Merge1 Third-Party Connectors User Guide(Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)).

- Al usuario que crea el conector de Zoom Meetings en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Paso 1: Configurar el conector de Zoom Meetings

El primer paso consiste en acceder a los **conectores de datos** en el portal de cumplimiento y crear un conector de Zoom Meetings.

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com/) continuación, haga clic en **Conectores de** >  **datosZoom Reuniones**.

2. En la página de descripción del producto **Zoom Meetings** , haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Paso 2: Configurar el conector de Zoom Meetings

El segundo paso consiste en configurar el conector zoom meetings en el sitio Merge1. Para obtener más información sobre cómo configurar el conector de Zoom Meetings en el sitio veritas merge1, consulte [la Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

Después de hacer clic en **Guardar & finalizar**, se muestra la página **Asignación** de usuarios del asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

1. En la página **Asignar usuarios externos a Microsoft 365 usuarios**, habilite la asignación automática de usuarios.

   Los elementos de Zoom Meetings incluyen una propiedad denominada *Correo electrónico* que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga clic en **Siguiente**, revise la configuración y vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Paso 4: Supervisión del conector zoom de reuniones

Después de crear el conector de Zoom Meetings, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector **Zoom Meetings** para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.

- Para que el conector Zoom Meetings funcione, debe habilitar las grabaciones al configurar Reuniones de Zoom.