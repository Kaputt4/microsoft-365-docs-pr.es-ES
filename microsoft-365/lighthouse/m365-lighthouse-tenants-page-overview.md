---
title: Microsoft 365 Lighthouse de la página Inquilinos
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Inquilinos.
ms.openlocfilehash: 23f151664455c35bb2fcc191d774ead00927e830
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329997"
---
# <a name="microsoft-365-lighthouse-tenants-page-overview"></a>Microsoft 365 Lighthouse de la página Inquilinos

Microsoft 365 Lighthouse permite administrar cuentas de inquilino seleccionando **Inquilinos** en el panel de navegación izquierdo para abrir la página Inquilinos. La página Inquilinos contiene una lista de todos los inquilinos. Puede seleccionar un inquilino para ver información detallada, incluidos los detalles de contacto y el estado de implementación.

La página Inquilinos también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar datos de espacio empresarial a Excel de valores separados por comas (.csv).
- **Administrar etiquetas:** Seleccione para agregar, editar o eliminar una etiqueta.
- **Asignar etiquetas:** Seleccione esta opción para asignar una etiqueta a un inquilino.
- **Buscar:** Escriba palabras clave para localizar rápidamente un espacio empresarial específico en la lista.

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-page-overview.png" alt-text="Captura de pantalla de la página Inquilino.":::

## <a name="tenant-list"></a>Lista de inquilinos

La lista de inquilinos proporciona información sobre los diferentes inquilinos con los que tiene un contrato, incluido su estado de incorporación de Faro de inquilino. La lista de inquilinos también le permite etiquetar los inquilinos para proporcionar distintos filtros a lo largo de Lighthouse y profundizar para obtener más información sobre un inquilino determinado y el estado de su plan de implementación.

Después de que los inquilinos cumplan los [requisitos de incorporación de Lighthouse](m365-lighthouse-requirements.md), su estado se mostrará **como Activo** en la lista de inquilinos.

La lista de inquilinos le permite:

- Ordene automáticamente los inquilinos por activos, inactivos e inelegibles.
- Exporte la lista de inquilinos.
- Asignar y administrar etiquetas.
- Buscar inquilinos por nombre.
- Filtre los inquilinos por estado, privilegios administrativos delegados (DAP) y etiquetas.

Para desactivar el inquilino o ver y administrar etiquetas, seleccione los tres puntos (más acciones) junto al nombre del inquilino. Puede ver inquilinos individuales seleccionando el nombre del inquilino o seleccionando una de las etiquetas asignadas al inquilino.

## <a name="tenant-status"></a>Estado de espacio empresarial

En la tabla siguiente se muestran los distintos estados y su significado.<br><br>

| Estado                                   | Descripción                                                                                             |
|------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Activa                                   | Se han iniciado la incorporación de inquilinos y el flujo de datos.                                                           |
| Inactivo                                 | El inquilino se desabordó a petición del MSP y ya no se está administrando en Lighthouse.           |
| En proceso                               | Inquilino detectado pero no totalmente incorporado.                                                              |
| Ineligible: DAP o GDAP no están configurados    | El partner debe tener privilegios de administrador delegados (DAP) o granulares delegados (GDAP) configurados con el inquilino. |
| Ineligible: falta la licencia necesaria | El inquilino no tiene la licencia necesaria.                                                               |
| Ineligible: se ha superado el número de usuarios         | El inquilino tiene más usuarios de los permitidos.                                                                     |
| Ineligible: error en la comprobación geográfica            | El partner y el cliente deben residir en la misma ubicación geográfica.                                       |

Una vez inactivado un inquilino, no podrá realizar acciones en el inquilino hasta que se complete el proceso de inactivación. La inactivación puede tardar hasta 48 horas en completarse. Si decide reactivar un inquilino, los datos pueden tardar hasta 48 horas en volver a aparecer.

## <a name="tenant-tags"></a>Etiquetas de inquilino

Para ayudar a organizar los inquilinos y filtrar fácilmente las vistas existentes, puede crear y asignar etiquetas a los inquilinos. Para obtener más información, consulte [Administrar la lista de inquilinos](m365-lighthouse-manage-tenant-list.md).

