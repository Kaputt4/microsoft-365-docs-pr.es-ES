---
title: Prepararse para la sincronización de directorios de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Describe cómo prepararse para aprovisionar usuarios para Microsoft 365 mediante la sincronización de directorios y las ventajas a largo plazo de usar este método.
---

# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Prepararse para la sincronización de directorios de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Si ha elegido el modelo de identidad híbrida y configurado la protección para cuentas de administrador en el paso [2](protect-your-global-administrator-accounts.md) y cuentas de usuario en el paso [3](microsoft-365-secure-sign-in.md) de esta solución, la siguiente tarea es implementar la sincronización de directorios. Las ventajas de la sincronización de directorios para su organización incluyen:

- Reducción de los programas administrativos de la organización
- Habilitar opcionalmente un escenario de inicio de sesión único
- Automatizar los cambios de cuenta en Microsoft 365

Para obtener más información acerca de las ventajas de usar la sincronización de directorios, vea [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity).

Sin embargo, la sincronización de directorios requiere planeación y preparación para garantizar que los Servicios de dominio de Active Directory (AD DS) se sincronicen con el inquilino Azure AD de la suscripción Microsoft 365 con un mínimo de errores.

Siga estos pasos para obtener los mejores resultados.

> [!NOTE]
> Los caracteres que no son ASCII no se sincronizan para ningún atributo en la cuenta de usuario de AD DS.

## <a name="ad-ds-preparation"></a>Preparación de AD DS

Para garantizar una transición sin problemas a Microsoft 365 mediante la sincronización, debe preparar el bosque de AD DS antes de comenzar la implementación Microsoft 365 sincronización de directorios.
  
La preparación del directorio debe centrarse en las siguientes tareas:

- Quite los **atributos proxyAddress y** **userPrincipalName duplicados** .
- Actualice los atributos **userPrincipalName** en blanco y no válidos con atributos **userPrincipalName** válidos.
- Quite caracteres no válidos y cuestionables en los atributos **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** y **userPrincipalName** . Para obtener más información acerca de la preparación de atributos, consulte [Lista de atributos sincronizados por la Azure Active Directory sync tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).

    > [!NOTE]
    > Estos son los mismos atributos que Azure AD Conectar sincroniza. 
  
## <a name="multi-forest-deployment-considerations"></a>Consideraciones de implementación de varios bosques

Para varios bosques y opciones de SSO, use [una instalación personalizada de Azure AD Conectar](/azure/active-directory/hybrid/how-to-connect-install-custom).
  
Si su organización tiene varios bosques para la autenticación (bosques de inicio de sesión), se recomienda encarecidamente lo siguiente:
  
- **Considere la posibilidad de consolidar los bosques.** En general, hay más sobrecarga necesaria para mantener varios bosques. A menos que su organización tenga restricciones de seguridad que dicten la necesidad de bosques independientes, considere la posibilidad de simplificar el entorno local.
- **Solo se usa en el bosque de inicio de sesión principal.** Considere la posibilidad de Microsoft 365 solo en el bosque de inicio de sesión principal para el lanzamiento inicial de Microsoft 365. 

Si no puedes consolidar la implementación de AD DS de varios bosques o estás usando otros servicios de directorio para administrar identidades, es posible que puedas sincronizarlas con la ayuda de Microsoft o un partner.
  
Vea [Topologías para obtener Azure AD Conectar](/azure/active-directory/hybrid/plan-connect-topologies) para obtener más información.
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>Características que dependen de la sincronización de directorios
  
La sincronización de directorios es necesaria para las siguientes características y funcionalidades:
  
- Azure AD seamless single Sign-On (SSO)
- Skype coexistencia
- Exchange implementación híbrida, incluida:
  - Lista global de direcciones (GAL) totalmente compartida entre el entorno Exchange local y Microsoft 365.
  - Sincronización de información de GAL desde varios sistemas de correo.
  - La capacidad de agregar usuarios a y quitar usuarios de Microsoft 365 ofertas de servicio. Esto requiere lo siguiente:
  - La sincronización bidireccional debe configurarse durante la instalación de sincronización de directorios. De forma predeterminada, las herramientas de sincronización de directorios escriben información de directorio solo en la nube. Al configurar la sincronización bidireccional, se habilita la funcionalidad de reescribición para que un número limitado de atributos de objeto se copien de la nube y, a continuación, se vuelvan a escribir en su AD DS local. La reescribición también se conoce como Exchange modo híbrido. 
  - Una implementación híbrida Exchange local
  - La capacidad de mover algunos buzones de usuario a Microsoft 365 mientras se mantienen otros buzones de usuario locales.
  - Caja fuerte remitentes y remitentes bloqueados localmente se replican en Microsoft 365.
  - Función de delegación básica y envío en nombre de otra persona.
  - Tiene una tarjeta inteligente local integrada o una solución de autenticación multifactor.
