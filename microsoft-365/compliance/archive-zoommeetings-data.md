---
title: Configurar un conector para archivar datos de reuniones de Zoom en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Veritas Zoom Meetings en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: f776fe3d03f8674a698b5c8fe2f355aa5635577f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327313"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Configurar un conector para archivar datos de reuniones de Zoom

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de reuniones de Zoom a buzones de usuario de su Microsoft 365 organización. Veritas proporciona un [conector de](https://globanet.com/zoom/) reuniones de Zoom que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido de las reuniones (incluidos los chats, los archivos grabados y los metadatos) de la cuenta de Reuniones de Zoom a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Después de almacenar los datos de reuniones de Zoom en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de reuniones de Zoom para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Información general sobre el archivado de datos de reuniones de zoom

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de reuniones de Zoom en Microsoft 365.

![Flujo de trabajo de archivado de reuniones de Zoom.](../media/ZoomMeetingsConnectorWorkflow.png)

1. Su organización trabaja con Reuniones de Zoom para configurar y configurar un sitio de reuniones de zoom.

2. Una vez cada 24 horas, los elementos de reunión de Zoom Meetings se copian en el sitio Veritas Merge1. El conector también convierte el contenido de las reuniones a un formato de mensaje de correo electrónico.

3. El conector de reuniones de Zoom que crea en el Centro de cumplimiento de Microsoft 365, se conecta a Veritas Merge1 todos los días y transfiere los mensajes de reunión a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos de reunión convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* y la asignación automática de usuarios, tal como se describe en el paso 3. Se crea una nueva subcarpeta en la carpeta Bandeja de entrada denominada Reuniones de zoom en los **buzones** de usuario y los elementos de la reunión se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email* . Cada elemento de reunión contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante de la reunión.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Obtenga el nombre de usuario y la contraseña de la cuenta de Zoom Business o Zoom Enterprise de la organización. Deberá iniciar sesión en esta cuenta en el paso 2 al configurar el conector de reuniones de zoom.

- Cree las siguientes aplicaciones en [Zoom Marketplace](https://marketplace.zoom.us):

  - Aplicación OAuth

  - Aplicación JWT

  Después de crear estas aplicaciones, la plataforma zoom genera un conjunto de credenciales únicas que se usan para generar los tokens. Estos tokens se usan para autenticar el conector cuando se conecta a su cuenta de Zoom y copia elementos en el sitio Merge1. Usará estos tokens al configurar el conector de zoom en el paso 2.

  Para obtener instrucciones paso a paso sobre cómo crear las aplicaciones OAuth y JWT, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- El usuario que crea el conector de reuniones de zoom en el paso 1 (y lo completa en el paso 3) debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas se encuentra en versión preliminar pública en GCC entornos de la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Paso 1: Configurar el conector de reuniones de zoom

El primer paso es obtener acceso a **los** conectores de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector de reuniones de zoom.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, **haga clic en Conectores** **de datosZoom** >  Reuniones.

2. En la página **Descripción del producto Reuniones de Zoom** , haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Paso 2: Configurar el conector de reuniones de zoom

El segundo paso es configurar el conector de reuniones de Zoom en el sitio Merge1. Para obtener más información acerca de cómo configurar el conector de reuniones de Zoom en el sitio veritas merge1, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

Después de hacer **clic en Guardar & finalizar**, se muestra  la página Asignación de usuario en el asistente para conector en Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

1. En la **página Asignar usuarios externos Microsoft 365 usuarios**, habilite la asignación automática de usuarios.

   Los elementos de Reuniones de Zoom incluyen una propiedad denominada *Correo* electrónico que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario

2. Haga **clic en** Siguiente, revise la configuración y vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Paso 4: Supervisar el conector de reuniones de zoom

Después de crear el conector de reuniones de zoom, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic **en Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector de reuniones **de Zoom** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.

- Para que el conector de reuniones de Zoom funcione, debe habilitar las grabaciones al configurar reuniones de zoom.