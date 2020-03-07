---
title: Introducción a la exhibición avanzada de documentos electrónicos en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: En este artículo se describe cómo empezar a usar la exhibición avanzada de documentos electrónicos en Microsoft 365. Una vez que haya completado algunos pasos rápidos, la herramienta eDiscovery avanzado estará lista para usarse. El primer paso consiste en crear un caso y, a continuación, empezar a usar las funciones y características de eDiscovery avanzadas.
ms.openlocfilehash: b351524f1bcaa54360d9f7422c0955c5c4a35254
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557924"
---
# <a name="get-started-with-advanced-ediscovery"></a>Introducción a la exhibición avanzada de documentos electrónicos

EDiscovery avanzado en Microsoft 365 proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar datos que responden a las investigaciones internas y externas de su organización. No se necesita nada para implementar la exhibición avanzada de documentos electrónicos, pero hay algunas tareas de requisitos previos que debe realizar un administrador de ti y un administrador de exhibición de documentos electrónicos antes de que su organización pueda empezar a crear y usar casos de eDiscovery avanzados para administrar las investigaciones.

En este artículo se describen los pasos necesarios para configurar la exhibición avanzada de documentos electrónicos. Esto incluye garantizar las licencias adecuadas necesarias para acceder a la exhibición de documentos electrónicos avanzada y agregar custodios a los casos, así como asignar permisos a su equipo legal y de investigación para que puedan acceder a los casos y administrarlos. En este artículo también se proporciona una introducción de alto nivel sobre el uso de casos para administrar el flujo de trabajo de eDiscovery avanzado para una investigación legal.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Paso 1: comprobar y asignar las licencias adecuadas

La concesión de licencias para eDiscovery avanzado requiere la suscripción a la organización correspondiente y la licencia por usuario.

