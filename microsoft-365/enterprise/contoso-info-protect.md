---
title: Protección de la información en Contoso Corporation
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo Contoso usa las características de protección de la información de Microsoft 365 para empresas para proteger sus recursos digitales en la nube.
ms.openlocfilehash: 29c31138a11966510a393dafbe2f5a3741b78f5b
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851444"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Protección de la información en Contoso Corporation

Contoso es serio sobre su seguridad de la información. La pérdida o destrucción de la propiedad intelectual que describe sus diseños de productos y técnicas de fabricación propias los colocaría en una desventaja competitiva.

Antes de trasladar sus recursos digitales confidenciales a la nube, Contoso se aseguró de que los servicios basados en la nube de Microsoft 365 para empresas admitían sus requisitos de protección y clasificación de información local.

## <a name="contoso-data-security-classification"></a>Clasificación de seguridad de datos de Contoso

Contoso realizó un análisis de sus datos y determinó los siguientes niveles de clasificación.

| Nivel 1: Base de referencia | Nivel 2: Confidencial | Nivel 3: Altamente regulado |
|:-------|:-----|:-----|
| Los datos están cifrados y solo están disponibles para los usuarios autenticados.<BR> <BR> Se proporciona para todos los datos almacenados en el entorno local y en cargas de trabajo y almacenamiento basados en la nube. Los datos se encriptan mientras residen en el servicio y en tránsito entre el servicio y los dispositivos de cliente. <BR><BR>Algunos ejemplos de datos de nivel 1 son las comunicaciones empresariales normales (correo electrónico) y los archivos de empleados administrativos, de ventas y de soporte técnico. | Nivel 1 más autenticación segura y protección contra la pérdida de datos.<BR> <BR> La autenticación segura incluye Azure AD Multi-Factor Authentication (MFA) con validación de SMS. Prevención de pérdida de datos de Microsoft Purview garantiza que la información confidencial o crítica no viaje fuera de la nube de Microsoft.<BR><BR>Algunos ejemplos de datos de nivel 2 son la información jurídica y financiera, y los datos de investigación y desarrollo de productos nuevos. | Características del nivel 2 además de los niveles más altos de cifrado, autenticación y auditoría.<BR><BR>Los niveles más altos de cifrado de datos en reposo y en la nube, conformes con la normativa regional, combinados con MFA con tarjetas inteligentes y alertas y auditoría pormenorizada.<BR> <BR>Algunos ejemplos de datos de nivel 3 son la información personal del cliente y del asociado, las especificaciones de ingeniería de productos y las técnicas de fabricación propietarias.  |
||||

## <a name="contoso-information-policies"></a>Directivas de información de Contoso
En la tabla siguiente se enumeran las directivas de información de Contoso.


| Valor | Acceso | Retención de datos | Protección de la información |
|:-------|:-----|:-----|:-----|
| Valor empresarial bajo (Nivel 1: Básico) | Permitir el acceso a todos.  | 6 meses | Se usa el cifrado. |
| Valor empresarial medio (Nivel 2: Confidencial) | Permitir el acceso a los empleados, subcontratistas y asociados de Contoso. <BR><BR> Se usa MFA, seguridad de la capa de transporte (TLS) y administración de aplicaciones móviles (MAM). | 2 años  | Se usan valores de hash para la integridad de datos.  |
| Valor empresarial alto (Nivel 3: Altamente regulado) | Se permite el acceso a ejecutivos y clientes potenciales de ingeniería y producción. <BR> <BR> Rights Management System (RMS) solo con dispositivos de red administrados.  | 7 años  | Se usan firmas digitales para evitar el rechazo.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Ruta de acceso de Contoso a la protección de la información con Microsoft 365 para empresas

Contoso ha seguido estos pasos para preparar Microsoft 365 para empresas para sus requisitos de protección de la información:

1. Identificación de la información que se va a proteger

   Contoso realizó una amplia revisión de sus recursos digitales existentes ubicados en sitios locales de SharePoint y recursos compartidos de archivos y clasificó cada recurso.

2. Determinar las directivas de acceso, retención y protección de la información para los niveles de datos

   En función de los niveles de datos, Contoso determinó requisitos de directiva detallados que se usaron para proteger los activos digitales al cambiarlos a la nube.

3. Crear etiquetas de confidencialidad y su configuración para los distintos niveles de información

   Contoso creó etiquetas de confidencialidad para sus niveles de datos con una etiqueta altamente regulada que incluye cifrado, permisos y marcas de agua.

