---
title: Implementar la infraestructura de identidad para Microsoft 365
f1.keywords:
  - NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
  - M365-identity-device-management
  - Strat_O365_Enterprise
  - m365initiative-coredeploy
  - m365solution-m365-identity
  - m365solution-scenario
  - m365solution-overview
ms.custom:
  - intro-overview
description: Implemente la infraestructura de identidad para Microsoft 365.
---

# <a name="deploy-your-identity-infrastructure-for-microsoft-365"></a>Implementar la infraestructura de identidad para Microsoft 365

En Microsoft 365 empresa, una infraestructura de identidades bien planeada y ejecutada allana el camino para una seguridad más sólida, incluida la restricción del acceso a las cargas de trabajo de productividad y sus datos a solo usuarios y dispositivos autenticados. La seguridad de las identidades es un elemento clave de una implementación de confianza cero, en la que todos los intentos de acceso a los recursos locales y en la nube se autentican y autorizan.

Para obtener información sobre las características de identidad de cada Microsoft 365 para empresas, el rol de Azure Active Directory (Azure AD), los componentes locales y basados en la nube y las configuraciones de autenticación más comunes, consulte el póster infraestructura de [identidad.](../downloads/m365e-identity-infra.pdf)

[![Póster de infraestructura de identidad.](../downloads/m365e-identity-infra.png)](../downloads/m365e-identity-infra.pdf)

Revise este póster de dos páginas para aumentar rápidamente los conceptos de identidad y las configuraciones para Microsoft 365 empresa.

Puede descargar [este póster y](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/m365e-identity-infra.pdf) imprimirlo en formato carta, legal o tabloide (11 x 17).

## <a name="whats-in-this-solution"></a>Acerca de esta solución

Esta solución le ayuda a implementar una infraestructura de identidad para su inquilino Microsoft 365 proporcionar acceso a los empleados y protección contra ataques basados en identidades.

![Implementar la infraestructura de identidad para Microsoft 365](../media/deploy-identity-solution-overview/deploy-identity-solution-overview.png)

Los pasos de esta solución son:

1. [Determine el modelo de identidad.](deploy-identity-solution-identity-model.md)
2. [Proteja sus Microsoft 365 cuentas con privilegios.](protect-your-global-administrator-accounts.md)
3. [Proteja sus Microsoft 365 de usuario.](microsoft-365-secure-sign-in.md)
4. [Implemente el modelo de identidad.](cloud-only-identities.md)

