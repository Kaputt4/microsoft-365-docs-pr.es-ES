---
title: Configurar un conector para archivar datos de Workplace desde Facebook en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Workplace desde Facebook, que se archiva en el sitio Merge1 de Veritas, en Microsoft 365. La configuración de un conector requiere que trabaje con Veritas Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 25221b1d71fe106f0f6dcf9c629414aeb0de8709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163834"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Configurar un conector para archivar datos de Workplace desde Facebook

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de Workplace desde Facebook a buzones de usuario de su organización de Microsoft 365. Veritas proporciona un conector [Workplace from Facebook](https://globanet.com/workplace/) configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido, como chats, datos adjuntos, publicaciones y vídeos de Workplace a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Una vez que los datos de Workplace se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. Usar Workplace from Facebook connector para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Información general sobre el archivado de datos de Workplace desde Facebook

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Workplace en Microsoft 365.

![Flujo de trabajo de archivado para Workplace desde datos de Facebook](../media/WorkplaceConnectorWorkflow.png)

1. Su organización trabaja con Workplace desde Facebook para configurar y configurar un sitio workplace.

2. Una vez cada 24 horas, los elementos de Workplace se copian en el sitio Veritas Merge1. El conector también convierte el contenido de estos elementos a un formato de mensaje de correo electrónico.

3. El conector Workplace from Facebook que crea en el Centro de cumplimiento de Microsoft 365, se conecta a Veritas Merge1 todos los días y transfiere los elementos workplace a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en el paso 3. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Workplace desde Facebook** y los elementos workplace se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email.* Cada elemento workplace contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante de chat o publicación.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de soporte al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Cree una integración personalizada en para recuperar datos de Workplace a través de API con fines de cumplimiento y https://my.workplace.com/work/admin/apps/ exhibición de documentos electrónicos.

   Al crear la integración, la plataforma Workplace genera un conjunto de credenciales únicas que se usan para generar tokens que se usan para la autenticación. Estos tokens se usan en el Asistente para la configuración del conector workplace de Facebook en el paso 2. Para obtener instrucciones paso a paso sobre cómo crear las aplicaciones, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

- El usuario que crea el conector Workplace from Facebook en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores de datos** del Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>Paso 1: Configurar el conector workplace from Facebook

El primer paso es obtener acceso a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector para datos de Workplace.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos** Workplace desde  >  **Facebook**.

2. En la página **Descripción del producto Workplace from Facebook,** haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector Workplace from Facebook en el sitio Veritas Merge1

El segundo paso es configurar el conector Workplace from Facebook en el sitio Merge1. Para obtener información sobre cómo configurar workplace desde el conector de Facebook, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar usuarios externos a usuarios de Microsoft 365,** habilite la asignación automática de usuarios. Los elementos workplace incluyen una propiedad denominada *Correo* electrónico que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>Paso 4: Supervisar el área de trabajo desde el conector de Facebook

Después de crear el conector Workplace from Facebook, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **Workplace from Facebook** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.