---
title: Configurar un conector para archivar workplace desde datos de Facebook en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Workplace desde Facebook, que se archiva en el sitio Merge1 de Veritas, en Microsoft 365. La configuración de un conector requiere que trabaje con Veritas Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 0dbd1bfaeea6a42db03793941b1fea894ee391b5
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "65001469"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Configuración de un conector para archivar Workplace desde datos de Facebook

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Use un conector de Veritas en el portal de cumplimiento de Microsoft Purview para importar y archivar datos de Workplace desde Facebook a buzones de usuario de su organización Microsoft 365. Veritas proporciona un conector [workplace from Facebook](https://globanet.com/workplace/) que está configurado para capturar elementos del origen de datos de terceros (de forma periódica) e importarlos a Microsoft 365. El conector convierte el contenido, como chats, datos adjuntos, publicaciones y vídeos de Workplace en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Una vez que los datos de Workplace se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview, como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso del conector workplace from Facebook para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Introducción al archivado de workplace a partir de datos de Facebook

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de Workplace en Microsoft 365.

![Archivado del flujo de trabajo para Workplace a partir de datos de Facebook.](../media/WorkplaceConnectorWorkflow.png)

1. Su organización trabaja con Workplace from Facebook para configurar y configurar un sitio de Workplace.

2. Una vez cada 24 horas, los elementos de Workplace se copian en el sitio de Veritas Merge1. El conector también convierte el contenido de estos elementos en un formato de mensaje de correo electrónico.

3. El conector Workplace from Facebook que se crea en el portal de cumplimiento, se conecta a Veritas Merge1 todos los días y transfiere los elementos de Workplace a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en el paso 3. Se crea una subcarpeta de la carpeta Bandeja de entrada denominada **Workplace from Facebook** y los elementos workplace se importan a esa carpeta. Para ello, el conector usa el valor de la propiedad *Email* . Cada elemento workplace contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante de chat o publicación.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Cree una integración personalizada en https://my.workplace.com/work/admin/apps/ para recuperar datos de Workplace a través de las API con fines de cumplimiento y exhibición de documentos electrónicos.

   Al crear la integración, la plataforma Workplace genera un conjunto de credenciales únicas que se usan para generar tokens que se usan para la autenticación. Estos tokens se usan en el Asistente para la configuración del conector workplace from Facebook en el paso 2. Para obtener instrucciones paso a paso sobre cómo crear las aplicaciones, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

- Al usuario que crea el conector workplace from Facebook en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>Paso 1: Configurar el conector workplace from Facebook

El primer paso consiste en acceder a la página **Conectores de datos** del portal de cumplimiento y crear un conector para los datos de Workplace.

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com/) continuación, haga clic en **Conectores** >  **de datosTrabajo desde Facebook**.

2. En la página **de descripción del producto Workplace from Facebook** , haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector Workplace from Facebook en el sitio de Veritas Merge1

El segundo paso es configurar el conector Workplace from Facebook en el sitio Merge1. Para obtener información sobre cómo configurar el conector workplace from Facebook, consulte [la Guía del usuario de Merge1 Third-Party Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

Después de hacer clic en **Guardar & finalizar**, se muestra la página **Asignación** de usuarios del asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En la página **Asignar usuarios externos a Microsoft 365 usuarios**, habilite la asignación automática de usuarios. Los elementos de Workplace incluyen una propiedad denominada *Email* que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga clic en **Siguiente**, revise la configuración y, a continuación, vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>Paso 4: Supervisión del conector workplace from Facebook

Después de crear el conector workplace from Facebook, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector **Workplace from Facebook (Lugar de trabajo desde Facebook** ) para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.