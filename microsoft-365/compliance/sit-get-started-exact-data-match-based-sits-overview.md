---
title: Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información general sobre cómo crear tipos de información confidencial basados en coincidencias de datos exactas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a9fc1af50c329b96ff77108698c8bbf952813f7f
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359500"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos

## <a name="applies-to"></a>Se aplica a 

- [Nueva experiencia](sit-create-edm-sit-unified-ux-workflow.md)
- [Experiencia clásica](sit-create-edm-sit-classic-ux-workflow.md)

La creación y puesta a disposición de un tipo de información confidencial (SIT) basado en una coincidencia exacta de datos (EDM) es un proceso de varias fases. Puede usar la *nueva experiencia* de la *experiencia clásica*  existente o mediante PowerShell. Este artículo le ayuda a comprender las diferencias entre las dos experiencias y le ayuda a elegir la adecuada para sus necesidades.

Los SIT de EDM se pueden usar en:

- Prevención de pérdida de datos de Microsoft Purview
- Etiquetado automático (servicio y cliente)
- directivas de Administración de riesgos internos de Microsoft Purview
- Microsoft Purview eDiscovery
- Administración de riesgos internos de Microsoft Purview
- Microsoft Defender for Cloud Apps



## <a name="before-you-begin"></a>Antes de empezar

Familiarícese con los conceptos y terminología de estos artículos:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md)

## <a name="supported-regions"></a>Regiones admitidas

La coincidencia exacta de datos está disponible en estas regiones:

- Asia Pacífico
- Australia
- Brasil
- Canadá
- Europa
- Francia
- Alemania
- India
- Japón
- Corea
- Noruega
- Sudáfrica
- Suiza
- Emiratos Árabes Unidos
- Reino Unido
- Estados Unidos
- DoD de EE. UU.
- GCC de EE. UU.
- GCCH de EE. UU.

Puede averiguar en qué región hospeda el inquilino datos en reposo siguiendo los procedimientos descritos en [Where your Microsoft 365 customer data is stored and](../enterprise/o365-data-locations.md) refer to the data center city locations in the same article (Dónde se almacenan los datos del cliente de Microsoft 365) y haciendo referencia a las ubicaciones de la ciudad del centro de datos en el mismo artículo.

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe ser un administrador global, administrador de cumplimiento o administrador de Exchange Online para realizar las tareas descritas en este artículo. Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).

Consulte la [descripción del servicio de prevención de pérdida de datos](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) para obtener información completa sobre las licencias.

## <a name="portal-links-for-your-subscription"></a>Vínculos del portal para la suscripción

|Portal|World Wide/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Portal de Microsoft 365 Defender|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Portal de cumplimiento de Microsoft Purview.|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="new-edm-experience"></a>Nueva experiencia de EDM

La nueva experiencia de EDM combina la funcionalidad del esquema EDM y los asistentes de tipos de información confidencial de EDM en una única experiencia de usuario. La nueva experiencia agrega:

### <a name="simplified-workflow"></a>Flujo de trabajo simplificado

Con la nueva experiencia, el esquema y SIT se crean a través de una experiencia de usuario, lo que significa menos clics, una mejor orientación sobre la asignación de elementos primarios a SIT predeterminados y niveles de confianza predeterminados para las reglas.

Cuando necesite ver el estado de una SIT de EDM en el proceso de creación, la nueva experiencia informa sobre esto en la interfaz de usuario.

- Datos aún no cargados
- Porcentaje de carga de datos
- Carga de datos completada
- Indexación completa
- Error en la carga de datos
- Error en la indexación de datos


### <a name="automated-schema-and-sit-creation"></a>Esquema automatizado y creación de SIT

En la nueva experiencia, puede proporcionar un archivo de datos de ejemplo que tenga los mismos valores de encabezado y suficientes filas (10-20) de datos representativos para el sistema. El sistema valida el formato y crea el esquema en función de los encabezados. A continuación, se identifican los campos principales del esquema y el sistema recomienda los SIT que mejor coinciden con él para asociarlos al campo principal. Si no desea cargar el archivo, puede escribir los mismos valores manualmente en la interfaz de usuario.

> [!IMPORTANT]
> Asegúrese de usar valores de datos de ejemplo que no sean confidenciales, pero que estén en el mismo formato que los datos confidenciales reales. El uso de datos no confidenciales es esencial porque el archivo de datos de ejemplo no se cifra ni aplica un hash cuando se carga como lo hace la tabla de información confidencial real. Los datos del archivo de datos de ejemplo no se conservan ni se puede acceder a ellos una vez creado el SIT de EDM.

El sistema genera las reglas de detección sit de EDM, una para cada campo principal. En función de la detección de los campos primarios, el sistema crea reglas de confianza de alto y medio utilizando todos los demás campos como evidencia corroborativa. Si lo desea, puede agregar reglas de confianza baja. 

