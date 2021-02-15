---
title: Prepararse para la sincronización de directorios de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Describe cómo prepararse para aprovisionar usuarios a Microsoft 365 mediante la sincronización de directorios y las ventajas a largo plazo de usar este método.
ms.openlocfilehash: e49cc4472b47320650d8a0ca90395b69ae5b6df7
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371629"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Prepararse para la sincronización de directorios de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Entre las ventajas de la sincronización de directorios e identidades híbridas se incluyen:

- Reducción de los programas administrativos de la organización
- Habilitar opcionalmente el escenario de inicio de sesión único
- Automatizar los cambios de cuenta en Microsoft 365

Para obtener más información sobre las ventajas de usar la sincronización de directorios, vea la identidad híbrida con [Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) y la identidad híbrida [de Microsoft 365.](plan-for-directory-synchronization.md)

Sin embargo, la sincronización de directorios requiere planificación y preparación para garantizar que los Servicios de dominio de Active Directory (AD DS) se sincronicen con el inquilino de Azure AD de su suscripción de Microsoft 365 con un mínimo de errores.

Siga estos pasos para obtener los mejores resultados.

## <a name="1-directory-cleanup-tasks"></a>1. Tareas de limpieza de directorios

Antes de sincronizar ad ds con el inquilino de Azure AD, debe limpiar su AD DS.

> [!IMPORTANT]
> Si no realiza la limpieza de AD DS antes de sincronizar, esto puede causar un impacto negativo significativo en el proceso de implementación. El ciclo de sincronización de directorios, la identificación de errores y la ree sincronización pueden tardar días o incluso semanas.

En su AD DS, complete las siguientes tareas de limpieza para cada cuenta de usuario a la que se asignará una licencia de Microsoft 365:

1. Asegúrese de que una dirección de correo electrónico válida y única en el **atributo proxyAddresses.**

2. Quite los valores duplicados en el **atributo proxyAddresses.**

3. Si es posible, asegúrese de un valor válido y único para el atributo **userPrincipalName** en el objeto **de usuario del** usuario. Para obtener la mejor experiencia de sincronización, asegúrese de que el UPN de AD DS coincide con el UPN de Azure AD. Si un usuario no tiene un valor para el atributo **userPrincipalName,** el objeto **de** usuario debe contener un valor válido y único para el atributo **sAMAccountName.** Quite los valores duplicados del **atributo userPrincipalName.**

4. Para un uso óptimo de la lista global de direcciones (GAL), asegúrese de que la información de los siguientes atributos de la cuenta de usuario de AD DS sea correcta:

   - givenName
   - surname
   - displayName
   - Puesto
   - Departamento
   - Oficina
   - Teléfono de la oficina
   - Teléfono móvil
   - Número de fax
   - Dirección
   - Ciudad
   - Provincia
   - Código postal
   - País o región

## <a name="2-directory-object-and-attribute-preparation"></a>2. Preparación de atributos y objetos de directorio

La sincronización de directorios correcta entre AD DS y Microsoft 365 requiere que los atributos de AD DS estén preparados correctamente. Por ejemplo, debe asegurarse de que no se usan caracteres específicos en determinados atributos que se sincronizan con el entorno de Microsoft 365. Los caracteres inesperados no provocan errores en la sincronización de directorios, pero pueden devolver una advertencia. Los caracteres no válidos provocarán errores en la sincronización de directorios.

También se producirá un error en la sincronización de directorios si algunos de los usuarios de AD DS tienen uno o más atributos duplicados. Cada usuario debe tener atributos únicos.

Los atributos que necesita preparar se enumeran aquí:

- **displayName**

  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365.
  - Si este atributo existe en el objeto de usuario, debe haber un valor para él. Es decir, el atributo no debe estar en blanco.
  - Número máximo de caracteres: 256

- **givenName**

  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365, pero Microsoft 365 no lo requiere ni lo usa.
  - Número máximo de caracteres: 64

- **mail**

  - El valor del atributo debe ser único dentro del directorio.

    > [!NOTE]
    > Si hay valores duplicados, se sincroniza el primer usuario con el valor. Los usuarios subsiguientes no aparecerán en Microsoft 365. Debe modificar el valor de Microsoft 365 o modificar ambos valores en AD DS para que ambos usuarios aparezcan en Microsoft 365.

- **mailNickname** (alias de Exchange)

  - El valor del atributo no puede comenzar con un punto (.).
  - El valor del atributo debe ser único dentro del directorio.

    > [!NOTE]
    > Los caracteres de subrayado ("_") en el nombre sincronizado indican que el valor original de este atributo contiene caracteres no válidos. Para obtener más información sobre este atributo, vea el atributo [de alias de Exchange](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).
    >

- **proxyAddresses**

  - Atributo de varios valores
  - Número máximo de caracteres por valor: 256
  - El valor del atributo no debe contener un espacio.
  - El valor del atributo debe ser único dentro del directorio.
  - Caracteres no válidos: \< \> ( ) ; , [ ] "

    Tenga en cuenta que los caracteres no válidos se aplican a los caracteres siguientes al delimitador de tipo y ":", de forma que SMTP:User@contso.com se permite, pero SMTP:user:M@contoso.com no lo está.

    > [!IMPORTANT]
    > Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico. Quite las direcciones duplicadas o no deseadas si existen.