- **Suscripción de la organización:** Para obtener acceso a la exhibición avanzada de documentos electrónicos en el centro de cumplimiento de Microsoft 365 o el centro de cumplimiento de & de seguridad de Office 365, su organización debe tener una de las siguientes opciones:

  - Suscripción a Microsoft 365 E5 o a Office 365 E5
  
  - Suscripción a Microsoft 365 E3 con el complemento de cumplimiento de E5
  
  - Suscripción a Office 365 E3 con el complemento de cumplimiento avanzado

  Si no tiene un plan de Microsoft 365 E5 existente y desea probar la exhibición avanzada de documentos electrónicos, puede [Agregar microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) a su suscripción existente de Office 365 o [registrarse para obtener una versión de prueba](https://www.microsoft.com/microsoft-365/enterprise) de Microsoft 365 E5.

- **Licencias por usuario:** Para agregar un usuario como custodio en un caso de exhibición de documentos electrónicos, el usuario debe tener asignada una de las siguientes licencias, según la suscripción de la organización:

  - Microsoft 365: los usuarios deben tener asignada una licencia de Microsoft 365 E5 o una licencia de complemento de cumplimiento E5.

  - Office 365: los usuarios deben tener asignada una licencia de Office 365 E5 o una licencia de complemento de cumplimiento avanzado.

   Para obtener información acerca de cómo asignar licencias, consulte [asignar licencias a los usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Los usuarios solo necesitan una licencia E5 (o la licencia de complemento correspondiente) para agregarse como custodios a un caso de eDiscovery avanzado. Los administradores de ti, los administradores de eDiscovery, los abogados, los parajudiciales o los investigadores que usan eDiscovery avanzado para administrar los casos y revisar los datos de caso no necesitan una licencia E5 o de complemento.

## <a name="step-2-assign-ediscovery-permissions"></a>Paso 2: asignar permisos de exhibición de documentos electrónicos

Para obtener acceso a la exhibición de documentos electrónicos avanzada o agregar como miembro de un caso de exhibición de documentos electrónicos avanzado, un usuario debe tener asignados los permisos adecuados. En concreto, debe agregarse un usuario como miembro del grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento de Office 365. Los miembros de este grupo de roles pueden crear y administrar casos de eDiscovery avanzados. Pueden agregar y quitar miembros, ubicar custodios y ubicaciones de contenido en retención, administrar notificaciones de retención legal, crear y editar búsquedas asociadas en un caso, agregar resultados de búsqueda a un conjunto de revisión, analizar datos en un conjunto de revisión, y exportar y descargar desde una configuración avanzada. caso de exhibición de documentos electrónicos.

Complete los siguientes pasos para agregar usuarios al grupo de roles eDiscovery Manager:

1. Vaya a [https://protection.office.com/permissions](https://protection.office.com/permissions) e inicie sesión con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En la página **permisos** , seleccione el grupo de roles **Administrador de exhibición** de documentos electrónicos.

3. En la página desplegable administrador de exhibición de documentos electrónicos, haga clic en **Editar** junto a la sección **Administrador de exhibición** de documentos electrónicos.

4. En la página **elegir administrador de exhibición** de documentos electrónicos del asistente editar grupo de roles, haga clic en **elegir administrador de detección**.

5. Haga clic en **Agregar** y, a continuación, active la casilla de verificación para todos los usuarios que desee agregar al grupo de roles.

6. Haga clic en **Agregar** para agregar los usuarios seleccionados y, a continuación, haga clic en **listo**.

7. Haga clic en **Guardar** para agregar los usuarios al grupo de roles y, a continuación, haga clic en **cerrar** para completar el paso.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Más información sobre el grupo de roles de eDiscovery Manager

Hay dos subgrupos en el grupo de roles de administrador de exhibición de documentos electrónicos. La diferencia entre estos subgrupos se basa en el ámbito.

- **Administrador de eDiscovery:** Permite ver y administrar los casos de eDiscovery avanzados que crean o de los que son miembros. Si otro administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo administrador de eDiscovery como miembro de ese caso, el segundo administrador de eDiscovery no podrá ver ni abrir el caso en la página de exhibición de documentos electrónicos avanzada en el centro de cumplimiento. En general, la mayoría de las personas de su organización se pueden agregar al subgrupo eDiscovery Manager.

- **Administrador de eDiscovery:** Puede realizar todas las tareas de administración de casos que puede realizar un administrador de exhibición de documentos electrónicos. Además, un administrador de exhibición de documentos electrónicos puede:

  - Ver todos los casos que se enumeran en la página exhibición avanzada de documentos electrónicos.
  
  - Administrar cualquier caso en la organización después de que se agreguen como miembro del caso.

  - Obtenga acceso y exporte datos de casos para cualquier caso de la organización.

  Debido al amplio ámbito de acceso, una organización solo debe tener unos pocos administradores que sean miembros del subgrupo administradores de eDiscovery.

Para obtener más información acerca de los permisos de exhibición de documentos electrónicos y una descripción de cada rol asignado al grupo de roles eDiscovery Manager, consulte [asignar permisos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Paso 3: configurar las opciones globales de eDiscovery avanzado

El último paso para completar antes de que los usuarios de la organización comiencen a crear y a usar casos es configurar las opciones globales que se aplican a todos los casos de la organización. En este momento, la única configuración global que está disponible es la *detección de privilegios de clientes de abogados* (la configuración global estará disponible en el futuro). Esta configuración permite que el modelo de privilegios abogado-Client se ejecute al analizar datos en un conjunto de revisión. El modelo usa el aprendizaje de la máquina para determinar la probabilidad de que un documento incluya contenido que sea legal por naturaleza. También compara los participantes de los documentos con una lista de abogados (que se envía al configurar el modelo) para determinar si un documento tiene al menos un participante que es un abogado.

Para obtener más información acerca de la configuración y el uso del modelo de detección de privilegios de clientes de abogados, consulte [set up abogado-Client Privilege Detection in Advanced eDiscovery](attorney-privilege-detection.md).

> [!NOTE]
> Este es un paso opcional que puede realizar en cualquier momento. No implementar el modelo de detección de privilegios de clientes de abogados no impide crear y usar casos de exhibición de documentos electrónicos avanzada.

## <a name="step-4-create-an-advanced-ediscovery-case"></a>Paso 4: crear un caso de exhibición avanzada de documentos electrónicos

El siguiente paso es crear un caso y empezar a usar la exhibición avanzada de documentos electrónicos. Complete los siguientes pasos para crear un caso y agregar miembros. El usuario que crea el caso se agrega automáticamente como miembro.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con las credenciales de la cuenta de usuario a la que se le han asignado los permisos de eDiscovery adecuados. Los miembros del grupo de roles administración de la organización también pueden crear casos de eDiscovery avanzados.

2. En la navegación de la izquierda del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo**y, a continuación, en **eDiscovery > avanzadas**.

3. En la página **EDiscovery avanzado** , haga clic en la pestaña **casos** y, a continuación, haga clic en **crear un caso**.

4. En la página nuevo elemento emergente de **exhibición** de documentos electrónicos, indique un nombre (obligatorio) y, a continuación, escriba un número de caso y una descripción opcionales. El nombre del caso debe ser único en la organización.

5. Haga clic en **Guardar** para crear el caso.

   Se crea el nuevo caso y se muestra la pestaña **configuración** en el nuevo caso. 

6. En el cuadro **permisos de acceso &** de la ficha **configuración** , haga clic en **seleccionar**y, a continuación, haga clic en **Actualizar**.

7. Haga clic en **Actualizar**.

8. En la página desplegable **administrar este caso** , en **administrar miembros**, haga clic en **Agregar** para agregar miembros al caso.

9. En la lista de personas, active la casilla de verificación situada junto a los nombres de las personas que desea agregar al caso. Como se ha explicado anteriormente, asegúrese de que a las personas que agregue al caso se les haya asignado el permiso de eDiscovery adecuado.

10. Una vez que haya seleccionado a los usuarios para agregar como miembros del caso, haga clic en **Agregar**.

11. En la página desplegable **administrar este caso** , haga clic en **Guardar** para guardar la nueva lista de miembros de mayúsculas y minúsculas.

12. Haga clic en la pestaña **Inicio** para ir a la Página principal del caso.

## <a name="explore-the-advanced-ediscovery-workflow"></a>Explorar el flujo de trabajo avanzado de eDiscovery

Para empezar a usar la exhibición avanzada de documentos electrónicos, este es un flujo de trabajo sencillo que se alinea con las [prácticas comunes de eDiscovery](overview-ediscovery-20.md#alignment-with-edrm). En cada uno de estos pasos también se resaltará alguna funcionalidad avanzada de exhibición de documentos electrónicos avanzada que puede explorar.

![Flujo de trabajo avanzado de eDiscovery](../media/AeDWorkflow.png)

1. **[Agregar custodios a un caso](add-custodians-to-case.md)**. El primer paso tras crear un caso es agregar custodios. Un *custodio* es una persona con control administrativo de un documento o un archivo electrónico que puede ser relevante para el caso. Estas son algunas de las cosas que ocurren (o que puede hacer) cuando agrega custodios a un caso:

   - Los datos del buzón de correo de Exchange, la cuenta de OneDrive y los grupos de Microsoft Teams o Yammer a los que pertenece el custodio pueden "marcarse" como datos de apoyo en el caso.
  
   - Los datos de custodios se vuelven a indexar (por un proceso denominado *indexación avanzada*). Esto ayuda a optimizar la búsqueda en el paso siguiente.
  
   - Puede poner una retención en los datos de custodios. Así se conservan los datos que puedan ser relevantes para el caso durante la investigación.
  
   - Puede asociar otros orígenes de datos a un custodio (por ejemplo, puede asociar un sitio de SharePoint o un grupo de Office 365 con un custodio) para que estos datos se puedan reindizar, poner en suspensión y realizar búsquedas, igual que los datos del buzón de correo de la custodio o de la cuenta de OneDrive.

   - Puede usar el [flujo de trabajo de comunicaciones](managing-custodian-communications.md) en la exhibición avanzada de documentos electrónicos para enviar una notificación de retención legal a los custodios.

2. **[Buscar orígenes de datos de apoyo para datos relevantes para el caso](collecting-data-for-ediscovery.md)**. Después de agregar custodios a un caso, use la herramienta de búsqueda integrada para buscar en las ubicaciones de datos del custodio los datos que puedan ser relevantes para el caso. Se usan palabras clave, propiedades y condiciones para [crear consultas de búsqueda](building-search-queries.md) que devuelven los resultados de la búsqueda con los datos que es más probable que sean relevantes para el caso. También puede hacer lo siguiente:

   - Ver las [estadísticas de búsqueda](search-statistics.md) que pueden ayudarle a refinar una consulta de búsqueda para restringir los resultados.

   - Obtenga una vista previa de los resultados de la búsqueda para comprobar rápidamente si se encuentran los datos relevantes.

   - Revise una consulta y vuelva a ejecutar la búsqueda.

3. **[Agregar datos a un conjunto de revisión](add-data-to-review-set.md)**. Una vez que haya configurado y comprobado que una búsqueda devuelve los datos deseados, el siguiente paso consiste en agregar los resultados de la búsqueda a un conjunto de revisión. Cuando se agregan datos a un conjunto de revisión, los elementos se copian de su ubicación original en una ubicación de almacenamiento segura de Azure. Los datos se vuelven a indizar para optimizarlos para realizar búsquedas exhaustivas y rápidas al revisar y analizar elementos en el conjunto de revisiones. Además, también puede [Agregar datos que no son de Office 365 a un conjunto de revisión](load-non-office-365-data-into-a-review-set.md).

   También hay un tipo especial de conjunto de revisión al que puede agregar datos, denominados un *conjunto de revisión de conversación*. Estos tipos de revisión proporcionan capacidades de reconstrucción de conversaciones para reconstruir, revisar y exportar conversaciones encadenadas como las de Microsoft Teams. Para obtener más información, vea [revisar conversaciones en EDiscovery avanzado](conversation-review-sets.md).

4. **Revisar y analizar los datos de un conjunto de revisión**. Ahora que los datos están en un conjunto de revisión, puede usar una amplia variedad de herramientas y capacidades para ver y analizar los datos de casos con el objetivo de reducir el conjunto de datos a lo más relevante para el caso que está investigando. Esta es una lista de algunas herramientas y capacidades que puede usar durante este proceso.

   - [Ver documentos](view-documents-in-review-set.md). Esto incluye ver los metadatos de cada documento en un conjunto de revisión y ver el documento en su versión nativa o de texto.

   - [Crear consultas y filtros](review-set-search.md). Las consultas de búsqueda se crean con diversos criterios de búsqueda (incluida la capacidad de buscar en todas [las propiedades de los metadatos de archivo](document-metadata-fields-in-advanced-ediscovery.md)) para refinar y refinar los datos de casos a lo que sea más relevante para el caso. También puede usar la revisión Set filters para aplicar rápidamente condiciones adicionales a los resultados de una consulta de búsqueda para restringir aún más los resultados. 

   - [Cree y use etiquetas](tagging-documents.md). Puede aplicar etiquetas a los documentos en un conjunto de revisiones para identificar los que responden (o que no responden a las mayúsculas y minúsculas) y, a continuación, usar esas etiquetas al crear consultas de búsqueda para incluir o excluir los documentos etiquetados. También puede etiquetar para determinar los documentos que se van a exportar.

   - [Anotar y censurar documentos](view-documents-in-review-set.md#annotate-view). Puede usar la herramienta de anotación en una revisión para anotar documentos y censurar el contenido de los documentos como producto de trabajo. Durante la revisión, se genera una versión en PDF de un documento anotado o redactado para reducir el riesgo de exportar la versión nativa no censurada del documento.

   - [Analizar datos de casos](analyzing-data-in-review-set.md). La funcionalidad de análisis en eDiscovery avanzado es eficaz. Después de ejecutar análisis en los datos del conjunto de revisiones, realizaremos análisis como la detección de duplicados, el procesamiento de mensajes de correo electrónico y los temas que pueden ayudarle a reducir el volumen de documentos que tiene que revisar. También se genera un informe de análisis que resume el resultado de la ejecución de análisis. Como se explicó anteriormente, la ejecución de análisis también ejecuta [el modelo de detección de privilegios de clientes de abogados](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).

5. **Exportar y descargar datos de casos**. Un paso final después de recopilar, revisar y analizar los datos de casos es exportarlos de la exhibición de documentos electrónicos avanzada para su revisión externa o su revisión por parte de personas ajenas al equipo de investigación. La exportación de datos es un proceso de dos pasos. El primer paso consiste en [exportar](export-documents-from-review-set.md) el conjunto de revisión y en una ubicación de almacenamiento de Azure diferente (una proporcionada por Microsoft o una administrada por la organización). A continuación, se usa el explorador de Azure Storage para [Descargar](download-export-jobs.md) los datos en un equipo local. Además de los archivos de datos exportados, los Contains del paquete de exportación también contienen un informe de exportación, un informe de Resumen y un informe de errores.
