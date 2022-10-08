---
title: Directiva de nomenclatura de grupos de Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: Obtenga información sobre cómo crear una directiva de nomenclatura para grupos de Microsoft 365.
ms.openlocfilehash: fd48c975a812eaf015dd5afe0e808103b7fa6d1e
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986826"
---
# <a name="microsoft-365-groups-naming-policy"></a>Directiva de nomenclatura de grupos de Microsoft 365

Puede usar una directiva de nomenclatura de grupos para aplicar una estrategia de nomenclatura coherente para los grupos creados por los usuarios de la organización. Una directiva de nomenclatura puede ayudarle a usted y a los usuarios a identificar la función del grupo, la pertenencia, la región geográfica o quién creó el grupo. La directiva de nomenclatura también puede ayudar a clasificar grupos en la libreta de direcciones. Puede usar la directiva para impedir que se usen palabras específicas en nombres de grupo y alias.

La directiva de nomenclatura se aplica a los grupos que se crean en todas las cargas de trabajo de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.). Se aplica tanto al nombre del grupo como al alias del grupo. También se aplica cuando un usuario crea un grupo y cuando se edita el nombre, alias, descripción o avatar del grupo para un grupo existente.

> [!TIP]
> Una directiva de nomenclatura de grupos de Microsoft 365 solo se aplica a los grupos de Microsoft 365. No se aplica a los grupos de distribución creados en Exchange Online. Para crear una directiva de nomenclatura para grupos de distribución, consulte [Creación de una directiva de nomenclatura de grupos de distribución](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

La directiva de nomenclatura de grupo consta de las siguientes características:

- **Directiva de nomenclatura de sufijos de prefijo**: puede usar prefijos o sufijos para definir la convención de nomenclatura de grupos (por ejemplo, "US\_My Group\_Engineering"). Los prefijos o sufijos pueden ser cadenas fijas o atributos de usuario como [Department] que se sustituirán en función del usuario que está creando el grupo.

- **Palabras bloqueadas personalizadas**: puede cargar un conjunto de palabras bloqueadas específicas de su organización que se bloquearían en grupos creados por los usuarios. (Por ejemplo: "CEO, Nómina, RR. HH.").

## <a name="licensing-requirements"></a>Requisitos de licencias

El uso de directivas de nomenclatura para grupos de Microsoft 365 requerirá que posea, pero no necesariamente que asigne, una licencia de Azure Active Directory Premium P1 o una licencia EDU básica de Azure AD por cada usuario único (incluyendo los invitados) que sea miembro de uno o más grupos de Microsoft 365.

Esto también es necesario para el administrador que crea la directiva de nomenclatura de grupos.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix directiva de nomenclatura

Los prefijos y sufijos pueden ser cadenas fijas o atributos de usuario.

### <a name="fixed-strings"></a>Cadenas fijas

Puede usar cadenas cortas que pueden ayudarle a diferenciar los grupos de la GAL y la navegación izquierda de las cargas de trabajo de grupo. Algunos de los sufijos de prefijos comunes son palabras clave como "Grp\_Name", "Name"\#, "\_Name"

### <a name="attributes"></a>Atributos

Puede usar atributos que pueden ayudar a identificar quién creó el grupo, como [Department] y dónde se creó, como [Country].

Ejemplos:

- Policy = "GRP [GroupName] [Department]"
- Departamento del usuario = Ingeniería
- Nombre del grupo creado = "GRP My Group Engineering"

Los atributos Azure Active Directory (Azure AD) compatibles son [Departmento], [Empresa], [Oficina], [ComunidadOProvincia], [PaísORegión] y [Título].

- Los atributos de usuario no admitidos se consideran cadenas fijas, por ejemplo [postalCode].

- No se admiten los atributos de extensión ni los atributos personalizados.

Se recomienda usar atributos que tengan valores rellenados para todos los usuarios de la organización y que no usen atributos con valores más largos.

### <a name="things-to-look-out-for"></a>Cosas que hay que tener en cuenta

- Durante la creación de la directiva, la longitud total de la cadena de prefijos y sufijos está restringida a 53 caracteres.

- Los prefijos y sufijos pueden contener caracteres especiales admitidos en el nombre del grupo y el alias de grupo. Cuando los prefijos y sufijos contienen caracteres especiales que no se permiten en el alias de grupo, solo se aplican al nombre del grupo. Por lo tanto, en este caso, los prefijos y sufijos aplicados al nombre del grupo serían diferentes de los aplicados al alias de grupo.

  > [!NOTE]
  > Se permite un punto (.) o un guion (-) en cualquier parte del nombre del grupo, excepto al principio o al final del nombre. Se permite un carácter de subrayado (_) en cualquier parte del nombre del grupo, incluido al principio o al final del nombre.

- Si usa Yammer Office 365 grupos conectados, evite usar los siguientes caracteres en la directiva de nomenclatura: @, \#, \[, \], \<, and \>. Si estos caracteres están en la directiva de nomenclatura, los usuarios de Yammer no podrán crear grupos.

> [!Tip]
> - Use cadenas cortas como sufijo.
> - Use atributos con valores.
> - No seas demasiado creativo, la longitud total del nombre tiene un máximo de 264 caracteres.
> - Cargue palabras bloqueadas específicas de la organización para restringir el uso.

## <a name="custom-blocked-words"></a>Palabras bloqueadas personalizadas

Puede escribir una lista separada por comas de palabras bloqueadas que se bloquearán en nombres de grupo y alias.

No se realizan búsquedas de subcadenas; específicamente, se requiere una coincidencia exacta entre el nombre especificado por el usuario y las palabras bloqueadas personalizadas para desencadenar un error.

**Cosas que debe tener en cuenta**:

- Las palabras bloqueadas no distinguen mayúsculas de minúsculas.

- Cuando un usuario escribe una palabra bloqueada, el cliente del grupo mostrará un mensaje de error con la palabra bloqueada.

- No hay restricciones de caracteres en las palabras bloqueadas usadas.

- Hay un límite de 5000 palabras que se pueden establecer como palabras bloqueadas.

## <a name="admin-override"></a>invalidación de Administración

Algunos administradores están exentos de estas directivas, en todas las cargas de trabajo y puntos de conexión de grupo, para que puedan crear grupos con estas palabras bloqueadas y con sus convenciones de nomenclatura deseadas. A continuación se muestra la lista de roles de administrador exentos de la directiva de nomenclatura de grupos.

- Administrador global

- Compatibilidad con el nivel 1 de asociado

- Soporte técnico de nivel 2 de asociado

- Administrador de cuentas de usuario

## <a name="how-to-set-up-the-naming-policy"></a>Configuración de la directiva de nomenclatura

Para configurar una directiva de nomenclatura:

1. En [Azure Active Directory](https://aad.portal.azure.com), en **Administrar**, haga clic en **Grupos**.
2. En **Configuración**, haga clic en **Directiva de nomenclatura**.
3. Elija la pestaña **Directiva de nomenclatura de grupos** .
4. En **Directiva actual**, elija si desea requerir un prefijo o sufijo o ambos y active las casillas adecuadas.
5. Elija entre **Atributo** y **Cadena** para cada línea y, a continuación, especifique el atributo o la cadena.
6. Cuando haya agregado los prefijos y sufijos que necesita, haga clic en **Guardar**.

![Captura de pantalla de la configuración de directivas de nomenclatura de grupos en Azure Active Directory.](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Cmdlets de Azure Active Directory para configurar configuraciones de grupo](/azure/active-directory/enterprise-users/groups-settings-cmdlets)