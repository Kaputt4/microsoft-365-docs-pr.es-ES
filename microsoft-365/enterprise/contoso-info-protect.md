---
title: Protección de la información en Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre cómo usa Contoso las características de protección de la información de Microsoft 365 Enterprise para proteger sus activos digitales en la nube.
ms.openlocfilehash: c11636d6fcdb1de634988e85238ce39a703d520d
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074080"
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
| Valor empresarial bajo (Nivel 1: Básico) | Se permite el acceso a todo el mundo  | 6 meses | Se usa cifrado |
| Valor empresarial medio (Nivel 2: Confidencial) | Se permite el acceso a subcontratistas, partners y empleados de Contoso <BR> <BR> Se usa la autenticación multifactor (MFA), Seguridad de la capa de transporte (TLS) y Administración de aplicaciones móviles (MAM) | 2 años  | Se usan valores de hash para la integridad de datos  |
| Valor empresarial alto (Nivel 3: Altamente regulado) | Se permite el acceso a ejecutivos y clientes potenciales de ingeniería y fabricación <BR> <BR> Rights Management System (RMS) solo con dispositivos de red administrados  | 7 años  | Se usan firmas digitales para evitar el rechazo  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a>Ruta de Contoso a la protección de la información con Microsoft 365 Enterprise

Contoso siguió los pasos siguientes para preparar Microsoft 365 Enterprise para sus requisitos de protección de la información:

1. Identificó qué información se iba a proteger.

   Contoso realizó una revisión exhaustiva de los activos digitales existentes en sitios locales de SharePoint y recursos compartidos de archivos, y los clasificó todos.

2. Determinó las directivas de acceso, retención y protección de la información para los niveles de datos.

   En función de los niveles de datos, Contoso determinó requisitos de directiva detallados que se usaron para proteger los activos digitales al cambiarlos a la nube.

3. Creó etiquetas de confidencialidad para los diferentes niveles de información.

   Contoso creó etiquetas de confidencialidad para sus niveles de datos, incorporando en las etiqueta Confidencial y Altamente regulado cifrado, permisos y marcas de agua.

4. Creó sitios de SharePoint Online protegidos para datos confidenciales y altamente regulados con permisos para bloquear el acceso.

   Los sitios confidenciales y altamente regulados se configuraron como [sitios aislados](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites), en los que los permisos de sitio de grupo de SharePoint Online predeterminados se personalizaron como grupos de Azure Active Directory (Azure AD). También se configuraron sitios confidenciales y altamente regulados en SharePoint Online con la etiqueta de retención correspondiente. Los archivos almacenados en los sitios de SharePoint Online altamente regulados están protegidos con la etiqueta de confidencialidad Altamente regulado. Para más información, consulte el escenario [Sitios de Microsoft Teams y SharePoint Online para datos altamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md)

5.  Se movieron los datos de los sitios de SharePoint locales y los recursos compartidos de archivos a los nuevos sitios de SharePoint Online.

    Los archivos que se migraron a los nuevos sitios de SharePoint Online heredaron las etiquetas de retención predeterminadas asignadas al sitio.

6.  Se formó a los empleados sobre cómo usar las etiquetas de confidencialidad para los documentos nuevos, cómo interactuar con el departamento de TI de Contoso al crear sitios de SharePoint Online y almacenar siempre los activos digitales en sitios de SharePoint Online.

    Asumiendo que era el aspecto más difícil de la transición a la nube de la protección de la información, los departamentos de TI y administración de Contoso tuvieron que cambiar los hábitos incorrectos de almacenamiento de la información por parte de los empleados de la organización para que etiquetaran y almacenaran siempre sus recursos digitales en la nube, absteniéndose de usar archivos compartidos locales, y nunca usaran servicios de almacenamiento en la nube de terceros o memorias USB.

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

- Las aplicaciones permitidas y las acciones que pueden realizar con los datos de la organización se definen mediante directivas de protección de aplicaciones.
- Los equipos y dispositivos móviles deben ser compatibles.
- Exchange Online usa el cifrado de mensajes de Office 365 para Exchange Online.
- SharePoint Online usa las restricciones que exige la aplicación.
- SharePoint Online usa directivas de control de acceso para el acceso de solo explorador y para bloquear el de los dispositivos no administrados.

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a>Asignación de características de Microsoft 365 Enterprise a los niveles de datos de Contoso

En la tabla siguiente se muestra la asignación de los niveles de datos de Contoso a las características de protección de la información de Microsoft 365 Enterprise.

|||||
|:-------|:-----|:-----|:-----|
| | **Office 365** | **Windows 10 y Office 365 ProPlus** | **EMS** |
| Nivel 1: Base de referencia  | Directivas de acceso condicional de SharePoint Online y Exchange Online <BR> Permisos en sitios de SharePoint Online | Etiquetas de confidencialidad <BR> BitLocker <BR> Windows Information Protection | Directivas de acceso condicional de dispositivo y directivas de administración de aplicaciones móviles |
| Nivel 2: Confidencial | Nivel 1 más: <BR> <BR> Etiquetas de confidencialidad <BR> Etiquetas de Office 365 en sitios de SharePoint Online <BR> Prevención de pérdida de datos de Office 365 para SharePoint Online y Exchange Online <BR> Sitios de SharePoint Online aislados  | Nivel 1 más: <BR> <BR> Etiquetas de confidencialidad en activos digitales <BR> Gobierno de datos avanzado de Office 365 | Nivel 1 |
| Nivel 3: Altamente regulado | Nivel 2 más: <BR><BR> Cifrado y protección Bring Your Own Key (BYOK) de la información de secretos empresariales <BR> Azure Key Vault para las aplicaciones de línea de negocio que interactúan con los servicios de Office 365 | Nivel 2 | Nivel 1 |
|||||


## <a name="next-step"></a>Paso siguiente

[Vea](contoso-security-summary.md) cómo Contoso ha usado las características de seguridad de Microsoft 365 Enterprise para la administración de la identidad, el acceso y la seguridad, la protección contra amenazas y la protección de la información.

## <a name="see-also"></a>Vea también

[Protección de la información para Microsoft 365 Enterprise](infoprotect-infrastructure.md)

[Guía de implementación](deploy-microsoft-365-enterprise.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)


