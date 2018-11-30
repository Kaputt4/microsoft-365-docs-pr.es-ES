---
title: Protección de la información en Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre cómo usa Contoso las características de protección de la información de Microsoft 365 Enterprise para proteger sus activos digitales en la nube.
ms.openlocfilehash: 2f6619aa3c6051696644b055e6c766525ad3a26d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871705"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Protección de la información en Contoso Corporation

**Resumen:** Obtenga información sobre cómo usa Contoso las características de protección de la información de Microsoft 365 Enterprise para proteger sus activos digitales en la nube.

Contoso se toma en serio la seguridad y la protección de la información. Por ejemplo, la filtración o destrucción de la propiedad intelectual en la que se describen diseños de productos y técnicas de fabricación propietarias les colocaría en desventaja con respecto a la competencia.

Antes de mover a la nube sus activos digitales confidenciales y más valiosos, se han asegurado de que los requisitos locales de clasificación y protección de la información se admitieran e implementaran en los servicios basados en la nube de Microsoft 365 Enterprise.

## <a name="contosos-data-security-classification"></a>Clasificación de seguridad de datos de Contoso

Contoso realizó un análisis de los datos y determinó los niveles siguientes.

||||
|:-------|:-----|:-----|
| **Nivel 1: Base de referencia** | **Nivel 2: Confidencial** | **Nivel 3: Altamente regulado** |
| Los datos están cifrados y solo están disponibles para los usuarios autenticados <BR> <BR> Se proporciona para todos los datos almacenados de forma local y en almacenamiento y cargas de trabajo basadas en la nube, como Office 365. Los datos se encriptan mientras residen en el servicio y en tránsito entre el servicio y los dispositivos de cliente. <BR><BR> Algunos ejemplos de datos de nivel 1 son las comunicaciones empresariales normales (correo electrónico) y los archivos de empleados administrativos, de ventas y de soporte técnico. | Características del nivel 1 más autenticación sólida y protección contra la pérdida de datos: <BR> <BR> La autenticación segura incluye autenticación multifactor con validación de SMS. La prevención de pérdida de datos garantiza que la información crítica o confidencial no sale de la red local.
 <BR><BR> Algunos ejemplos de datos de nivel 2 son la información jurídica y financiera, y los datos de investigación y desarrollo de productos nuevos. | Características del nivel 2 además de los niveles más altos de cifrado, autenticación y auditoría. <BR> <BR>  Los niveles más altos de cifrado de datos en reposo y en la nube, conformes con la normativa regional, combinados con autentificación multifactor con tarjetas inteligentes y auditoría y alertas pormenorizadas. <BR> <BR> Algunos ejemplos de datos de nivel 3 son la información de identificación personal de clientes y partners, las especificaciones de ingeniería de productos y las técnicas de fabricación propietarias.  |
||||

## <a name="contosos-information-policies"></a>Directivas de información de Contoso
En la tabla siguiente se enumeran las directivas de información de Contoso.

|||||
|:-------|:-----|:-----|:-----|
|  | **Acceso** | **Retención de datos** | **Protección de la información** |
| Nivel 1: valor empresarial bajo (Base de referencia) | Se permite el acceso a todo el mundo  | 6 meses | Se usa cifrado |
| Nivel 2: valor empresarial medio (Confidencial) | Se permite el acceso a subcontratistas, partners y empleados de Contoso <BR> <BR> Se usa la autenticación multifactor (MFA), Seguridad de la capa de transporte (TLS) y Administración de aplicaciones móviles (MAM) | 2 años  | Se usan valores de hash para la integridad de datos  |
| Nivel 3: valor empresarial alto (Altamente regulado) | Se permite el acceso a ejecutivos y clientes potenciales de ingeniería y fabricación <BR> <BR> Rights Management System (RMS) solo con dispositivos de red administrados  | 7 años  | Se usan firmas digitales para evitar el rechazo  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a>Ruta de Contoso a la protección de la información con Microsoft 365 Enterprise

Contoso siguió los pasos siguientes para preparar Microsoft 365 Enterprise para sus requisitos de protección de la información:

1. Identificó qué información se iba a proteger.

   Contoso realizó una revisión exhaustiva de los activos digitales existentes en sitios locales de SharePoint y recursos compartidos de archivos, y los clasificó todos.

2. Determinó las directivas de acceso, retención y protección de la información para los niveles de datos.

   En función de los niveles de datos, Contoso determinó requisitos de directiva detallados que se usaron para proteger los activos digitales al cambiarlos a la nube.

3. Creó y configuró etiquetas de Azure Information Protection para los diferentes niveles de información.

   Contoso modificó las etiquetas predeterminadas de Azure Information Protection con los títulos que coincidían con sus niveles de datos y configuró las etiquetas Confidencial y Altamente regulado para cifrarlas con la clave de nube de Azure. Crearon subetiquetas de la etiqueta Altamente regulado para tipos concretos de datos secretos comerciales y limitaron el acceso a grupos de investigación y desarrollo específicos. Además, implementaron el cliente de Azure Information Protection en todos los equipos y dispositivos Windows.

