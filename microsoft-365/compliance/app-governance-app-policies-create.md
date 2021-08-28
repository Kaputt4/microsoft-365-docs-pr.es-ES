---
title: Crear directivas de aplicación
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Crear directivas de aplicación.
ms.openlocfilehash: 3b5f4bda7855f79e8a0e731cd6c26793ac9c6927
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58572268"
---
# <a name="create-app-policies"></a>Crear directivas de aplicación

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Además de un conjunto de funciones integradas para detectar comportamientos anómalos de las aplicaciones y generar alertas, las directivas de aplicaciones en el gobierno de aplicaciones de Microsoft son una forma de:

- Especifique las condiciones por las que el gobierno de la aplicación puede alertarle del comportamiento de la aplicación para su corrección automática o manual.
- Implemente las directivas de cumplimiento de aplicaciones para su organización.

Puede crear directivas de aplicación a partir de plantillas proporcionadas que pueden ser personalizadas, o puede crear su propia directiva de aplicación personalizada.

Para crear una nueva directiva de aplicaciones, vaya al **Centro de cumplimiento de Microsoft 365 > Gobierno de aplicaciones > Página de descripción general > Directivas**:

- Para crear una nueva directiva de aplicaciones con plantillas diseñadas para el uso de aplicaciones, seleccione **Crear directiva** en **Crear una política de uso de aplicaciones**.
- Para crear una nueva directiva de aplicaciones con plantillas diseñadas para permisos de aplicaciones, seleccione **Crear directiva** en **Crear una directiva de permisos**.
- Para crear una nueva directiva de aplicación para la certificación de aplicaciones o para una directiva personalizada, seleccione **Crear nuevo**.

## <a name="app-policy-templates"></a>Plantillas de directiva de aplicaciones

Para crear una nueva directiva de aplicación basada en una plantilla de directiva de aplicación, en la **página Elegir plantilla de directiva de aplicación**, seleccione una categoría de plantilla de aplicación, seleccione el nombre de la plantilla y, a continuación, seleccione **Siguiente**.

El gobierno de las aplicaciones tiene tres categorías de plantillas de directivas de aplicaciones.

### <a name="app-users-and-data-access"></a>Usuarios de la aplicación y acceso a los datos

El gobierno de las aplicaciones incluye estas plantillas para generar alertas sobre el uso de las mismas.

<br>

****

|Nombre de la plantilla|Descripción|
|---|---|
|Nueva aplicación con un alto volumen de acceso a datos|Destaca las aplicaciones registradas recientemente con un alto volumen de acceso a los datos para asegurarse de que esos patrones de datos son los esperados. <p> De forma predeterminada, esta directiva marcará todas las aplicaciones que se han registrado en los últimos 7 días y que han tenido más de 1 GB de acceso a datos durante ese período. Esta directiva se puede personalizar con más condiciones y acciones.|
|||

### <a name="app-permissions"></a>Permisos de aplicación

El gobierno de las aplicaciones incluye estas plantillas para generar alertas sobre los permisos de las aplicaciones.

<br>

****

|Nombre de la plantilla|Descripción|
|---|---|
|Aplicaciones con exceso de privilegios|Destaca cualquier aplicación con más permisos concedidos de los que están siendo utilizados por esas aplicaciones para identificar oportunidades de reducción potencial de permisos. <p> Por defecto, esta directiva marcará todas las aplicaciones que estén marcadas como con exceso de privilegios si no se utilizan durante 90 días. Este filtro de periodo de tiempo se puede personalizar con más condiciones y acciones.|
|Nueva aplicación con permisos de alto privilegio|Destaca todas las nuevas aplicaciones con permisos de alto privilegio para identificar las posibles aplicaciones de alto impacto que pueden necesitar una mayor investigación. <p> De forma predeterminada, esta directiva marcará todas las aplicaciones registradas en los últimos 7 días que tengan permisos de alto alcance.|
|||

### <a name="m365-certification"></a>Certificación M365

El gobierno de las aplicaciones incluye estas plantillas para generar alertas para la certificación de M365.

<br>

****

|Nombre de la plantilla|Descripción|
|---|---|
|Nueva aplicación no certificada|Destaca las nuevas aplicaciones que no han pasado por el proceso de certificación de M365 para garantizar que son esperadas en el espacio empresarial. <p> De forma predeterminada, esta directiva marcará todas las aplicaciones que se hayan registrado en los últimos 7 días y que no estén certificadas.|
|||

## <a name="custom-app-policies"></a>Directivas de aplicación personalizadas

Utilice una directiva de aplicación personalizada cuando necesite hacer algo que no esté hecho por una de las plantillas incorporadas.

Para crear una nueva directiva de aplicación personalizada, primero seleccione **Crear nueva** en la página de **Directivas**. En la **página Elegir plantilla de directiva de aplicación**, seleccione la categoría **Personalizada**, la plantilla de **Directiva personalizada**, y luego, seleccione **Siguiente**.

En la página **Nombre y descripción**, configure lo siguiente:

- Nombre de directiva

- Descripción de directiva

- Seleccione la gravedad de la directiva, que establece la gravedad de las alertas generadas por esta directiva.

  - Alto
  - Medio
  - Bajo

En la página **Elegir la configuración y las condiciones de la directiva**, para **Elegir las aplicaciones a las que se aplica esta directiva**, seleccione:

