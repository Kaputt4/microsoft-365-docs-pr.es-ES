---
title: 'Paso 9: Simplificar las actualizaciones de contraseñas'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la escritura diferida de contraseñas para entornos híbridos.
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871341"
---
# <a name="step-9-simplify-password-updates"></a>Paso 9: Simplificar las actualizaciones de contraseñas

*Este paso es opcional para los entornos híbridos y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, permitirá que los usuarios restablezcan sus contraseñas a través de Azure Active Directory (AD), que se replica después en la instancia local de Windows Server Active Directory (AD). Este proceso se conoce como escritura diferida de contraseñas. Con la escritura diferida de contraseñas, los usuarios no necesitan actualizar sus contraseñas a través de la instancia local de Windows Server AD donde se almacenan las cuentas de usuario y sus atributos. Esto resulta útil para los usuarios remotos o en itinerancia que no tengan una conexión de acceso remoto a la red local.

La escritura diferida de contraseñas es necesaria para utilizar por completo las funcionalidades de la característica de Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando se haya detectado un alto riesgo de que la cuenta se haya visto comprometida.

Para obtener más información e instrucciones de configuración, vea [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) (SSPR de Azure AD con escritura diferida de contraseñas).

>[!Note]
>Actualice a la última versión de Azure AD Connect para garantizar que tiene la mejor experiencia posible y nuevas características cuando se publican. Para obtener más información, vea [Instalación personalizada de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

Como control interno, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-pw-writeback) de este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [Simplificar el inicio de sesión de usuario](identity-single-sign-on.md) |

