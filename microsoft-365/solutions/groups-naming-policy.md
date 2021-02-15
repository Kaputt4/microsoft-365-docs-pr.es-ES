---
title: Directiva de nomenclatura de grupos de Microsoft 365
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
description: Obtenga información sobre cómo crear una directiva de nomenclatura para grupos de Microsoft 365.
ms.openlocfilehash: acf660375508760bd2e9874a07454709849929b0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759829"
---
# <a name="microsoft-365-groups-naming-policy"></a>Directiva de nomenclatura de grupos de Microsoft 365

Puede usar una directiva de nomenclatura de grupos para aplicar una estrategia de nomenclatura coherente para los grupos creados por los usuarios de la organización. Una directiva de nomenclatura puede ayudarle a usted y a los usuarios a identificar la función del grupo, la pertenencia, la región geográfica o quién creó el grupo. La directiva de nomenclatura también puede ayudar a clasificar grupos en la libreta de direcciones. Puede usar la directiva para bloquear el uso de palabras específicas en nombres de grupo y alias.

La directiva de nomenclatura se aplica a los grupos que se crean en todas las cargas de trabajo de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.). Se aplica tanto al nombre del grupo como al alias del grupo. También se aplica cuando un usuario crea un grupo y cuando el nombre del grupo, alias, descripción o avatar se edita para un grupo existente.

> [!TIP]
> Una directiva de nomenclatura de grupos de Microsoft 365 solo se aplica a los grupos de Microsoft 365. No se aplica a los grupos de distribución creados en Exchange Online. Para crear una directiva de nomenclatura para grupos de distribución, vea Crear una directiva de nomenclatura [de grupos de distribución.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)

La directiva de nomenclatura de grupos consta de las siguientes características:

- **Directiva de nomenclatura** de prefijos y sufijos: puede usar prefijos o sufijos para definir la convención de nomenclatura de grupos (por ejemplo: "Ingeniería de mi grupo de EE. UU."). \_ \_ Los prefijos o sufijos pueden ser cadenas fijas o atributos de usuario como [Department] que se sustituirán en función del usuario que está creando el grupo.

- **Palabras bloqueadas personalizadas:** puede cargar un conjunto de palabras bloqueadas específicas de su organización que se bloquearían en grupos creados por usuarios. (Por ejemplo: "CEO, Nómina, RECURSOS HUMANOS").

## <a name="licensing-requirements"></a>Requisitos de licencia

El uso de la directiva de nomenclatura de Azure AD para Grupos de Microsoft 365 requiere que posea, pero no necesariamente, una licencia de Azure Active Directory Premium P1 o una licencia edu básica de Azure AD para cada usuario único (incluidos los invitados) que sea miembro de uno o más grupos de Microsoft 365.

Esto también es necesario para el administrador que crea la directiva de nomenclatura de grupos.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix de nomenclatura

Los prefijos y sufijos pueden ser cadenas fijas o atributos de usuario.

### <a name="fixed-strings"></a>Cadenas fijas

Puede usar cadenas cortas que pueden ayudarle a diferenciar los grupos de la GAL y la navegación izquierda de las cargas de trabajo del grupo. Algunos de los sufijos de prefijo comunes son palabras clave como 'Grp \_ Name', \# 'Name', ' \_ Name'

### <a name="attributes"></a>Atributos

Puede usar atributos que pueden ayudar a identificar quién creó el grupo como [Departamento] y dónde se creó a partir de [País].

Ejemplos:

- Policy = "GRP [GroupName] [Department]"
- Departamento del usuario = Ingeniería
- Nombre de grupo creado = "GRP My Group Engineering"

Los atributos admitidos de Azure Active Directory (Azure AD) son [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] y [Title].

- Los atributos de usuario no admitidos se consideran cadenas fijas, por ejemplo [postalCode].

- Los atributos de extensión y los atributos personalizados no son compatibles.