- **sAMAccountName**

  - Número máximo de caracteres: 20
  - El valor del atributo debe ser único dentro del directorio.
  - Caracteres no válidos: [ \ " | , / : \< \> + = ; ? \* ']
  - Si un usuario tiene un atributo **sAMAccountName** no válido pero tiene un atributo **userPrincipalName** válido, la cuenta de usuario se crea en Microsoft 365.
  - Si **tanto sAMAccountName** como **userPrincipalName** no son válidos, se debe actualizar el atributo **userPrincipalName** de AD DS.

- **sn** (apellido)

  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365, pero Microsoft 365 no lo requiere ni lo usa.

- **targetAddress**

    Es necesario que el atributo **targetAddress** (por ejemplo, SMTP:tom@contoso.com) que se rellena para el usuario debe aparecer en la GAL de Microsoft 365. En escenarios de migración de mensajería de terceros, esto requeriría la extensión de esquema de Microsoft 365 para AD DS. La extensión de esquema de Microsoft 365 también agregaría otros atributos útiles para administrar objetos de Microsoft 365 que se rellenan con una herramienta de sincronización de directorios de AD DS. Por ejemplo, se agregaría el atributo **msExchHideFromAddressLists** para administrar buzones ocultos o grupos de distribución.

  - Número máximo de caracteres: 256
  - El valor del atributo no debe contener un espacio.
  - El valor del atributo debe ser único dentro del directorio.
  - Caracteres no válidos: \ \< \> ( ) ; , [ ] "
  - Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.

- **userPrincipalName**

  - El **atributo userPrincipalName** debe estar en el formato de inicio de sesión con estilo de Internet donde el nombre de usuario va seguido del signo (@) y un nombre de dominio: por ejemplo, user@contoso.com. Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.
  - El número máximo de caracteres para el **atributo userPrincipalName** es 113. Se permite un número específico de caracteres antes y después del signo (@), como se muestra a continuación:
  - Número máximo de caracteres para el nombre de usuario que está delante del signo (@): 64
  - Número máximo de caracteres para el nombre de dominio que sigue al signo (@): 48
  - Caracteres no válidos: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - Caracteres permitidos: A – Z, a - z, 0 – 9, ' . - _ ! # ^ ~
  - Las letras con signos diacríticos, como umlauts, acentos y tildes, son caracteres no válidos.
  - El carácter @ es obligatorio en cada **valor userPrincipalName.**
  - El carácter @ no puede ser el primer carácter de cada valor **userPrincipalName**.
  - El nombre de usuario no puede terminar con un punto (.), una yand ( ), un espacio o un signo &amp; (@).
  - El nombre de usuario no puede contener espacios.
  - Se deben usar dominios enrutables; por ejemplo, no se pueden usar dominios locales o internos.
  - Unicode se convierte a guiones bajos.
  - **userPrincipalName** no puede contener valores duplicados en el directorio.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Preparar el atributo userPrincipalName

Active Directory está diseñado para permitir que los usuarios finales de la organización inicien sesión en el directorio mediante **sAMAccountName** o **userPrincipalName**. De forma similar, los usuarios finales pueden iniciar sesión en Microsoft 365 con el nombre principal de usuario (UPN) de su cuenta de trabajo o escuela. La sincronización de directorios intenta crear nuevos usuarios en Azure Active Directory mediante el mismo UPN que se encuentra en AD DS. El UPN tiene el formato de una dirección de correo electrónico.

En Microsoft 365, el UPN es el atributo predeterminado que se usa para generar la dirección de correo electrónico. Es fácil obtener **userPrincipalName** (en AD DS y en Azure AD) y la dirección de correo electrónico principal en **proxyAddresses** establecida en valores diferentes. Cuando se establecen en valores diferentes, puede haber confusión para los administradores y los usuarios finales.

Es mejor alinear estos atributos para reducir la confusión. Para cumplir los requisitos del inicio de sesión único con Servicios de federación de Active Directory (AD FS) 2.0, debe asegurarse de que los UPN de Azure Active Directory y ad DS coincidan y usen un espacio de nombres de dominio válido.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Agregar un sufijo UPN alternativo a AD DS

Es posible que tenga que agregar un sufijo UPN alternativo para asociar las credenciales corporativas del usuario con el entorno de Microsoft 365. Un sufijo UPN es la parte de un UPN situada a la derecha del carácter @. Los UPN que se usan para el inicio de sesión único pueden contener letras, números, puntos, guiones y caracteres de subrayado, pero ningún otro tipo de carácter.

Para obtener más información sobre cómo agregar un sufijo UPN alternativo a Active Directory, vea [Preparar la sincronización de directorios.]( https://go.microsoft.com/fwlink/p/?LinkId=525430)

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Hacer coincidir el UPN de AD DS con el UPN de Microsoft 365

Si ya ha configurado la sincronización de directorios, es posible que el UPN del usuario para Microsoft 365 no coincida con el UPN de AD DS del usuario definido en su AD DS. Esto puede suceder cuando se ha asignado una licencia a un usuario antes de que se comprobara el dominio. Para corregir esto, use PowerShell para corregir el [UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) duplicado para actualizar el UPN del usuario para asegurarse de que el UPN de Microsoft 365 coincide con el nombre de usuario corporativo y el dominio. Si va a actualizar el UPN en AD DS y desea que se sincronice con la identidad de Azure Active Directory, debe quitar la licencia del usuario en Microsoft 365 antes de realizar los cambios en AD DS.

Vea también [cómo preparar un dominio no enrutable (como el dominio .local) para la sincronización de directorios.](prepare-a-non-routable-domain-for-directory-synchronization.md)

## <a name="next-steps"></a>Pasos siguientes

Si ha realizado los pasos 1 a 5 anteriores, consulte [Configurar la sincronización de directorios.](set-up-directory-synchronization.md)
