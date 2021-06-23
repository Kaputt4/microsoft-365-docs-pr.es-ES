---
title: Archivar datos de la plataforma CellTrust SL2 para Microsoft 365
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
description: Obtenga información sobre cómo configurar y usar un conector de datos CellTrust SL2 para importar y archivar datos de comunicaciones móviles.
ms.openlocfilehash: 0929a92978f9b48d40153b3cc7328e5e05b54fd0
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097223"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365-preview"></a>Archivar datos de CellTrust SL2 a Microsoft 365 (versión preliminar)

CellTrust SL2 captura datos de comunicaciones móviles e se integra con las tecnologías de archivado líderes para cumplir los requisitos de detección electrónica de normativas como FINRA, HIPAA, FOIA y TCPA. SL2 Data Connector importa elementos de comunicación móvil a Microsoft 365. En este artículo se describe el proceso de integración de SL2 con Microsoft 365 mediante cellTrust SL2 Data Connector para el archivado. Al completar este proceso se supone que se ha suscrito al servicio CellTrust SL2 y que está familiarizado con la arquitectura SL2. Para obtener información acerca de SL2, vea <www.celltrust.com>.

Después de importar datos a buzones de usuario en Microsoft 365, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención de Microsoft 365 y cumplimiento de comunicaciones. El uso de CellTrust SL2 Data Connector para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a>Información general sobre el archivado con CellTrust SL2 Data Connector

La plataforma SL2 de CellTrust captura datos de comunicación de varios orígenes. Los orígenes de datos sl2 son de persona a persona (P2P) o de aplicación a persona (A2P). El proceso descrito en este artículo solo pertenece a orígenes de datos P2P. Para todos los orígenes de datos P2P, al menos una parte de la colaboración es un usuario sl2 que está suscrito al servicio SL2. En la siguiente introducción se explica el proceso de uso de CellTrust SL2 Data Connector en Microsoft 365.

![Flujo de trabajo de archivado para el servicio CellTrust SL2](../media/CellTrustSL2ConnectorWorkflow.png)

1. Los usuarios de SL2 envían y reciben datos desde y hacia los servicios SL2 en la Microsoft Azure nube.

2. Su organización tiene un dominio SL2 en el entorno de servicio en la nube sl2 de CellTrust. El dominio puede tener una o más unidades organizativas (UNIDADES organizativas). El servicio en la nube SL2 transfiere los datos a un área altamente segura en la plataforma Microsoft Azure, de modo que los datos no abandone nunca el Microsoft Azure web. Según el plan SL2 (Enterprise, SMB o Government), el dominio se hospeda en Microsoft Azure Global o Microsoft Azure Government.

3. Después de crear CellTrust SL2 Data Connector, el dominio y las US (independientemente del plan SL2), comiencen a enviar datos a Microsoft 365. La fuente de datos está estructurada para admitir informes basados en orígenes de datos, US o el dominio por sí mismo. Como resultado, la organización solo necesita un conector para alimentar todos los orígenes de datos para Microsoft 365.

