---
title: Configurar un conector para archivar datos de MS SQL Database
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
description: Los administradores pueden configurar un conector para importar y archivar datos de MS SQL Database. Este conector permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 494e91085494ba027a80480faba3cfb189cbd928
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164221"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>Configurar un conector para archivar datos de MS SQL Database

Use un conector Veritas en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de MS SQL Database buzones de usuario de su Microsoft 365 organización. Veritas le proporciona un conector de MS SQL Database Importer que está configurado para capturar elementos de una base de datos mediante un archivo de configuración XML e importar esos elementos a Microsoft 365. El conector convierte el contenido de MS SQL Database a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Después de almacenar contenido de MS SQL Database en buzones de usuario, puede aplicar características de cumplimiento Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector SQL Database MS para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-the-ms-sql-data"></a>Información general sobre cómo archivar los datos SQL MS

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos SQL MS en Microsoft 365.

![Flujo de trabajo de archivado para datos SQL MS](../media/MSSQLDatabaseConnectorWorkflow.png)

1. Su organización trabaja con un proveedor de SQL Database MS para configurar y configurar un sitio de MS SQL Database MS.

2. Una vez cada 24 horas, los SQL Database MS se copian en el sitio Veritas Merge1. El conector también convierte este contenido en un formato de mensaje de correo electrónico.

3. El conector de MS SQL Database Importer que crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos SQL Database MS convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **MS SQL Database Importer** en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de la SQL Database MS contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://www.veritas.com/content/support/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector de MS SQL Database Importer en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol Exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página Conectores de datos del centro de Microsoft 365 cumplimiento. De forma predeterminada, este rol no se asigna a ningún grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>Paso 1: Configurar el conector MS SQL Database Importer

El primer paso consiste en obtener acceso a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft365 y crear un conector para MS SQL Database.

1. Vaya a y, a continuación, haga clic en [https://compliance.microsoft.com](https://compliance.microsoft.com) **Conectores** de  >  **datos MS SQL Database Importer**.

2. En la **página MS SQL Database Descripción del** producto del importador, haga clic en Agregar nuevo **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector de MS SQL Database Importer en el sitio de Veritas Merge1

El segundo paso es configurar el conector de MS SQL Database Importer en el sitio Merge1. Para obtener información sobre cómo configurar MS SQL Database Importer, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en Microsoft 365 centro de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector, siga estos pasos:

1. En la página Asignar **usuarios de MS SQL Database importador a Microsoft 365 usuarios,** habilite la asignación automática de usuarios. Los elementos de SQL Database MS incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>Paso 4: Supervisar el conector de SQL Database MS

Después de crear el conector de SQL Database MS, puede ver el estado del conector en el centro Microsoft 365 cumplimiento.

1. Vaya a <https://compliance.microsoft.com/> y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic en la **pestaña Conectores** y, a continuación, seleccione el conector **MS SQL Database** **Importer** para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.