- Todas las aplicaciones
- Elija aplicaciones específicas

  Un panel permite seleccionar una o varias aplicaciones.
  Seleccione **Agregar**.

Seleccione **Siguiente**.

En la página **Elegir configuración y condiciones de la directiva**, seleccione **Establecer nuevas condiciones para la directiva**, y luego seleccione **Siguiente**.

El panel **Crear regla** permite seleccionar las condiciones para una nueva regla. Seleccione **Agregar condición** y seleccione de la lista de condiciones, y luego especifique el valor de la condición. Puede agregar varias condiciones.

Estas son las condiciones disponibles para una directiva de aplicación personalizada.

<br>

****

|Condición|Valores de condición aceptados|Más información|
|---|---|---|
|Edad de registro de la aplicación|En los últimos X días||
|Certificación de aplicación|Cumplimiento básico, cumplimiento del MCAS o N/A|[Certificación Microsoft 365](/microsoft-365-app-certification/docs/enterprise-app-certification-guide)|
|Verificación del editor|Sí o no|[Verificación del editor](/azure/active-directory/develop/publisher-verification-overview)|
|Permiso de aplicación|Seleccione uno o más permisos de API de la lista|[Referencia de permisos de Microsoft Graph](/graph/permissions-reference)|
|Permiso delegado|Seleccione uno o más permisos de API de la lista|[Referencia de permisos de Microsoft Graph](/graph/permissions-reference)|
|Privilegio alto|Sí o no|Se trata de una designación interna basada en la misma lógica utilizada por el MCAS.|
|Aplicación sobre privilegiada|Sí o no|Aplicaciones con más permisos concedidos de los que están siendo utilizados por esas aplicaciones.|
|Acceso a los datos de la aplicación|Más de X GB de acceso a datos por hora||
|Tendencia de acceso a los datos de la aplicación|X% de aumento en el uso de datos en los últimos 7 días||
|Acceso a la API de la aplicación|Más de X llamadas a la API por hora||
|Tendencia de acceso a la API de la aplicación|X% de aumento en las llamadas a la API en los últimos 7 días||
|Consentimiento del usuario|(mayor o menor que) X usuarios con consentimiento||
|El usuario con prioridad ha dado su consentimiento|Sí o no|Un usuario con una [cuenta prioritaria](/microsoft-365/admin/setup/priority-accounts).|
|Consentimiento de la aplicación concedido por|Seleccionar usuario(s) de la lista||
|Rol del usuario que da su consentimiento|Seleccione uno o más: Administrador de equipos, Lector de directorios, Lector de seguridad, Administrador de cumplimiento, Administrador de seguridad, Administrador de Helpdesk, Administrador de SharePoint, Administrador de Exchange, Lector global, Administrador global, Administrador de datos de cumplimiento, Administrador de usuarios, Administrador de soporte técnico|La selección múltiple está permitida. <p> Cualquier rol de Azure AD con miembro asignado debe estar disponible en esta lista.|
|Carga de trabajo a la que se accede|OneDrive y/o SharePoint y/o Exchange|La selección múltiple está permitida.|
|Tasa de errores|La tasa de error es superior al X% en los últimos 7 días, donde X es un valor definido por el administrador||
||||

Se deben cumplir todas las condiciones especificadas para que esta directiva de aplicación genere una alerta.

Cuando haya terminado de especificar las condiciones, seleccione **Guardar**, y luego seleccione **Siguiente**.

En la página **Definir acciones de directiva**, seleccione **Desactivar aplicación** si desea que el gobierno de la aplicación desactive la aplicación cuando se genere una alerta basada en esta directiva, y luego, seleccione **Siguiente**.

En la página **Definir el estado de la directiva**, seleccione una de estas opciones:

- **Modo de auditoría**: las directivas son evaluadas pero las acciones configuradas no ocurrirán. Las directivas en modo de auditoría aparecen con el estado de **Auditoría** en la lista de directivas.
- **Activo**: las directivas son evaluadas y las acciones configuradas se llevarán a cabo.
- **Inactivo**: las directivas no son evaluadas y las acciones configuradas no tendrán lugar.

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a>Pruebe y supervise su nueva directiva de aplicaciones

Ahora que su directiva de aplicación está creada, debe supervisarla en la página de **Directivas** para asegurarse de que está registrando un número esperado de alertas activas y alertas totales durante las pruebas.

![La página de resumen de las directivas de MAPG en el Centro de cumplimiento de Microsoft 365 con una directiva resaltada.](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

Si el número de alertas es un valor inesperadamente bajo, edite la configuración de la directiva de la aplicación para asegurarse de que la ha configurado correctamente antes de establecer su estado.

Este es un ejemplo de un proceso para crear una nueva directiva, probarla y luego activarla:

1. Cree la nueva directiva con la gravedad, las aplicaciones, las condiciones y las acciones establecidas en el **Modo de auditoría**.
2. Compruebe el comportamiento esperado, como las alertas generadas.
3. Si el comportamiento no es el esperado, edite las aplicaciones de la directiva, las condiciones y la configuración de la acción según sea necesario y vuelva al paso 2.
4. Si el comportamiento es el esperado, edite la directiva y cambie su estado a **Activo**.

![El flujo de trabajo para crear una directiva de aplicación.](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a>Paso siguiente

[Administre las directivas de sus aplicaciones.](app-governance-app-policies-manage.md)