- Sincronización de fotos, miniaturas, salas de conferencia y grupos de seguridad

## <a name="1-directory-cleanup-tasks"></a>1. Tareas de limpieza de directorios

Antes de sincronizar tu AD DS con tu Azure AD inquilino, debes limpiar tu AD DS.

> [!IMPORTANT]
> Si no realizas la limpieza de AD DS antes de sincronizar, puede provocar un impacto negativo significativo en el proceso de implementación. Puede tardar días o incluso semanas en pasar por el ciclo de sincronización de directorios, identificar errores y volver a sincronizar.

En AD DS, complete las siguientes tareas de limpieza para cada cuenta de usuario a la que se le asignará una Microsoft 365 licencia:

1. Asegúrese de que una dirección de correo electrónico válida y única en el **atributo proxyAddresses** .

2. Quite los valores duplicados del **atributo proxyAddresses** .

3. Si es posible, asegúrese de que el atributo **userPrincipalName** es válido y único en el objeto **de usuario del** usuario. Para obtener la mejor experiencia de sincronización, asegúrese de que el UPN de AD DS coincide con Azure AD UPN. Si un usuario no tiene un valor para el atributo **userPrincipalName** , el objeto **user** debe contener un valor válido y único para el atributo **sAMAccountName** . Quite los valores duplicados del **atributo userPrincipalName** .

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

La sincronización correcta de directorios entre ad ds y Microsoft 365 requiere que los atributos de AD DS estén preparados correctamente. Por ejemplo, debe asegurarse de que los caracteres específicos no se usan en determinados atributos que se sincronizan con el Microsoft 365 usuario. Los caracteres inesperados no provocan errores en la sincronización de directorios, pero pueden devolver una advertencia. Los caracteres no válidos provocarán un error en la sincronización de directorios.

La sincronización de directorios también producirá un error si algunos de los usuarios de AD DS tienen uno o más atributos duplicados. Cada usuario debe tener atributos únicos.

Los atributos que necesita preparar se enumeran aquí:

- **displayName**

  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365.
  - Si este atributo existe en el objeto de usuario, debe haber un valor para él. Es decir, el atributo no debe estar en blanco.
  - Número máximo de caracteres: 256

- **givenName**

  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365, pero Microsoft 365 no lo requiere ni lo usa.
  - Número máximo de caracteres: 64

- **mail**

  - El valor del atributo debe ser único en el directorio.

    > [!NOTE]
    > Si hay valores duplicados, se sincroniza el primer usuario con el valor. Los usuarios posteriores no aparecerán en Microsoft 365. Debe modificar el valor de Microsoft 365 o modificar ambos valores en AD DS para que ambos usuarios aparezcan en Microsoft 365.

- **mailNickname** (Exchange alias)

  - El valor del atributo no puede comenzar por un punto (.).
  - El valor del atributo debe ser único en el directorio.

    > [!NOTE]
    > Los caracteres de subrayado ("_") en el nombre sincronizado indican que el valor original de este atributo contiene caracteres no válidos. Para obtener más información sobre este atributo, [vea Exchange alias.](/powershell/module/exchange/set-mailbox)
    >

- **proxyAddresses**

  - Atributo de varios valores
  - Número máximo de caracteres por valor: 256
  - El valor del atributo no debe contener un espacio.
  - El valor del atributo debe ser único en el directorio.
  - Caracteres no válidos: \< \> ( ) ; , [ ] "
  - Las letras con marcas diacríticos, como umlauts, acentos y tildes, son caracteres no válidos.

    Tenga en cuenta que los caracteres no válidos se aplican a los caracteres siguientes al delimitador de tipos y ,, de forma que SMTP:User@contso.com, pero SMTP:user:M@contoso.com no lo es.

    > [!IMPORTANT]
    > Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico. Quite las direcciones duplicadas o no deseadas si existen.

