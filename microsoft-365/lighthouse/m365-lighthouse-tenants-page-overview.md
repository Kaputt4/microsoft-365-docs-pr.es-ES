---
title: Información general de la página Inquilinos de Microsoft 365 Lighthouse
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
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Inquilinos.
ms.openlocfilehash: 0f25f8bb02c6957598b2b328bc7832c429ca1e7a
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128382"
---
# <a name="overview-of-the-tenants-page-in-microsoft-365-lighthouse"></a>Información general de la página Inquilinos de Microsoft 365 Lighthouse

Microsoft 365 Lighthouse permite administrar cuentas de inquilino seleccionando **Inquilinos** en el panel de navegación izquierdo para abrir la página Inquilinos. La página Inquilinos contiene una lista de todos los inquilinos. Puede seleccionar un inquilino para ver información detallada, incluidos los detalles de contacto y el estado de la implementación.

La página Inquilinos también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar datos de inquilino a un archivo de valores separados por comas (.csv) Excel.
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

### <a name="overview-tab"></a>Pestaña Información general

En la pestaña Información general, puede ver información general del inquilino, información de contacto y Microsoft 365 uso del servicio.

#### <a name="tenant-overview-card"></a>Tarjeta de información general del inquilino

La tarjeta Información general del inquilino proporciona información sobre el inquilino de su cuenta de Microsoft 365.<br><br>

| Información del inquilino    | Descripción|
|-----------------------|------------------|
| Headquarters    | Dónde se encuentra el inquilino.|
| Industria    |El sector de la organización.|
| Sitio web    |Sitio web de la organización. Puede editar este campo si no se proporciona ningún dato.|
| Dominio del cliente    |Dominio de la organización.|
| Usuarios totales    |Número de usuarios asignados en el inquilino. Puede seleccionar este número para abrir la página Usuarios de ese inquilino.|
| Total de dispositivos|Número de dispositivos inscritos en el inquilino. Puede seleccionar este número para abrir la página Dispositivos de ese inquilino.|

#### <a name="contacts-card"></a>Tarjeta de contactos

La tarjeta Contactos le permite especificar información para los contactos clave dentro de los inquilinos que administra, como:

- Nombre
- El título
- Phone
- Correo electrónico
- Notas

La sección Notas es un campo de texto que puede usar para registrar información clave del inquilino, como preferencias de interacción, ubicación, zona horaria y detalles sobre su rol dentro de la organización.

Para editar los detalles o eliminar un contacto existente, seleccione el nombre del contacto en la lista. En el panel **Editar contacto** , edite o elimine el contacto. Para agregar otro contacto, seleccione **+Agregar contacto**.

#### <a name="microsoft-365-usage-card"></a>Microsoft 365 tarjeta de uso

Lighthouse proporciona información sobre el uso de Microsoft 365 servicios, incluido el número de usuarios de un inquilino con licencia y uso activo de cada servicio. Activo indica el número de usuarios o dispositivos que han iniciado sesión en el servicio al menos una vez en los últimos 28 días. El cambio indica el cambio en los usuarios y dispositivos activos desde el mes pasado.

La tarjeta de uso de Microsoft 365 contiene dos secciones:

- **servicios habilitados para Microsoft 365 Lighthouse:** servicios que se pueden administrar en el portal de Lighthouse.
- **Servicios de Microsoft 365 adicionales:** servicios que se incluyen en el conjunto de Microsoft 365 pero que no se pueden administrar en el portal de Microsoft 365 Lighthouse en este momento.

### <a name="deployment-plans-tab"></a>Pestaña Planes de implementación

La pestaña Planes de implementación proporciona el estado del plan de implementación de un inquilino. Los pasos de implementación de la lista se basan en la línea base aplicada al inquilino. Para ver los detalles del paso de implementación, seleccione un paso de implementación de la lista.

La pestaña Planes de implementación también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos del paso de implementación a un archivo de valores separados por comas (.csv) Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos del paso de implementación más actuales.
- **Búsqueda:** Escriba palabras clave para localizar rápidamente un paso de implementación específico en la lista.

## <a name="related-content"></a>Contenido relacionado

[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)\
[preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)\
[Administrar la lista de inquilinos en Microsoft 365 Lighthouse](m365-lighthouse-manage-tenant-list.md) (artículo)\
[Información general sobre el uso de líneas base de Microsoft 365 Lighthouse para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artículo)\
[Implementación Microsoft 365 Lighthouse líneas base](m365-lighthouse-deploy-baselines.md) (artículo)