### <a name="additional-guardrails-to-ensure-better-performance"></a>Barreras adicionales para garantizar un mejor rendimiento

<!--As the Azure-based EDM cloud service leverages a shared infrastructure, a misconfigured EDM SIT that triggers excessive EDM lookups could impact EDM performance for other customers if it wasn't controlled. This is prevented by throttling instances where EDM is misconfigured in a way that would cause excessive lookups.--> 

El sistema le avisa si encuentra un campo principal asignado a una SIT que detecta una amplia gama de valores, denominada *SIT definida de forma flexible*.  Esto puede hacer que el sistema realice búsquedas en un gran número de cadenas que no están relacionadas con el tipo de contenido que está buscando. La asignación entre estos tipos de SIT y campos primarios puede dar lugar a falsos negativos y reducir el rendimiento.

> [!NOTE]
> Como *sit definida de forma flexible*, como una personalizada que busca todos los números de identificación personal, tiene reglas de detección que permiten una mayor variabilidad en los elementos detectados. Una *SIT fuertemente definida*, como el número de seguro social de EE. UU., tiene reglas de detección que solo permiten detectar un conjunto estrecho y bien definido de elementos. 

El sistema también le advertirá si los valores del campo principal que seleccione se producen varias veces en un gran número de filas. Esto puede hacer que se devuelvan y procesen grandes cantidades de conjuntos de resultados, lo que podría provocar un tiempo de espera. Los tiempos de espera pueden dar lugar a detecciones perdidas y un rendimiento deficiente.


## <a name="choosing-the-right-edm-sit-creation-experience-for-you"></a>Elección de la experiencia de creación correcta de EDM SIT para usted

Puede alternar entre las experiencias nuevas y clásicas, pero se recomienda usar la nueva experiencia a menos que sus necesidades se divida en uno o varios de estos cuatro casos de uso. 

1. Lea esta sección.
1. Elija la experiencia que desea usar.
1. Seleccione el vínculo del [paso Siguiente](#next-steps) para la experiencia que desee.

### <a name="you-want-to-map-multiple-edm-sits-to-the-same-schema"></a>Desea asignar varias SITS de EDM al mismo esquema

En EDM, puede crear un máximo de 10 esquemas. Cada vez que se crea una SIT de EDM con la nueva experiencia, se crea un nuevo esquema. Esto da como resultado una asignación 1:1 entre el esquema EDM y EDM SIT. La nueva experiencia no admite la asignación de varios SIT al mismo esquema.

### <a name="you-need-to-create-or-manage-more-than-10-edm-sits"></a>Debe crear o administrar más de 10 SIT de EDM.

 Dado que la nueva experiencia no admite la asignación de varios SIT al mismo esquema, se limita a crear y administrar 10 SITS de EDM. En la experiencia clásica, puede asignar varios SIT de EDM al mismo esquema y, por lo tanto, tener más de 10 SIT de EDM. Con el nuevo flujo, recibirá un error si intenta crear un undécimo esquema EDM y no podrá ver más de 10 SIT de EDM.

### <a name="you-need-to-specify-the-name-of-your-edm-schema"></a>Debe especificar el nombre del esquema de EDM.

Si necesita especificar un nombre para los esquemas SIT de EDM, debe usar la experiencia clásica para crearlos y administrarlos. Dado que la nueva experiencia crea automáticamente el esquema, no tiene la oportunidad de asignar un nombre personalizado al esquema. El nombre generado automáticamente es una concatenación del nombre sit de EDM y el *esquema* de palabra. Por ejemplo, si el nombre sit de EDM es *PatientNumber*, el nombre del esquema sería *PatientNumberschema*.

### <a name="you-need-to-edit-edm-schemas-that-were-created-in-the-classic-experience"></a>Debe editar esquemas EDM creados en la experiencia clásica

Todos los esquemas creados con la experiencia clásica o cargados como un archivo XML mediante PowerShell no se pueden ver ni administrar en la nueva experiencia.

## <a name="next-steps"></a>Siguientes pasos

- [Creación de una nueva experiencia de tipo de información confidencial de coincidencia exacta de datos](sit-create-edm-sit-unified-ux-workflow.md)

o

- [Creación de una experiencia clásica de coincidencia exacta de datos con información confidencial](sit-create-edm-sit-classic-ux-workflow.md)

## <a name="see-also"></a>Vea también

- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md)
- [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
- [Creación de una nueva experiencia de flujo de trabajo de tipo de información confidencial que coincida con datos exactos](sit-create-edm-sit-unified-ux-workflow.md)
- [Creación de una experiencia clásica de flujo de trabajo de tipo de información confidencial de coincidencia exacta de datos](sit-create-edm-sit-classic-ux-workflow.md)