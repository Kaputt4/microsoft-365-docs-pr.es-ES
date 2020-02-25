---
title: Directiva de nomenclatura de grupos de Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Obtenga información sobre cómo crear una directiva de nomenclatura para grupos de Office 365.
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245488"
---
# <a name="office-365-groups-naming-policy"></a>Directiva de nomenclatura de grupos de Office 365

Una directiva de nomenclatura de grupos se usa para aplicar una estrategia de nomenclatura coherente para los grupos creados por los usuarios de la organización. Una directiva de nomenclatura puede ayudarle a usted y a sus usuarios a identificar la función del grupo, la pertenencia, la región geográfica o el usuario que creó el grupo. La Directiva de nomenclatura también puede ayudar a clasificar los grupos de la libreta de direcciones. Puede usar la Directiva para bloquear palabras específicas para que no se usen en nombres de grupo y alias.

La Directiva de nomenclatura se aplica a los grupos que se crean en todas las cargas de trabajo de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.). Se aplica al nombre del grupo y al alias del grupo. Se aplica cuando un usuario crea un grupo y cuando se modifica el nombre o el alias del grupo para un grupo existente.

> [!TIP]
> Una directiva de nomenclatura de grupo de Office 365 solo se aplica a los grupos de Office 365. No se aplica a los grupos de distribución creados en Exchange Online. Para crear una directiva de nomenclatura para los grupos de distribución, consulte [Create a Distribution Group naming Policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

La Directiva de nomenclatura de grupos consta de las siguientes características:

- **Directiva de nomenclatura de prefijo-sufijo**: puede usar prefijos o sufijos para definir la Convención de nomenclatura de grupos (\_por\_ejemplo:\_"GRP US My Group Engineering"). Los prefijos/sufijos pueden ser cadenas fijas o atributos de usuario, como [Departamento], que se sustituirán según el usuario que cree el grupo.

- **Palabras bloqueadas personalizadas**: puede cargar un conjunto de palabras bloqueadas específicas de su organización que podrían bloquearse en grupos creados por los usuarios. (Por ejemplo: "CEO, nóminas, h").

## <a name="licensing-requirements"></a>Requisitos de licencia

El uso de la Directiva de nomenclatura de Azure AD para Office 365 grupos requiere que posea, pero no necesariamente, una licencia de Azure Active Directory Premium P1 o la licencia de Azure AD Basic EDU para cada usuario único (incluidos los invitados) que pertenezca a uno o más grupos de Office 365.
Esto también es necesario para el administrador que crea la Directiva de nomenclatura de grupos.

## <a name="prefix-suffix-naming-policy"></a>Directiva de nomenclatura prefix-Suffix

Los prefijos y los sufijos pueden ser cadenas fijas o atributos de usuario.

### <a name="fixed-strings"></a>Cadenas fijas

Puede usar cadenas cortas que pueden ayudarle a diferenciar los grupos de la GAL y la navegación izquierda de las cargas de trabajo de grupo. Algunos de los sufijos comunes son palabras clave como "nombre\_del GRP",\#"nombre",\_"nombre".

### <a name="attributes"></a>Atributos

Puede usar atributos que ayuden a identificar quién ha creado el grupo como [Departamento] y dónde se ha creado desde like [país].

|||
|:-----|:-----|
|**Ejemplos**|Policy = "GRP [Nombredegrupo] [Departamento]"|
||Departamento del usuario = ingeniería|
||Nombre de grupo creado = "grupo de ingeniería de mi grupo"|

Atributos compatibles de Azure Active Directory (Azure AD) son [Departamento], [compañía], [Office], [StateOrProvince], [CountryOrRegion], [cargo]

- Los atributos de usuario no admitidos se consideran cadenas fijas. Por ejemplo "[CódigoPostal]"

- Los atributos de extensión y los atributos personalizados no son compatibles.

Se recomienda usar atributos que tengan valores rellenados para todos los usuarios de la organización y que no usen atributos que tengan valores más largos.

### <a name="things-to-look-out-for"></a>Aspectos que se deben tener en cuentan

- Durante la creación de la Directiva, la longitud total de las cadenas de prefijos y sufijos se limita a 53 caracteres.

- Los prefijos y los sufijos pueden contener caracteres especiales que se admiten en nombre de grupo y alias de grupo. Cuando los prefijos y los sufijos contienen caracteres especiales que no se permiten en el alias del grupo, se quitan y se aplican al alias del grupo. Por lo tanto, en este caso, los prefijos y los sufijos aplicados al nombre del grupo serían distintos de los que se aplican al alias del grupo.

- Si usa los grupos conectados de Yammer Office 365, evite usar los siguientes caracteres en su Directiva de nomenclatura: @ \#, \[, \], \<, y \>. Si estos caracteres están en la Directiva de nomenclatura, los usuarios normales de Yammer no podrán crear grupos.

## <a name="custom-blocked-words"></a>Palabras bloqueadas personalizadas

Puede escribir una lista separada por comas de palabras bloqueadas que se bloquearán en nombres de grupo y alias.

La comprobación de las palabras bloqueadas se realiza en el nombre de grupo escrito por el usuario. Por lo tanto, si el usuario introduce ' darnit\_' y ' prefix ' es la directiva\_de nomenclatura, se producirá un error ' prefix darnit '.

No se realizan búsquedas de subcadenas; concretamente, se necesita una coincidencia exacta entre el nombre del usuario especificado y las palabras bloqueadas personalizadas para desencadenar un error. La búsqueda de subcadenas no se realiza para que los usuarios puedan usar algunas de las palabras comunes, como ' clase ', incluso si ' ase ' es una palabra bloqueada.

**Aspectos que se deben tener en**cuentan:

- Las palabras bloqueadas no distinguen mayúsculas de minúsculas.

- Cuando un usuario escribe una palabra bloqueada, el cliente del grupo mostrará un mensaje de error con la palabra bloqueada.

- No hay restricciones de caracteres en las palabras bloqueadas que se usan.

- Hay un límite superior de 5000 palabras que se pueden establecer como palabras bloqueadas.

## <a name="admin-override"></a>Invalidación de administrador

Los administradores selectivos están exentos de estas directivas, en todas las cargas de trabajo y extremos de grupo, de modo que puedan crear grupos con estas palabras bloqueadas y con sus convenciones de nomenclatura deseadas. A continuación se muestra la lista de roles de administrador exentos de la Directiva de nomenclatura de grupos.

- Administrador global

- Soporte técnico de nivel 1 de asociado

- Soporte técnico de nivel 2 del asociado

- Administrador de cuentas de usuario

- Escritores de directorios

## <a name="how-to-set-up-the-naming-policy"></a>Cómo configurar la Directiva de nomenclatura

Para configurar una directiva de nomenclatura:

1. En [Azure Active Directory](https://aad.portal.azure.com), en **administrar**, haga clic en **grupos**.
2. En **configuración**, haga clic en **Directiva de nomenclatura**.
3. Seleccione la pestaña **Directiva de nomenclatura de grupos** .
4. En **Directiva actual**, elija si desea requerir un prefijo o un sufijo o ambos y active las casillas de verificación adecuadas.
5. Elija entre **atributo** y **cadena** para cada línea y, a continuación, especifique el atributo o la cadena.
6. Cuando haya agregado los prefijos y los sufijos que necesita, haga clic en **Guardar**.

![Captura de pantalla de la configuración de la Directiva de nomenclatura de grupos en Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a>Experiencias de directiva de nomenclatura en las aplicaciones de Office 365

Las aplicaciones de Office 365 se han actualizado para mostrar una vista previa del nombre del grupo de directivas de nomenclatura (con prefijos y sufijos) cuando el usuario escribe en el nombre de grupo y el alias. Cuando el usuario escribe palabras bloqueadas, verá un mensaje de error para que puedan quitar las palabras bloqueadas.

## <a name="outlook-on-the-web"></a>Outlook en la Web

Outlook en la web (anteriormente conocido como Outlook Web App o OWA) muestra el nombre representativo de la Directiva de nomenclatura cuando el usuario escribe un nombre de grupo o un alias de grupo. Cuando un usuario escribe una palabra bloqueada personalizada, se muestra un mensaje de error en la interfaz de usuario junto con la palabra bloqueada para que el usuario pueda quitarla. Las instantáneas de la experiencia de Outlook en la web se muestran a continuación.

![Vista en paralelo de la Directiva de nomenclatura de grupos en Office 365 grupos](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a>Escritorio de Outlook

Los grupos creados en el escritorio de Outlook son compatibles con la Directiva de nomenclatura. La aplicación de escritorio de Outlook todavía no muestra la vista previa de la Directiva de nomenclatura y no devuelve los errores de Word bloqueados personalizados cuando el usuario escribe el nombre del grupo. Sin embargo, la Directiva de nomenclatura se aplicará automáticamente al seleccionar crear/editar y los usuarios recibirán errores si hay palabras bloqueadas personalizadas en el nombre o el alias del grupo.

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft Teams muestra el nombre representativo de la Directiva de nomenclatura cuando el usuario escribe un nombre de equipo. Cuando un usuario escribe una palabra bloqueada personalizada, se muestra un mensaje de error junto con la palabra bloqueada para que el usuario pueda quitarla.

![Directiva de nomenclatura de grupos en Microsoft Teams ejemplo bloqueado](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a>SharePoint

SharePoint muestra el nombre de la Directiva de nomenclatura cuando el usuario escribe un nombre de sitio o una dirección de correo electrónico de grupo. Cuando un usuario escribe una palabra bloqueada personalizada, se muestra un mensaje de error junto con la palabra bloqueada para que el usuario pueda quitarla.

![Directiva de nomenclatura de Grupo: nombre bloqueado del sitio de SharePoint](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a>Microsoft Stream

Microsoft Stream muestra el nombre representativo de la Directiva de nomenclatura cuando el usuario escribe un nombre de grupo o alias de correo electrónico de grupo. Cuando un usuario escribe una palabra bloqueada personalizada, se muestra un mensaje de error con la palabra bloqueada para que el usuario pueda quitarla.

![Directiva de nomenclatura de grupo de ejemplo bloqueado para Microsoft Stream](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a>Aplicación de Outlook para iOS y Android

Los grupos creados en aplicaciones de Outlook son compatibles con la Directiva de nomenclatura. Outlook Mobile muestra la vista previa de la Directiva de nomenclatura al escribir el nombre del grupo. Cuando un usuario escribe una palabra bloqueada personalizada, se muestra un mensaje de error al crear el grupo, de modo que el usuario puede quitar la palabra bloqueada.

## <a name="planner"></a>Planner

Planner es compatible con la Directiva de nomenclatura. Planner muestra la vista previa de la Directiva de nomenclatura al especificar el nombre del plan. Cuando un usuario escribe una palabra bloqueada personalizada, se muestra un mensaje de error al crear el plan, por lo que el usuario puede quitar la palabra bloqueada.

![Directiva de nomenclatura de grupos: ejemplo de creación de un nuevo plan bloqueado](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a>Dynamics 365 para el compromiso del cliente

Dynamics 365 for Customer Engagement es compatible con la Directiva de nomenclatura. Dynamics 365 muestra el nombre representativo de la Directiva de nomenclatura cuando el usuario escribe un nombre de grupo o alias de correo electrónico de grupo. Cuando el usuario escribe una palabra bloqueada personalizada, se muestra un mensaje de error con la palabra bloqueada para que el usuario pueda quitarla.

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a>School Data Sync (SDS)

Los grupos creados mediante SDS cumplen con la Directiva de nomenclatura, pero la Directiva de nomenclatura no se aplica automáticamente. Los administradores de SDS deben anexar los prefijos y los sufijos a los nombres de clase para los que es necesario crear grupos y, a continuación, cargarlos en SDS. De lo contrario, se producía un error en la creación o modificación de grupos.

## <a name="outlook-customer-manager-ocm"></a>Administrador de clientes de Outlook (OCM)

El administrador de clientes de Outlook es compatible con la Directiva de nomenclatura. La Directiva de nomenclatura se aplica automáticamente al grupo creado en el administrador de clientes de Outlook. Si alguna de las palabras de "todo el equipo de ventas" se define como una palabra bloqueada personalizada, la creación del grupo en OCM se bloqueará. El usuario no podrá crear el grupo OCM y se le impedirá que use la aplicación OCM. "

## <a name="classroom-app"></a>Aplicación de aula

Los grupos creados en la aplicación de Classroom cumplen con la Directiva de nomenclatura, pero la Directiva de nomenclatura no se aplica automáticamente y la vista previa de la Directiva de nomenclatura no se muestra a los usuarios mientras se escribe el nombre de un grupo de aulas. Por lo tanto, los usuarios tendrían que escribir el nombre del grupo de aula decorado con prefijos y sufijos. De lo contrario, se producirá un error en el grupo de aulas crear o editar.

## <a name="power-bi"></a>Power BI

Los grupos creados en áreas de trabajo de Power BI cumplen con la Directiva de nomenclatura, pero la Directiva de nomenclatura no se aplica automáticamente. Además, la vista previa de la Directiva de nomenclatura no se muestra a los usuarios cuando especifican un nombre de área de trabajo de Power BI.

El nombre recomendado, con la Directiva de nomenclatura aplicada, se muestra en los detalles de error en crear o editar áreas de trabajo. Esto significa que los usuarios tienen que escribir el nombre del área de trabajo decorado con prefijos y sufijos. De lo contrario, se producirá un error al crear o editar el área de trabajo con errores.

## <a name="yammer"></a>Yammer

Cuando un usuario que ha iniciado sesión en Yammer con su cuenta de Azure Active Directory crea un grupo o edita un nombre de grupo, el nombre de grupo cumplirá con la Directiva de nomenclatura. Esto se aplica a los grupos conectados de Office 365 y a todos los demás grupos de Yammer.

Si se creó un grupo conectado de Office 365 antes de que la Directiva de nomenclatura esté en su lugar, el nombre del grupo no seguirá automáticamente las directivas de nomenclatura. Cuando un usuario edite el nombre de grupo, se le pedirá que agregue el prefijo y el sufijo.

Si la Directiva de nomenclatura incluye caracteres que no pueden estar en los nombres de grupo de Yammer, solo los administradores podrán crear un grupo conectado en Yammer.

## <a name="staffhub"></a>StaffHub

Los equipos de StaffHub no siguen la Directiva de nomenclatura, pero sí lo hace el grupo de Office 365 subyacente. El nombre del equipo de StaffHub no aplica los prefijos y los sufijos y no comprueba las palabras no admitidas personalizadas. Pero StaffHub aplica los prefijos y los sufijos y quita las palabras bloqueadas del grupo de Office 365 subyacente.

## <a name="exchange-powershell"></a>Exchange PowerShell

Los cmdlets de PowerShell de Exchange son compatibles con la Directiva de nomenclatura. Los usuarios recibirán los mensajes de error adecuados con prefijos y sufijos sugeridos, y con palabras bloqueadas personalizadas si la Convención de nomenclatura no se usa en los nombres de grupo y el alias de grupo.

## <a name="azure-active-directory-powershell-cmdlets"></a>Cmdlets de PowerShell de Azure Active Directory

Los cmdlets de PowerShell de Azure Active Directory son compatibles con la Directiva de nomenclatura. Los usuarios recibirán los mensajes de error adecuados con prefijos y sufijos sugeridos, y con palabras bloqueadas personalizadas si la Convención de nomenclatura no se usa en los nombres de grupo y el alias de grupo.

## <a name="exchange-admin-center"></a>Centro de administración de Exchange

El centro de administración de Exchange (EAC) es compatible con la Directiva de nomenclatura. Al crear o editar acciones, los usuarios recibirán los mensajes de error adecuados con los prefijos y sufijos sugeridos, así como con las palabras bloqueadas personalizadas si la Convención de nomenclatura no se usa en los nombres de grupo y el alias de grupo.

## <a name="microsoft-365-admin-center"></a>Centro de administración de Microsoft 365

El centro de administración de Microsoft 365 es compatible con la Directiva de nomenclatura. En las acciones de creación o edición, la Directiva de nomenclatura se aplicará automáticamente. Los usuarios recibirán los errores adecuados cuando introduzcan palabras bloqueadas personalizadas. El centro de administración de Microsoft 365 todavía no muestra la vista previa de la Directiva de nomenclatura y no devuelve los errores de Word bloqueados personalizados cuando el usuario escribe el nombre del grupo.

## <a name="azure-active-directory-portal"></a>Portal de Azure Active Directory

El portal de Azure Active Directory es compatible con la Directiva de nomenclatura. El portal de Azure Active Directory muestra la vista previa de la Directiva de nomenclatura al escribir el nombre del grupo. Cuando un usuario escribe una palabra bloqueada personalizada, se muestra un mensaje de error al crear el grupo, de modo que el usuario puede quitar la palabra bloqueada.

## <a name="more-articles-on-naming-policy"></a>Más artículos sobre la Directiva de nomenclatura

[Aplicar una directiva de nomenclatura para los grupos de Office 365 en Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)

[Cmdlets de Azure Active Directory para configurar configuraciones de grupo](https://go.microsoft.com/fwlink/?linkid=868341)