4. El conector crea una carpeta debajo de cada usuario asignado con una licencia Office 365 adecuada titulada **CellTrust SL2**. Esta asignación conecta un usuario de CellTrust SL2 a un buzón Office 365 mediante una dirección de correo electrónico. Si un identificador de usuario en CellTrust SL2 no coincide en Office 365, los datos del usuario no se archivarán.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Compruebe que tiene un dominio en el entorno de servicio en la nube de CellTrust SL2. Para obtener información adicional sobre cómo obtener un dominio SL2 de producción o prueba, [póngase en contacto con CellTrust](https://www.celltrust.com/contact-us/#form).

- Obtenga las credenciales para obtener acceso a la cuenta de administrador del dominio SL2.

- El usuario que crea el conector de datos de CellTrust SL2 en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-create-a-celltrust-sl2-connector"></a>Paso 1: Crear un conector CellTrust SL2

El primer paso es crear un conector de datos en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la **pestaña Información** general, haga clic **en Filtrar** y seleccione **Por CellTrust** y, a continuación, aplique el filtro.

   ![Configurar el filtro para mostrar conectores CellTrust](../media/DataConnectorsFilter.png)

3. Haga **clic en CellTrust SL2 (versión preliminar).**

4. En la **página de descripción del producto CellTrust SL2 (versión preliminar),** haga clic en Agregar **conector**.

5. En la **página Términos de** servicio, haga clic **en Aceptar**.

6. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**. El nombre que escriba identificará el conector en la **página Conectores de** datos después de crearlo.

7. En la página **Iniciar sesión en su cuenta de CellTrust,** haga clic en Iniciar sesión en **CellTrust**. Se le redirigirá a **CellTrust Portal para Microsoft 365** en una nueva ventana del explorador.

## <a name="step-2-select-the-domains-or-ous-to-archive"></a>Paso 2: Seleccionar los dominios o US que se archivarán

El siguiente paso es iniciar sesión en una cuenta de administrador para su dominio cellTrust SL2 y seleccionar los dominios y las US que se archivarán en Microsoft 365.

1. En la página CellTrust **Microsoft 365 Connector,** seleccione el entorno en el servicio en la nube sl2 para mostrar una página de inicio de sesión.

   Normalmente, debería ver una opción que represente el entorno. Sin embargo, si tiene dominios en más de un entorno, verá opciones para cada entorno. Después de realizar una selección, se le redirigirá a la página de inicio de sesión de SL2.

2. Inicie sesión con las credenciales de la cuenta de administrador de dominio o ou.

   Si inicia sesión como administrador de dominio SL2, verá el nombre de su dominio y las us en ese dominio. Si no tiene us, solo verá el nombre de su dominio. Si inicia sesión como administrador de unidad organizativa, solo verá el nombre de la unidad organizativa.

3. Habilite las unidades de negocio que desea archivar. Al seleccionar el dominio no se seleccionarán automáticamente las us. Debe habilitar cada unidad organizativa por separado para archivarla.

   ![Habilitar US para archivar](../media/EnableCellTrustOUs.png)

4. Cuando haya terminado con las selecciones, cierre la ventana del explorador y vuelva a la página del asistente en Centro de cumplimiento de Microsoft 365. Después de unos segundos, el asistente avanza automáticamente al siguiente paso de asignación de usuarios.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

El último paso es asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365.

1. En la **página Asignación de** usuario, seleccione Habilitar la asignación automática de usuarios si la dirección de correo electrónico de los usuarios es la misma en SL2 y Microsoft 365.  De lo contrario, debe cargar manualmente las direcciones de correo electrónico del usuario cargando un archivo CSV que asigna la dirección SL2 de los usuarios a su Microsoft 365 usuario.

2. Haga **clic en Siguiente,** revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

   El nuevo conector se agrega a la lista de la **página Conectores de** datos.

## <a name="get-help-from-celltrust"></a>Obtener ayuda de CellTrust

Consulte la página de soporte al cliente de [CellTrust](https://www.celltrust.com/contact-us/#support) para obtener más información sobre cómo ponerse en contacto con CellTrust para obtener ayuda con la configuración de un conector de datos de CellTrust SL2.

## <a name="more-information"></a>Más información

- Un administrador de dominio puede configurar un conector para el dominio o cualquier UO de ese dominio. Si usa la cuenta de administrador de unidad organizativa, solo puede configurar un conector para esa OU específica.

- Para completar correctamente los pasos anteriores, se le debe asignar una Microsoft 365 E5 licencia y tener los derechos Microsoft Office administradores adecuados.

- Para probar el nuevo conector, envíe un mensaje de texto con la aplicación móvil SL2 o desde el portal sl2. Vaya a su buzón Microsoft 365 y abra la **carpeta CellTrust SL2** en la Bandeja de entrada. Los mensajes de texto pueden tardar unos minutos en aparecer en el buzón.

- Muchas leyes y reglamentos requieren que la comunicación electrónica se conserve de forma que, cuando se solicite, se pueda producir como prueba. La detección electrónica (eDiscovery) se usa para cumplir con la producción de comunicaciones electrónicas. Enterprise Las soluciones de archivado de información (EIA) están diseñadas para realizar exhibición de documentos electrónicos y proporcionan características como la administración de directivas de retención, la clasificación de datos y la supervisión de contenido. Microsoft 365 ofrece una solución de retención a largo plazo para el cumplimiento de los reglamentos y estándares que afectan a su organización.

- El término *archivado tal* como se usa en este documento hace referencia al archivado en el contexto de uso dentro de una Enterprise de archivado de información (EIA). Las soluciones EIA tienen características de exhibición de documentos electrónicos que producen documentos para procedimientos legales, litigios, auditorías e investigaciones. El archivado en el contexto de copia de seguridad y restauración que se usa para la recuperación ante desastres y la continuidad empresarial no es el uso previsto del término dentro de este documento.
