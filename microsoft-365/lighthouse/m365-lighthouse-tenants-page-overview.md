---
title: Información general de la página Inquilinos de Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: kywirpel
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Inquilinos.
ms.openlocfilehash: 59b1071aa698e6e44086223c2388bc4746a11347
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734503"
---
# <a name="overview-of-the-tenants-page-in-microsoft-365-lighthouse"></a>Información general de la página Inquilinos de Microsoft 365 Lighthouse

Microsoft 365 Lighthouse permite administrar cuentas de inquilino seleccionando **Inquilinos** en el panel de navegación izquierdo para abrir la página Inquilinos. La página Inquilinos contiene una lista de todos los inquilinos. Puede seleccionar un inquilino para ver información detallada, incluidos los detalles de contacto y el estado de la implementación.

La página Inquilinos también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar datos de inquilino a un archivo de valores separados por comas (.csv) de Excel.
- **Administrar etiquetas:** Seleccione esta opción para agregar, editar o eliminar una etiqueta.
- **Asignar etiquetas:** Seleccione esta opción para asignar una etiqueta a un inquilino.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente un inquilino específico en la lista.

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-page-overview.png" alt-text="Captura de pantalla de la página Inquilino.":::

## <a name="tenant-list"></a>Lista de inquilinos

La lista de inquilinos proporciona información sobre los distintos inquilinos con los que tiene un contrato, incluido su estado de incorporación de Lighthouse del inquilino. La lista de inquilinos también le permite etiquetar inquilinos para proporcionar filtros diferentes en Lighthouse y explorar en profundidad para obtener más información sobre un inquilino determinado y el estado de su plan de implementación.

Una vez que los inquilinos cumplan [los requisitos de incorporación de Lighthouse](m365-lighthouse-requirements.md), su estado se mostrará como **Activo** en la lista de inquilinos.

La lista de inquilinos le permite:

- Ordene automáticamente los inquilinos por activos, inactivos e inelegibles.
- Exporte la lista de inquilinos.
- Asignar y administrar etiquetas.
- Busque inquilinos por nombre.
- Filtre los inquilinos por estado, privilegios administrativos delegados (DAP) y etiquetas.

Para desactivar el inquilino o ver y administrar etiquetas, seleccione los tres puntos (más acciones) junto al nombre del inquilino. Puede ver inquilinos individuales seleccionando el nombre del inquilino o seleccionando una de las etiquetas asignadas al inquilino.

Para obtener información sobre cómo agregar inquilinos, consulte [Agregar y administrar varios inquilinos en la cuenta del Centro](/partner-center/multi-tenant-account) de partners.

## <a name="tenant-status"></a>Estado de espacio empresarial