4. Crearon sitios de SharePoint Online protegidos para datos confidenciales y altamente regulados con permisos para bloquear el acceso.

   Los sitios confidenciales y con reglamentos estrictos se configuraron como [sitios aislados](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites), donde se personalizaron los permisos de sitios de grupo de SharePoint Online predeterminados para grupos de Azure AD. Los sitios confidenciales y con reglamentos estrictos de SharePoint Online también se configuraron con una etiqueta predeterminada de Office 365. Los archivos almacenados en sitios de SharePoint Online con reglamentos estrictos están protegidos con una subetiqueta de Azure Information Protection (AIP) de una directiva con ámbito. Para obtener más información, vea el escenario [Sitios de SharePoint Online y Microsoft Teams para datos con reglamentos estrictos](teams-sharepoint-online-sites-highly-regulated-data.md).

5.  Se movieron los datos de los sitios de SharePoint locales y los recursos compartidos de archivos a los nuevos sitios de SharePoint Online.

    Los archivos que se migraron a los nuevos sitios de SharePoint Online heredaron las etiquetas predeterminadas de Office 365 asignadas al sitio.

6.  Se formó a los empleados sobre cómo usar las etiquetas de Azure Information Protection para los documentos nuevos, cómo interactuar con el departamento de TI de Contoso al crear sitios de SharePoint Online y almacenar siempre los activos digitales en sitios de SharePoint Online.

    Asumiendo que era el aspecto más difícil de la transición a la nube de la protección de la información, los departamentos de TI y administración de Contoso tuvieron que cambiar los hábitos incorrectos de almacenamiento de la información por parte de los empleados de la organización para que etiquetaran siempre los activos digitales y nunca usaran recursos compartidos de archivos locales.

## <a name="conditional-access-policies-for-information-protection"></a>Directivas de acceso condicional para la protección de la información

Junto con la infraestructura de administración de identidades y dispositivos móviles, y como parte de su implementación de Exchange Online y SharePoint Online, Contoso configuró el siguiente conjunto de directivas de acceso condicional y las aplicó a los grupos de Azure AD adecuados:

- [Directivas de acceso a aplicaciones administradas y no administradas en dispositivos](identity-access-policies.md)
- [Directivas de acceso de Exchange Online](secure-email-recommended-policies.md)
- [Directivas de acceso de SharePoint Online](sharepoint-file-access-policies.md)

En la Figura 1 se muestra el conjunto resultante de directivas de protección de la información de Contoso.

![](./media/contoso-info-protect/contoso-info-protect-fig1.png)

**Figura 1: Directivas de acceso condicional de dispositivos, Exchange Online y SharePoint Online**
 
>[!Note]
>Contoso también configuró directivas de acceso condicional adicionales para la identidad y el inicio de sesión. Vea [Identidad para Contoso Corporation](contoso-identity.md).
>

Estas directivas garantizan que:

- Las directivas de protección de aplicaciones definen qué aplicaciones se permiten y las acciones que se pueden realizar con los datos de la organización.
- Los equipos y dispositivos móviles deben ser compatibles.
- Exchange Online usa el cifrado de mensajes de Office 365 para Exchange Online.
- SharePoint Online usa las restricciones que exige la aplicación.
- SharePoint Online usa directivas de control de acceso para el acceso de solo explorador y para bloquear el de los dispositivos no administrados.

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a>Asignación de características de Microsoft 365 Enterprise a los niveles de datos de Contoso

En la tabla siguiente se muestra la asignación de los niveles de datos de Contoso a las características de protección de la información de Microsoft 365 Enterprise.

|||||
|:-------|:-----|:-----|:-----|
| | **Office 365** | **Windows 10 y Office 365 ProPlus** | **EMS** |
| Nivel 1: Base de referencia  | Directivas de acceso condicional de SharePoint Online y Exchange Online <BR> Permisos en sitios de SharePoint Online | Cliente de Azure Information Protection <BR> BitLocker <BR> Windows Information Protection | Directivas de acceso condicional de dispositivo y directivas de administración de aplicaciones móviles |
| Nivel 2: Altamente confidencial | Nivel 1: Base de referencia más: <BR> <BR> Etiquetas de Azure Information Protection <BR> Etiquetas de Office 365 en sitios de SharePoint Online <BR> Prevención de pérdida de datos de Office 365 para SharePoint Online y Exchange Online <BR> Sitios de SharePoint Online aislados  | Nivel 1: Base de referencia más: <BR> <BR> Etiquetas y activos digitales de Azure Information Protection <BR> Gobierno de datos avanzado de Office 365 | Nivel 1: Base de referencia |
| Nivel 3: Altamente regulado | Nivel 2: Altamente confidencial más: <BR><BR> Cifrado y protección Bring Your Own Key (BYOK) de la información de secretos empresariales <BR> Azure Key Vault para las aplicaciones de línea de negocio que interactúan con los servicios de Office 365 | Nivel 2: Altamente confidencial | Nivel 1: Base de referencia |
|||||


## <a name="next-step"></a>Paso siguiente

[Vea](contoso-security-summary.md) cómo Contoso ha usado las características de seguridad de Microsoft 365 Enterprise para la administración de la identidad, el acceso y la seguridad, la protección contra amenazas y la protección de la información.

## <a name="see-also"></a>Vea también

[Protección de la información para Microsoft 365 Enterprise](infoprotect-infrastructure.md)

[Guía de implementación](deploy-microsoft-365-enterprise.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)