- **sAMAccountName**

  - Número máximo de caracteres: 20
  - El valor del atributo debe ser único en el directorio.
  - Caracteres no válidos: [ \ " | , / : \< \> + = ; ? \* ']
  - Si un usuario tiene un atributo **sAMAccountName** no válido pero tiene un atributo **userPrincipalName** válido, la cuenta de usuario se crea en Microsoft 365.
  - Si tanto **sAMAccountName** como **userPrincipalName** no son válidos, se debe actualizar el atributo **userPrincipalName** de AD DS.

- **sn** (apellido)

  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365, pero Microsoft 365 no lo requiere ni lo usa.

- **targetAddress**

    Es necesario que el atributo **targetAddress** (por ejemplo, SMTP:tom@contoso.com) que se rellena para el usuario debe aparecer en la GAL Microsoft 365. En escenarios de migración de mensajería de terceros, esto requeriría la Microsoft 365 de esquema para AD DS. La Microsoft 365 de esquema también agregaría otros atributos útiles para administrar Microsoft 365 objetos que se rellenan mediante una herramienta de sincronización de directorios de AD DS. Por ejemplo, se agregaría **el atributo msExchHideFromAddressLists para administrar buzones** o grupos de distribución ocultos.

  - Número máximo de caracteres: 256
  - El valor del atributo no debe contener un espacio.
  - El valor del atributo debe ser único en el directorio.
  - Caracteres no válidos: \ \< \> ( ) ; , [ ] "
  - Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.

- **userPrincipalName**

  - El **atributo userPrincipalName** debe tener el formato de inicio de sesión de estilo de Internet donde el nombre de usuario va seguido del signo at (@) y un nombre de dominio: por ejemplo, user@contoso.com. Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.
  - El número máximo de caracteres para el **atributo userPrincipalName** es 113. Se permite un número específico de caracteres antes y después del signo at (@), como se muestra a continuación:
  - Número máximo de caracteres para el nombre de usuario que está delante del signo at (@): 64
  - Número máximo de caracteres para el nombre de dominio después del signo at (@): 48
  - Caracteres no válidos: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - Caracteres permitidos: A – Z, a - z, 0 – 9, ' . - _ ! # ^ ~
  - Las letras con marcas diacríticos, como umlauts, acentos y tildes, son caracteres no válidos.
  - El carácter @ es necesario en cada **valor userPrincipalName** .
  - El carácter @ no puede ser el primer carácter de cada valor **userPrincipalName**.
  - El nombre de usuario no puede terminar con un punto (.), una yand (&amp;), un espacio o un signo at (@).
  - El nombre de usuario no puede contener espacios.
  - Se deben usar dominios enrutables; por ejemplo, no se pueden usar dominios locales o internos.
  - Unicode se convierte a guiones bajos.
  - **userPrincipalName** no puede contener valores duplicados en el directorio.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Preparar el atributo userPrincipalName

Active Directory está diseñado para permitir que los usuarios finales de la organización inicien sesión en el directorio mediante **sAMAccountName** o **userPrincipalName**. Del mismo modo, los usuarios finales pueden iniciar sesión en Microsoft 365 usando el nombre principal de usuario (UPN) de su cuenta laboral o educativa. La sincronización de directorios intenta crear nuevos usuarios en Azure Active Directory mediante el mismo UPN que está en su AD DS. El UPN tiene el formato de una dirección de correo electrónico.

En Microsoft 365, el UPN es el atributo predeterminado que se usa para generar la dirección de correo electrónico. Es fácil obtener **userPrincipalName** (en AD DS y en Azure AD) y la dirección de correo electrónico principal en **proxyAddresses** establecida en valores diferentes. Cuando se establecen en valores diferentes, puede haber confusión para los administradores y los usuarios finales.

Es mejor alinear estos atributos para reducir la confusión. Para cumplir los requisitos del inicio de sesión único con Servicios de federación de Active Directory (AD FS) 2.0, debe asegurarse de que los UPN de Azure Active Directory y su AD DS coincidan y usen un espacio de nombres de dominio válido.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Agregar un sufijo UPN alternativo a AD DS

Es posible que deba agregar un sufijo UPN alternativo para asociar las credenciales corporativas del usuario con el entorno Microsoft 365 usuario. Un sufijo UPN es la parte de un UPN situada a la derecha del carácter @. Los UPN que se usan para el inicio de sesión único pueden contener letras, números, puntos, guiones y caracteres de subrayado, pero ningún otro tipo de carácter.

Para obtener más información sobre cómo agregar un sufijo UPN alternativo a Active Directory, vea [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=525430).

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Hacer coincidir el UPN de AD DS Microsoft 365 UPN

Si ya ha configurado la sincronización de directorios, es posible que el UPN del usuario para Microsoft 365 no coincida con el UPN de AD DS definido en su AD DS. Esto puede suceder cuando se ha asignado una licencia a un usuario antes de que se comprobara el dominio. Para solucionar esto, use [PowerShell para corregir upn](https://go.microsoft.com/fwlink/p/?LinkId=396730) duplicado para actualizar el UPN del usuario para asegurarse de que el UPN de Microsoft 365 coincide con el nombre de usuario corporativo y el dominio. Si está actualizando el UPN en AD DS y desea que se sincronice con la identidad de Azure Active Directory, debe quitar la licencia del usuario en Microsoft 365 antes de realizar los cambios en AD DS.

Vea también [Cómo preparar un dominio no enrutable (por ejemplo, dominio .local) para la sincronización de directorios](prepare-a-non-routable-domain-for-directory-synchronization.md).

## <a name="next-steps"></a>Pasos siguientes

Después de realizar del 1 al 5 anterior, consulte [Configurar la sincronización de directorios](set-up-directory-synchronization.md).
