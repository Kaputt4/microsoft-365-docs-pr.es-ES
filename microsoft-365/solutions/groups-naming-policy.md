---
title: Microsoft 365 de nomenclatura de grupos
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: Obtenga información sobre cómo crear una directiva de nomenclatura para Microsoft 365 grupos.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538176"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 de nomenclatura de grupos

Puede usar una directiva de nomenclatura de grupo para aplicar una estrategia de nomenclatura coherente para los grupos creados por usuarios de la organización. Una directiva de nomenclatura puede ayudarle a usted y a los usuarios a identificar la función del grupo, la pertenencia, la región geográfica o quién creó el grupo. La directiva de nomenclatura también puede ayudar a clasificar grupos en la libreta de direcciones. Puede usar la directiva para impedir que se usen palabras específicas en nombres de grupo y alias.

La directiva de nomenclatura se aplica a los grupos que se crean en todas las cargas de trabajo de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.). Se aplica tanto al nombre del grupo como al alias de grupo. También se aplica cuando un usuario crea un grupo y cuando se edita el nombre, el alias, la descripción o el avatar del grupo para un grupo existente.

> [!TIP]
> Una Microsoft 365 de nomenclatura de grupos solo se aplica a Microsoft 365 grupos. No se aplica a los grupos de distribución creados en Exchange Online. Para crear una directiva de nomenclatura para grupos de distribución, vea [Create a distribution group naming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

La directiva de nomenclatura de grupo consta de las siguientes características:

- **Directiva de nomenclatura prefix-suffix:** puede usar prefijos o sufijos para definir la convención de nomenclatura de grupos (por ejemplo: "Ingeniería de mi grupo de ESTADOS \_ \_ UNIDOS"). Los prefijos o sufijos pueden ser cadenas fijas o atributos de usuario como [Department] que se sustituirán en función del usuario que está creando el grupo.

- **Palabras bloqueadas** personalizadas: puede cargar un conjunto de palabras bloqueadas específicas de su organización que se bloquearían en grupos creados por usuarios. (Por ejemplo: "CEO, Payroll, HR").

## <a name="licensing-requirements"></a>Requisitos de licencias

El uso de la directiva de nomenclatura de Azure AD para grupos de Microsoft 365 requiere que posea una licencia de Azure Active Directory Premium P1 o una licencia EDU básica de Azure AD para cada usuario único (incluidos los invitados) que sea miembro de uno o más grupos de Microsoft 365.

Esto también es necesario para el administrador que crea la directiva de nomenclatura de grupos.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix de nomenclatura

Los prefijos y sufijos pueden ser cadenas fijas o atributos de usuario.

### <a name="fixed-strings"></a>Cadenas fijas

Puede usar cadenas cortas que pueden ayudarle a diferenciar los grupos de la GAL y la navegación izquierda de las cargas de trabajo de grupo. Algunos de los sufijos de prefijo comunes son palabras clave como 'Grp \_ Name', ' \# Name', ' \_ Name'

### <a name="attributes"></a>Atributos

Puede usar atributos que pueden ayudar a identificar quién creó el grupo como [Departamento] y dónde se creó desde [País].

Ejemplos:

- Policy = "GRP [GroupName] [Department]"
- Departamento del usuario = Ingeniería
- Nombre de grupo creado = "GRP Mi ingeniería de grupo"

Los atributos Azure Active Directory (Azure AD) son [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] y [Title].

- Los atributos de usuario no admitidos se consideran cadenas fijas, por ejemplo [postalCode].

- No se admiten atributos de extensión ni atributos personalizados.

Se recomienda usar atributos que tengan valores rellenados para todos los usuarios de la organización y que no usen atributos con valores más largos.

### <a name="things-to-look-out-for"></a>Aspectos a tener en cuenta

- Durante la creación de directivas, la longitud total de la cadena de prefijos y sufijos está restringida a 53 caracteres.

- Los prefijos y sufijos pueden contener caracteres especiales admitidos en el nombre del grupo y el alias de grupo. Cuando los prefijos y sufijos contienen caracteres especiales que no están permitidos en el alias de grupo, solo se aplican al nombre del grupo. Por lo tanto, en este caso, los prefijos y sufijos aplicados al nombre de grupo serían diferentes de los que se aplican al alias de grupo.

  > [!NOTE]
  > Se permite un punto (.) o un guión (-) en cualquier lugar del nombre del grupo, excepto al principio o al final del nombre. Se permite un carácter de subrayado (_) en cualquier lugar del nombre del grupo, incluso al principio o al final del nombre.

- Si usa grupos Yammer Office 365 conectados, evite usar los siguientes caracteres en la directiva de nomenclatura: @, \# , \[ , , \] \<, and \> . Si estos caracteres están en la directiva de nomenclatura, los usuarios Yammer no podrán crear grupos.

> [!Tip]
> - Use cadenas cortas como sufijo.
> - Use atributos con valores.
> - No seas demasiado creativo, la longitud total del nombre tiene un máximo de 264 caracteres.
> - Upload palabras bloqueadas específicas de la organización para restringir el uso.

## <a name="custom-blocked-words"></a>Palabras bloqueadas personalizadas

Puede escribir una lista separada por comas de palabras bloqueadas que se bloquearán en nombres de grupo y alias.

No se llevan a cabo búsquedas de subcadena; Específicamente, se requiere una coincidencia exacta entre el nombre especificado por el usuario y las palabras bloqueadas personalizadas para desencadenar un error.

**Aspectos que debe tener en cuenta:**

- Las palabras bloqueadas no tienen mayúsculas de minúsculas.

- Cuando un usuario escribe una palabra bloqueada, el cliente de grupo mostrará un mensaje de error con la palabra bloqueada.

- No hay restricciones de caracteres en las palabras bloqueadas usadas.

- Hay un límite de 5000 palabras que se pueden establecer como palabras bloqueadas.

## <a name="admin-override"></a>Reemplazo de administrador

Algunos administradores están exentos de estas directivas, en todas las cargas de trabajo de grupo y puntos de conexión, para que puedan crear grupos con estas palabras bloqueadas y con sus convenciones de nomenclatura deseadas. A continuación se muestra la lista de roles de administrador exentos de la directiva de nomenclatura de grupo.

- Administrador global

- Soporte técnico de nivel 1 de partner

- Soporte técnico de nivel 2 de partner

- Administrador de cuentas de usuario

## <a name="how-to-set-up-the-naming-policy"></a>Cómo configurar la directiva de nomenclatura

Para configurar una directiva de nomenclatura:

1. En [Azure Active Directory](https://aad.portal.azure.com), en **Administrar**, haga clic en **Grupos**.
2. En **Configuración**, haga clic **en Directiva de nomenclatura**.
3. Elija la **pestaña Directiva de nomenclatura de** grupo.
4. En **Directiva actual,** elija si desea requerir un prefijo o sufijo o ambos, y active las casillas correspondientes.
5. Elija entre **Atributo** y **Cadena** para cada línea y, a continuación, especifique el atributo o cadena.
6. Cuando haya agregado los prefijos y sufijos que necesita, haga clic en **Guardar**.

![Captura de pantalla de la configuración de directiva de nomenclatura de grupos en Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Cmdlets de Azure Active Directory para configurar configuraciones de grupo](/azure/active-directory/enterprise-users/groups-settings-cmdlets)