Esta solución admite los principios clave de [la confianza cero](https://www.microsoft.com/security/business/zero-trust/):

- **Comprobar de forma explícita:** autentique y autorice siempre en función de todos los puntos de datos disponibles.
- **Usar acceso con privilegios mínimos:** limite el acceso del usuario con acceso suficiente y justo a tiempo (JIT/JEA), directivas adaptables basadas en los riesgos y protección de datos.
- **Asumir la vulneración:** minimice el radio de explosión y el acceso a los segmentos. Compruebe el cifrado de un extremo a otro y use análisis para obtener visibilidad, impulsar la detección de amenazas y mejorar las defensas.

A diferencia del acceso convencional a la intranet, que confía en todo lo que hay detrás del firewall de una organización, Confianza cero trata cada inicio de sesión y acceso como si se originase en una red no controlada, ya sea detrás del firewall de la organización o en Internet. Confianza cero requiere protección para la red, la infraestructura, las identidades, los puntos de conexión, las aplicaciones y los datos.

## <a name="microsoft-365-capabilities-and-features"></a>Funcionalidades y características de Microsoft 365

Azure AD proporciona un conjunto completo de capacidades de seguridad y administración de identidades para su Microsoft 365 inquilino.

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|[Autenticación multifactor (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA requiere que los usuarios proporcionen dos formas de comprobación, como una contraseña de usuario más una notificación de la aplicación Microsoft Authenticator o una llamada de teléfono. MFA reduce en gran medida el riesgo de que las credenciales robadas se puedan usar para obtener acceso al entorno. Microsoft 365 el servicio Azure AD multifactor authentication para inicios de sesión basados en MFA.|Microsoft 365 E3 o E5|
|[Acceso condicional](/azure/active-directory/conditional-access/overview)|Azure AD evalúa las condiciones del inicio de sesión del usuario y usa directivas de acceso condicional para determinar el acceso permitido. Por ejemplo, en esta guía te mostramos cómo crear una directiva de acceso condicional para requerir el cumplimiento del dispositivo para obtener acceso a datos confidenciales. Esto reduce en gran medida el riesgo de que un hacker con su propio dispositivo y credenciales robadas pueda acceder a sus datos confidenciales. También protege los datos confidenciales de los dispositivos, ya que los dispositivos deben cumplir requisitos específicos de salud y seguridad.|Microsoft 365 E3 o E5|
|[Azure AD grupos](/azure/active-directory/fundamentals/active-directory-manage-groups)|Las directivas de acceso condicional, la administración de dispositivos con Intune e incluso los permisos para archivos y sitios de la organización dependen de la asignación a cuentas de usuario o Azure AD grupos. Se recomienda crear grupos Azure AD que correspondan a los niveles de protección que está implementando. Por ejemplo, es probable que el personal ejecutivo sea un destino de mayor valor para los hackers. Por lo tanto, tiene sentido agregar las cuentas de usuario de estos empleados a un grupo de Azure AD y asignar este grupo a directivas de acceso condicional y otras directivas que aplican un mayor nivel de protección para el acceso.|Microsoft 365 E3 o E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar la directiva de corrección automatizada en riesgo de inicio de sesión bajo, medio y alto y riesgo de usuario. Esta guía se basa en esta evaluación de riesgos para aplicar directivas de acceso condicional para la autenticación multifactor. Esta guía también incluye una directiva de acceso condicional que requiere que los usuarios cambien su contraseña si se detecta actividad de alto riesgo para su cuenta.|Microsoft 365 E5, Microsoft 365 E3 con el complemento de seguridad E5, EMS E5 o Azure AD Premium P2 licencias|
|[Restablecimiento de contraseñas de autoservicio (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Permitir que los usuarios restablezcan sus contraseñas de forma segura y sin intervención del servicio de asistencia, proporcionando la comprobación de varios métodos de autenticación que el administrador puede controlar.|Microsoft 365 E3 o E5|
|[Azure AD contraseña](/azure/active-directory/authentication/concept-password-ban-bad)|Detectar y bloquear contraseñas débiles conocidas y sus variantes y términos débiles adicionales que son específicos de su organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.|Microsoft 365 E3 o E5|
|

## <a name="next-steps"></a>Pasos siguientes

Siga estos pasos para implementar un modelo de identidad y una infraestructura de autenticación para su Microsoft 365 inquilino:

1. [Determine el modelo de identidad de la nube.](deploy-identity-solution-identity-model.md)
2. [Proteja sus Microsoft 365 cuentas con privilegios.](protect-your-global-administrator-accounts.md)
3. [Proteja sus Microsoft 365 de usuario.](microsoft-365-secure-sign-in.md)
4. Implemente el modelo de identidad de nube: [solo en la nube](cloud-only-identities.md) o [híbrido](prepare-for-directory-synchronization.md).

[![Determinar el modelo de identidad que se usará para su Microsoft 365 inquilino](../media/deploy-identity-solution-overview/identity-solution-identity-model.png)](deploy-identity-solution-identity-model.md)
  
## <a name="additional-microsoft-cloud-identity-resources"></a>Recursos de identidad de nube de Microsoft adicionales

### <a name="manage"></a>Administrar

Para administrar la implementación de identidades en la nube de Microsoft, vea:

- [Cuentas de usuario](manage-microsoft-365-accounts.md)
- [Licencias](assign-licenses-to-user-accounts.md)
- [Contraseñas](manage-microsoft-365-passwords.md)
- [Grupos](manage-microsoft-365-groups.md)
- [Gobierno](manage-microsoft-365-identity-governance.md)
- [Sincronización de directorios](view-directory-synchronization-status.md)

### <a name="how-microsoft-does-identity-for-microsoft-365"></a>Cómo Microsoft hace identidad para Microsoft 365

Aprenda como los expertos de IT en Microsoft[administran identidades y acceso seguro](https://www.microsoft.com/en-us/itshowcase/managing-user-identities-and-secure-access-at-microsoft).

>[!Note]
>Este recurso De presentación de IT solo está disponible en inglés.
>

### <a name="how-contoso-did-identity-for-microsoft-365"></a>Cómo contoso hizo identidad para Microsoft 365

Para obtener un ejemplo de cómo una organización multinacional ficticia pero representativa ha implementado una infraestructura de identidad híbrida para Microsoft 365 servicios en la nube, vea [Identity for the Contoso Corporation](contoso-identity.md).

<!--

## Plan

To plan for your identity implementation:

- [Understand the different identity models](about-microsoft-365-identity.md)
- [Plan for hybrid identity and directory synchronization](plan-for-directory-synchronization.md)

## Deploy

To deploy your identity implementation:

- [Protect your global administrator accounts](protect-your-global-administrator-accounts.md)
- [Configure and use cloud-only identities](cloud-only-identities.md)
- [Configure and use hybrid identities](prepare-for-directory-synchronization.md)
- [Set up directory synchronization](set-up-directory-synchronization.md)
- If needed, deploy [hybrid identity scenarios](hybrid-solutions.md)

### Identity and device access recommendations

To help ensure a secure and productive workforce, Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md). For identity, use the recommendations and settings in these articles:

- [Prerequisites](../security/office-365-security/identity-access-prerequisites.md)
- [Common identity and device access policies](../security/office-365-security/identity-access-policies.md)

--> 