4. Traslado de datos de sitios y recursos compartidos de archivos locales de SharePoint a sus nuevos sitios de SharePoint

    Los archivos que se han migrado a los nuevos sitios de SharePoint heredaron las etiquetas de retención predeterminadas asignadas al sitio.

5. Entrenamiento de empleados sobre cómo usar etiquetas de confidencialidad para nuevos documentos, cómo interactuar con TI de Contoso al crear nuevos sitios de SharePoint y almacenar siempre recursos digitales en sitios de SharePoint

    Cambiar los hábitos de almacenamiento de información de trabajo incorrecto a menudo se considera la parte más difícil de la transición de la protección de la información para la nube. El equipo de TI y la administración de Contoso necesitan para que los empleados etiqueten y almacenen siempre sus recursos digitales en la nube, no usen recursos compartidos de archivos locales y no usen servicios de almacenamiento en la nube o unidades USB de terceros.

## <a name="conditional-access-policies-for-information-protection"></a>Directivas de acceso condicional para la protección de la información

Como parte de su implementación de Exchange Online y SharePoint, Contoso configuró el siguiente conjunto de directivas de acceso condicional y las aplicó a los grupos adecuados:

- [Directivas de acceso a aplicaciones administradas y no administradas en dispositivos](../security/office-365-security/identity-access-policies.md)
- [Directivas de acceso de Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)
- [Directivas de acceso a SharePoint](../security/office-365-security/sharepoint-file-access-policies.md)

Este es el conjunto resultante de directivas de Contoso para la protección de la información.

:::image type="content" alt-text="Directivas de acceso condicional de Dispositivo, Exchange Online y SharePoint." source="../media/contoso-info-protect/contoso-info-protect-fig1.png" lightbox="../media/contoso-info-protect/contoso-info-protect-fig1.png":::

>[!Note]
>Contoso también configuró directivas de acceso condicional adicionales para identidad e inicio de sesión. Vea [Identidad para Contoso Corporation](contoso-identity.md#conditional-access-policies-for-zero-trust-identity-and-device-access).
>

Estas directivas garantizan que:

- Las aplicaciones permitidas y las acciones que pueden realizar con los datos de la organización se definen mediante directivas de protección de aplicaciones.
- Los equipos y dispositivos móviles deben ser compatibles.
- Exchange Online usa el cifrado de mensajes de Office 365 (OME) para Exchange Online.
- SharePoint usa restricciones aplicadas por la aplicación.
- SharePoint usa directivas de control de acceso para el acceso de solo explorador y para bloquear el de los dispositivos no administrados.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Asignación de Microsoft 365 para características empresariales a los niveles de datos de Contoso

En la tabla siguiente se asignan los niveles de datos de Contoso a las características de protección de la información de Microsoft 365 para empresas.

| Nivel | Servicios en la nube de Microsoft 365 | Aplicaciones de Microsoft 365 para empresas y Windows 10 | Seguridad y cumplimiento |
|:-------|:-----|:-----|:-----|
| Nivel 1: Base de referencia  | Directivas de acceso condicional de SharePoint y Exchange Online <BR> Permisos en los sitios de SharePoint | Etiquetas de confidencialidad <BR> BitLocker <BR> Windows Information Protection | Directivas de acceso condicional de dispositivos y directivas de administración de aplicaciones móviles |
| Nivel 2: Confidencial | Nivel 1 más: <BR> <BR> Etiquetas de confidencialidad <BR> Las etiquetas de retención de Microsoft 365 en los sitios de SharePoint <BR> Prevención de pérdida de datos para SharePoint y Exchange Online <BR> Sitios de SharePoint aislados  | Nivel 1 más: <BR> <BR> Etiquetas de confidencialidad en activos digitales  | Nivel 1 |
| Nivel 3: Altamente regulado | Nivel 2 más: <BR><BR> Cifrado y protección de su propia clave (BYOK) para la información de secretos comerciales <BR> Azure Key Vault para aplicaciones de línea de negocio que interactúan con servicios de Microsoft 365 | Nivel 2 | Nivel 1 |
|||||

Esta es la configuración de protección de la información de Contoso resultante.

:::image type="content" alt-text="Configuración de protección de la información resultante de Contoso." source="../media/contoso-info-protect/contoso-info-protect-fig2.png":::

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso usa las [características de seguridad de Microsoft 365 para empresas](contoso-security-summary.md) para la administración de identidades y acceso, la protección contra amenazas, la protección de la información y la administración de seguridad.

## <a name="see-also"></a>Vea también

[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/overview)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)