En la tabla siguiente se muestran los distintos estados y su significado. Para obtener información sobre cómo solucionar problemas de estado de inquilino de cliente, consulte [Solución de problemas y mensajes de error en Microsoft 365 Lighthouse: Incorporación de inquilinos del cliente](m365-lighthouse-troubleshoot.md#customer-tenant-onboarding).<br><br>

| Estado                                   | Descripción                                                                                             |
|------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Activo                                   | Se han iniciado la incorporación de inquilinos y el flujo de datos.                                                           |
| Inactivo                                 | El inquilino se quitó a petición del MSP y ya no se administra en Lighthouse.           |
| En proceso                               | El inquilino se ha detectado pero no está totalmente incorporado.                                                              |
| Inelegible: DAP o GDAP no está configurado    | El asociado debe tener privilegios de administrador delegados (DAP) o delegados granulares (GDAP) configurados con el inquilino. |
| No válido: falta la licencia necesaria | El inquilino no tiene la licencia necesaria.                                                               |
| No válido: se superó el recuento de usuarios         | El inquilino tiene más usuarios de los permitidos.                                                                     |
| No válido: error de comprobación geográfica            | El partner y el cliente deben residir en la misma ubicación geográfica.                                       |

Una vez que inactiva un inquilino, no puede realizar ninguna acción en el inquilino hasta que se complete el proceso de inactivación. La inactivación puede tardar hasta 48 horas en completarse. Si decide reactivar un inquilino, los datos pueden tardar hasta 48 horas en volver a aparecer.

## <a name="tenant-tags"></a>Etiquetas de inquilino

Para ayudar a organizar los inquilinos y filtrar fácilmente las vistas existentes, puede crear y asignar etiquetas a los inquilinos. Para más información, consulte [Administración de la lista de inquilinos en Microsoft 365 Lighthouse](m365-lighthouse-manage-tenant-list.md).

> [!NOTE]
> Puede crear hasta 30 etiquetas en todo el inquilino.

## <a name="tenant-details-page"></a>Página de detalles del inquilino

Para ver información detallada del inquilino, seleccione un inquilino en la lista de inquilinos. La página de detalles del inquilino contiene información de contacto y estado del plan de implementación.

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-details-page.png" alt-text="Captura de pantalla de la página Detalles del inquilino.":::

### <a name="overview-tab"></a>‎Pestaña da Información general

En la pestaña Información general, puede ver información general del inquilino, información de contacto y uso del servicio Microsoft 365.

#### <a name="tenant-overview-section"></a>Sección de información general del inquilino

La sección Información general del inquilino proporciona información sobre el inquilino de su cuenta de Microsoft 365.<br><br>

| Información del inquilino    | Descripción|
|-----------------------|------------------|
| Headquarters    | Dónde se encuentra el inquilino.|
| Industria    |El sector de la organización.|
| Sitio web    |Sitio web de la organización. Puede editar este campo si no se proporciona ningún dato.|
| Dominio del cliente    |Dominio de la organización.|
| Usuarios totales    |Número de usuarios asignados en el inquilino. Puede seleccionar este número para abrir la página Usuarios de ese inquilino.|
| Total de dispositivos|Número de dispositivos inscritos en el inquilino. Puede seleccionar este número para abrir la página Dispositivos de ese inquilino.|

#### <a name="contacts-section"></a>Sección Contactos

La sección Contactos proporciona información para los contactos clave dentro de los inquilinos que administra, como:

- Nombre
- El título
- Phone
- Correo electrónico
- Notas

La columna **Notas** muestra información para el inquilino, como preferencias de interacción, ubicación, zona horaria y detalles sobre su rol dentro de la organización.

Para editar detalles, agregar notas o eliminar un contacto existente, seleccione el nombre del contacto de la lista. En el panel **Editar contacto** , edite o elimine el contacto. Para agregar otro contacto, seleccione **+Agregar contacto**.

#### <a name="microsoft-365-services-usage-section"></a>Sección de uso de servicios de Microsoft 365

Lighthouse proporciona información sobre el uso de servicios de Microsoft 365, incluido el número de usuarios de un inquilino con licencia y uso activo de cada servicio. La columna **Usuarios activos & dispositivos** indica el número de usuarios o dispositivos que han iniciado sesión en el servicio al menos una vez en los últimos 28 días. La columna **Cambio en la actividad** indica el cambio en los usuarios y dispositivos activos desde el mes pasado.

La sección **uso de servicios de Microsoft 365** contiene dos subses:

- **servicios habilitados para Microsoft 365 Lighthouse:** servicios que se pueden administrar en el portal de Lighthouse.
- **Servicios adicionales de Microsoft 365:** Servicios que se incluyen en el conjunto de aplicaciones de Microsoft 365 pero que no se pueden administrar en el portal de Microsoft 365 Lighthouse en este momento.

### <a name="deployment-plan-tab"></a>Pestaña Plan de implementación

La pestaña Planes de implementación proporciona el estado del plan de implementación de un inquilino. Los pasos de implementación de la lista se basan en la línea base aplicada al inquilino. Para ver los detalles del paso de implementación, seleccione un paso de implementación de la lista.

La pestaña Plan de implementación también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos del paso de implementación a un archivo de valores separados por comas (.csv) de Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos del paso de implementación más actuales.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente un paso de implementación específico en la lista.

## <a name="related-content"></a>Contenido relacionado

[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)\
[preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)\
[Administrar la lista de inquilinos en Microsoft 365 Lighthouse](m365-lighthouse-manage-tenant-list.md) (artículo)\
[Información general sobre el uso de líneas base de Microsoft 365 Lighthouse para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artículo)\
[Implementación Microsoft 365 Lighthouse líneas base](m365-lighthouse-deploy-baselines.md) (artículo)
