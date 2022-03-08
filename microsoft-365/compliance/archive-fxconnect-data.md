---
title: Configurar un conector para archivar fx Conectar datos en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Veritas FX Conectar en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: a625cc6d7367521ab30f4018b04f1ad8449efa55
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328307"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a>Configurar un conector para archivar datos Conectar FX

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de la plataforma de colaboración fx Conectar a los buzones de usuario de la Microsoft 365 organización. Veritas proporciona un [conector de Conectar FX](https://globanet.com/fx-connect/) que está configurado para capturar Conectar fx e importar esos elementos a Microsoft 365. El conector convierte el contenido de FX Conectar, como operaciones, mensajes y otros detalles de la cuenta fx Conectar de la organización, a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de almacenar Conectar fx en buzones de usuario, puede aplicar características de cumplimiento Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector Conectar FX para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-fx-connect-data"></a>Información general sobre el archivado de datos Conectar FX

En la siguiente introducción se explica el proceso de uso de un conector para archivar la información Conectar FX en Microsoft 365.

![Flujo de trabajo de archivado para fx Conectar datos.](../media/FXConnectConnectorWorkflow.png)

1. Su organización funciona con FX Conectar para configurar y configurar un sitio Conectar FX.

2. Una vez cada 24 horas, los elementos de fx Conectar cuentas se copian en el sitio Veritas Merge1. El conector también convierte los elementos Conectar FX a un formato de mensaje de correo electrónico.

3. El conector Conectar FX que crea en el Centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere los elementos de FX Conectar a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de **entrada denominada FX Conectar** en los buzones de usuario y los elementos se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email* . Cada elemento Conectar fx contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft.  Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector Conectar FX en el paso 1 (y lo completa en el paso 3) debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas se encuentra en versión preliminar pública en GCC entornos de la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-fx-connect-connector"></a>Paso 1: Configurar el conector de Conectar FX

El primer paso es obtener acceso a la página **Conectores** de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector para fx Conectar datos.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **Conectores** >  **de datosFX Conectar**.

2. En la **página Descripción Conectar** producto fx, haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-fx-connect-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector de Conectar FX en el sitio de Veritas Merge1

El segundo paso es configurar el conector de Conectar FX en el sitio Merge1. Para obtener información sobre cómo configurar el conector de Conectar FX, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).

Después de hacer **clic en Guardar & finalizar**, se muestra  la página Asignación de usuario en el asistente para conector en Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar FX Conectar a Microsoft 365 usuarios**, habilite la asignación automática de usuarios. Los elementos Conectar fx incluyen una propiedad denominada *Correo* electrónico, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-fx-connect-connector"></a>Paso 4: Supervisar el conector de Conectar FX

Después de crear el conector Conectar FX, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com/> y haga clic **en Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el **conector Conectar FX** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.