> [!NOTE]
> Puede crear hasta 30 etiquetas en todos los inquilinos.

## <a name="tenant-details-page"></a>Página de detalles del inquilino

Para ver información detallada del inquilino, seleccione un espacio empresarial de la lista de inquilinos. La página de detalles del espacio empresarial contiene información de contacto y el estado del plan de implementación.

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-details-page.png" alt-text="Captura de pantalla de la página detalles del inquilino.":::

### <a name="overview-tab"></a>Ficha Información general

En la pestaña Información general, puede ver información general sobre el espacio empresarial, información de contacto y Microsoft 365 de servicio.

#### <a name="tenant-overview-card"></a>Tarjeta de información general del inquilino

La tarjeta de información general del inquilino proporciona información sobre el espacio empresarial desde Microsoft 365 cuenta.<br><br>

| Información del inquilino    | Descripción|
|-----------------------|------------------|
| Headquarters    | Donde se encuentra el inquilino.|
| Industria    |La industria de la organización.|
| Sitio web    |Sitio web de la organización. Puede editar este campo si no se proporcionan datos.|
| Dominio de cliente    |Dominio de la organización.|
| Usuarios totales    |Número de usuarios asignados en el espacio empresarial. Puede seleccionar este número para abrir la página Usuarios de ese espacio empresarial.|
| Dispositivos totales|El número de dispositivos inscritos en el espacio empresarial. Puede seleccionar este número para abrir la página Dispositivos para ese espacio empresarial.|

#### <a name="contacts-card"></a>Tarjeta de contactos

La tarjeta Contactos te permite escribir información para los contactos clave dentro de los inquilinos que administras, como:

- Nombre
- El título
- Phone
- Correo electrónico
- Notas

La sección Notas es un campo de texto que puede usar para registrar información clave para el inquilino, como las preferencias de participación, la ubicación, la zona horaria y los detalles sobre su rol dentro de la organización.

Para editar detalles o eliminar un contacto existente, seleccione el nombre del contacto de la lista. En el **panel Editar contacto** , edite o elimine el contacto. Para agregar otro contacto, seleccione **+Agregar contacto**.

#### <a name="microsoft-365-usage-card"></a>Microsoft 365 de uso

Lighthouse proporciona información sobre el Microsoft 365 de servicios, incluido el número de usuarios dentro de un espacio empresarial que tienen licencia y usan activamente cada servicio. Active indica el número de usuarios o dispositivos que han iniciado sesión en el servicio al menos una vez en los últimos 28 días. El cambio indica el cambio en los usuarios y dispositivos activos desde el mes pasado.

La Microsoft 365 de uso contiene dos secciones:

- **Microsoft 365 Lighthouse habilitados para aplicaciones:** servicios que se pueden administrar en el portal de Faro.
- **Servicios Microsoft 365 adicionales:** servicios que se incluyen en el conjunto de Microsoft 365 pero que no se pueden administrar en el portal de Microsoft 365 Lighthouse en este momento.

### <a name="deployment-plans-tab"></a>Pestaña Planes de implementación

La pestaña Planes de implementación proporciona el estado del plan de implementación de un inquilino. Los pasos de implementación de la lista se basan en la línea base aplicada al inquilino. Para ver los detalles del paso de implementación, seleccione un paso de implementación de la lista.

La pestaña Planes de implementación también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos del paso de implementación Excel un archivo de valores separados por comas (.csv).
- **Actualizar:** Seleccione esta opción para recuperar los datos del paso de implementación más actuales.
- **Buscar:** Escriba palabras clave para localizar rápidamente un paso de implementación específico en la lista.

## <a name="related-content"></a>Contenido relacionado

[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)\
[Administrar la lista de inquilinos](m365-lighthouse-manage-tenant-list.md) (artículo)\
[Introducción al uso de líneas base para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artículo)\
[Implementar Microsoft 365 Lighthouse base de referencia](m365-lighthouse-deploy-baselines.md) (artículo)
