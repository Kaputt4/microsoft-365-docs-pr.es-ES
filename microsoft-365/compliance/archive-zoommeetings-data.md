---
title: Configurar un conector para archivar datos de reuniones de zoom en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Globanet reuniones de zoom en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: c7052e7f51108cac93ad8d87402a07acd12df28a
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956237"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data-preview"></a>Configurar un conector para archivar datos de reuniones de zoom (versión preliminar)

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de las reuniones de zoom en los buzones de usuario de la organización 365 de Microsoft. Globanet proporciona un conector de [reuniones de zoom](https://globanet.com/zoom/) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar los elementos a Microsoft 365. El conector convierte el contenido de las reuniones (incluidos los chats, los archivos grabados y los metadatos) de la cuenta de reuniones de zoom a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de usuario en Microsoft 365.

Después de almacenar los datos de las reuniones de zoom en los buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la exhibición de documentos electrónicos, las directivas de retención y las etiquetas de retención, y el cumplimiento de la comunicación. El uso de un conector de reuniones de zoom para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Información general sobre el archivado de datos de reuniones de zoom

La siguiente introducción explica el proceso de uso de un conector para archivar datos de reuniones de zoom en Microsoft 365.

![Zoom para reuniones archivado flujo de trabajo](../media/ZoomMeetingsConnectorWorkflow.png)

1. Su organización trabaja con reuniones de zoom para instalar y configurar un sitio de reuniones de zoom.

2. Una vez cada 24 horas, los elementos de reunión de las reuniones de zoom se copian en el sitio de Merge1 de Globanet. El conector también convierte el contenido de las reuniones en un formato de mensaje de correo electrónico.

3. El conector de reuniones de zoom que ha creado en el centro de cumplimiento de Microsoft 365, se conecta a Globanet Merge1 cada día y transfiere los mensajes de reunión a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa los elementos de reunión convertidos a los buzones de usuarios específicos usando el valor de la propiedad *email* y la asignación automática de usuarios, como se describe en el paso 3. En los buzones de usuario se crea una subcarpeta nueva en la carpeta Bandeja de entrada con el nombre opciones de **zoom** , y los elementos de la reunión se importan a esa carpeta. El conector lo hace mediante el valor de la propiedad *email* . Todos los elementos de reunión contienen esta propiedad, que se rellena con la dirección de correo electrónico de cada participante de la reunión.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para Microsoft Connectors. Para ello, póngase en contacto con el [soporte técnico de Globanet](https://globanet.com/ms-connectors-contact). Debe iniciar sesión en esta cuenta cuando cree el conector en el paso 1.

- Obtenga el nombre de usuario y la contraseña de la cuenta de zoom para la empresa o el zoom de la organización. Deberá iniciar sesión en esta cuenta en el paso 2 cuando configure el conector de reuniones de zoom.

- Cree las siguientes aplicaciones en el [Catálogo de soluciones de zoom](https://marketplace.zoom.us):

  - Aplicación de OAuth

  - Aplicación JWT

  Después de crear estas aplicaciones, la plataforma de zoom genera un conjunto de credenciales únicas usadas para generar los tokens. Estos tokens se usan para autenticar el conector cuando se conecta a la cuenta de zoom y copia elementos en el sitio de Merge1. Usará estos tokens al configurar el conector zoom en el paso 2.

  Para obtener instrucciones paso a paso sobre cómo crear las aplicaciones OAuth y JWT, consulte la [Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- El usuario que crea el conector de reuniones de zoom en el paso 1 (y lo completa en el paso 3) debe asignarse a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Paso 1: configurar el conector de reuniones de zoom

El primer paso es obtener acceso a los **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector de reuniones de zoom.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **Data Connectors**  >  **zoom Meetings**.

2. En la página Descripción del producto de las **reuniones más detalladas** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Paso 2: configurar el conector para reuniones de zoom

El segundo paso consiste en configurar el conector de reuniones de zoom en el sitio de Merge1. Para obtener más información acerca de cómo configurar el conector de reuniones de zoom en el sitio de Merge1 de Globanet, consulte [Merge1 guía del usuario de conectores de terceros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se le redirigirá al centro de cumplimiento de Microsoft 365, a la página **asignación de usuarios** del Asistente para el conector.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

1. En la página **asignar usuarios externos a Microsoft 365 usuarios** , habilite la asignación automática de usuarios.

   Zoom los elementos de reuniones incluyen una propiedad denominada *correo electrónico* que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. En la página **consentimiento del administrador** , haga clic en el botón **proporcionar consentimiento** . Se le redirigirá al sitio de Microsoft. Haga clic en **Aceptar** para proporcionar el consentimiento.
  
   La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Microsoft 365 y aceptar la solicitud de consentimiento. Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de administrador global para aceptar la solicitud.

3. Haga clic en **siguiente**, revise la configuración y vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Paso 4: supervisar el conector para reuniones de zoom

Después de crear el conector de reuniones de zoom, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y seleccione el conector **zoom para reuniones** para mostrar la página de flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos de más de 10 MB, pero el soporte para elementos de mayor tamaño estará disponible en una fecha posterior.

- Para que funcione el conector de reuniones de zoom, debe habilitar las grabaciones al configurar las reuniones de zoom.