Se recomienda usar atributos que tengan valores rellenados para todos los usuarios de la organización y no usen atributos que tengan valores más largos.

### <a name="things-to-look-out-for"></a>Aspectos que hay que tener en cuenta

- Durante la creación de directivas, la longitud total de la cadena de prefijos y sufijos está restringida a 53 caracteres.

- Los prefijos y sufijos pueden contener caracteres especiales admitidos en el nombre de grupo y el alias de grupo. Cuando los prefijos y sufijos contienen caracteres especiales que no están permitidos en el alias de grupo, solo se aplican al nombre del grupo. Por lo tanto, en este caso, los prefijos y sufijos aplicados al nombre del grupo serían diferentes de los que se aplican al alias de grupo.

  > [!NOTE]
  > Se permite un punto (.) o un guión (-) en cualquier parte del nombre del grupo, excepto al principio o al final del nombre. Se permite un carácter de subrayado (_) en cualquier parte del nombre del grupo, incluso al principio o al final del nombre.

- Si usa grupos conectados a Yammer Office 365, evite usar los siguientes caracteres en la directiva de nomenclatura: @, \# \[ , , \] \<, and \> . Si estos caracteres están en la directiva de nomenclatura, los usuarios normales de Yammer no podrán crear grupos.

> [!Tip]
> - Use cadenas cortas como sufijo.
> - Use atributos con valores.
> - No seas demasiado creativo, la longitud total del nombre tiene un máximo de 264 caracteres.
> - Cargue palabras bloqueadas específicas de su organización para restringir el uso.

## <a name="custom-blocked-words"></a>Palabras bloqueadas personalizadas

Puede escribir una lista separada por comas de palabras bloqueadas que se bloquearán en nombres de grupo y alias.

No se realizan búsquedas de subcadenas; específicamente, se requiere una coincidencia exacta entre el nombre especificado por el usuario y las palabras bloqueadas personalizadas para desencadenar un error.

**Aspectos que debe tener en cuenta:**

- Las palabras bloqueadas no tienen en cuenta mayúsculas de minúsculas.

- Cuando un usuario escribe una palabra bloqueada, el cliente del grupo mostrará un mensaje de error con la palabra bloqueada.

- No hay restricciones de caracteres en las palabras bloqueadas usadas.

- Hay un límite de 5000 palabras que se pueden establecer como palabras bloqueadas.

## <a name="admin-override"></a>Invalidación de administrador

Algunos administradores están exentos de estas directivas, en todas las cargas de trabajo de grupo y puntos de conexión, para que puedan crear grupos con estas palabras bloqueadas y con sus convenciones de nomenclatura deseadas. A continuación se muestra la lista de roles de administrador exentos de la directiva de nomenclatura de grupos.

- Administrador global

- Soporte técnico de nivel 1 de partner

- Soporte técnico de nivel de partner 2

- Administrador de cuentas de usuario

## <a name="how-to-set-up-the-naming-policy"></a>Cómo configurar la directiva de nomenclatura

Para configurar una directiva de nomenclatura:

1. En [Azure Active Directory,](https://aad.portal.azure.com)en **Administrar**, haga clic en **Grupos.**
2. En **Configuración,** haga **clic en Directiva de nomenclatura.**
3. Elija la **pestaña Directiva de nomenclatura de** grupos.
4. En **Directiva actual,** elija si desea requerir un prefijo o sufijo o ambos y active las casillas correspondientes.
5. Elija entre **atributo** y **cadena** para cada línea y, a continuación, especifique el atributo o la cadena.
6. Cuando haya agregado los prefijos y sufijos que necesita, haga clic en **Guardar**.

![Captura de pantalla de la configuración de directiva de nomenclatura de grupos en Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso del gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear un plan de gobierno de colaboración](collaboration-governance-first.md)

[Cmdlets de Azure Active Directory para configurar configuraciones de grupo](https://go.microsoft.com/fwlink/?linkid=868341)
