---
title: Protección de la información en Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo contoso usa las características de protección de la información de Microsoft 365 para empresas para proteger sus activos digitales en la nube.
ms.openlocfilehash: 51740db9a0bb2e770e959fe8d9dcde15c042f5b8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637240"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Protección de la información en Contoso Corporation

Contoso tiene serios sobre la seguridad de la información. La filtración o destrucción de la propiedad intelectual que describe sus diseños de productos y las técnicas de fabricación propietarias los colocarían en una desventaja competitiva.

Antes de migrar sus activos digitales confidenciales a la nube, contoso se asegura de que los requisitos de protección y clasificación de la información local se hayan admitido en los servicios basados en la nube de Microsoft 365 para empresas.

## <a name="contoso-data-security-classification"></a>Clasificación de seguridad de datos de Contoso

Contoso realizó un análisis de sus datos y determinó los siguientes niveles de clasificación.

| Nivel 1: Base de referencia | Nivel 2: Confidencial | Nivel 3: Altamente regulado |
|:-------|:-----|:-----|
| Los datos están cifrados y solo están disponibles para los usuarios autenticados.<BR> <BR> Se proporciona para todos los datos almacenados de forma local y en las cargas de trabajo y el almacenamiento basado en la nube. Los datos se cifran mientras residen en el servicio y en tránsito entre el servicio y los dispositivos de cliente. <BR><BR>Algunos ejemplos de datos de nivel 1 son las comunicaciones empresariales normales (correo electrónico) y los archivos de empleados administrativos, de ventas y de soporte técnico. | Nivel 1 más autenticación segura y protección contra la pérdida de datos.<BR> <BR> La autenticación segura incluye la Azure Multi-Factor Authentication con validación de SMS. La prevención de pérdida de datos garantiza que la información confidencial o importante no viaja fuera de la nube de Microsoft.<BR><BR>Algunos ejemplos de datos de nivel 2 son la información jurídica y financiera, y los datos de investigación y desarrollo de productos nuevos. | Características del nivel 2 además de los niveles más altos de cifrado, autenticación y auditoría.<BR><BR>Los niveles más altos de cifrado de datos en reposo y en la nube, conformes con la normativa regional, combinados con MFA con tarjetas inteligentes y alertas y auditoría pormenorizada.<BR> <BR>Algunos ejemplos de datos de nivel 3 son la información personal de clientes y Partners, las especificaciones de ingeniería de productos y las técnicas de fabricación propietarias.  |
||||

## <a name="contoso-information-policies"></a>Directivas de información de Contoso
En la siguiente tabla se enumeran las directivas de información de contoso.


| Valor | Access | Retención de datos | Protección de la información |
|:-------|:-----|:-----|:-----|
| Valor empresarial bajo (Nivel 1: Básico) | Permitir el acceso a todo.  | 6 meses | Se usa el cifrado. |
| Valor empresarial medio (Nivel 2: Confidencial) | Permitir el acceso a los empleados, subcontratistas y socios de contoso. <BR><BR> Se usa MFA, seguridad de la capa de transporte (TLS) y administración de aplicaciones móviles (MAM). | 2 años  | Se usan valores de hash para la integridad de datos.  |
| Valor empresarial alto (Nivel 3: Altamente regulado) | Se permite el acceso a ejecutivos y clientes potenciales de ingeniería y producción. <BR> <BR> Rights Management System (RMS) solo con dispositivos de red administrados.  | 7 años  | Se usan firmas digitales para evitar el rechazo.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Ruta de acceso de Contoso a la protección de la información con Microsoft 365 para empresas

Contoso siguió estos pasos para preparar a Microsoft 365 para empresas para sus requisitos de protección de la información:

1. Identificación de la información que se va a proteger

   Contoso realizó una revisión exhaustiva de sus activos digitales existentes ubicados en los sitios de SharePoint locales y los recursos compartidos de archivos, y clasificó cada activo.

2. Determinar las directivas de acceso, retención y protección de la información para los niveles de datos

   En función de los niveles de datos, Contoso determinó requisitos de directiva detallados que se usaron para proteger los activos digitales al cambiarlos a la nube.

3. Crear etiquetas de confidencialidad y su configuración para los distintos niveles de información

   Contoso creó etiquetas de confidencialidad para sus niveles de datos con una etiqueta altamente regulada que incluye cifrado, permisos y marcas de agua.

4.  Mover los datos de los sitios de SharePoint locales y los recursos compartidos de archivos a sus nuevos sitios de SharePoint

    Los archivos que se han migrado a los nuevos sitios de SharePoint heredaron las etiquetas de retención predeterminadas asignadas al sitio.

5.  Entrenar a los empleados sobre cómo usar las etiquetas de confidencialidad para nuevos documentos, cómo interactuar con contoso al crear nuevos sitios de SharePoint y almacenar siempre activos digitales en los sitios de SharePoint

    Cambio de la información de trabajo incorrecta: a menudo, los hábitos de almacenamiento se consideran la parte más difícil de la transición de protección de la información para la nube. Contoso ti y la administración necesarias para conseguir que los empleados siempre etiqueten y almacenen sus activos digitales en la nube, abstenerse de usar recursos compartidos de archivos locales y no usen servicios de almacenamiento en la nube de terceros o unidades USB.

## <a name="conditional-access-policies-for-information-protection"></a>Directivas de acceso condicional para la protección de la información

Como parte de su implementación de Exchange Online y SharePoint, contoso ha configurado el siguiente conjunto de directivas de acceso condicional y los ha aplicado a los grupos adecuados:

- [Directivas de acceso a aplicaciones administradas y no administradas en dispositivos](../security/office-365-security/identity-access-policies.md)
- [Directivas de acceso de Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)
- [Directivas de acceso a SharePoint](../security/office-365-security/sharepoint-file-access-policies.md)

Este es el conjunto resultante de directivas de Contoso para la protección de la información.

![Directivas de acceso condicional de SharePoint, Exchange Online y dispositivo](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso también configuró directivas de acceso condicional adicionales para identidad e inicio de sesión. Vea [Identidad para Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Estas directivas garantizan que:

- Las aplicaciones que están permitidas y las acciones que pueden llevar a cabo con los datos de la organización se definen mediante directivas de protección de aplicaciones.
- Los equipos y dispositivos móviles deben ser compatibles.
- Exchange online usa el cifrado de mensajes de Office 365 (OME) para Exchange Online.
- SharePoint usa restricciones aplicadas por aplicación.
- SharePoint usa directivas de control de acceso para el acceso de solo explorador y para bloquear el de los dispositivos no administrados.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Asignación de Microsoft 365 para las características de Enterprise a los niveles de datos de Contoso

En la siguiente tabla se asignan los niveles de datos de Contoso a las características de protección de la información de Microsoft 365 para empresas.

| Nivel | Servicios en la nube de Microsoft 365 | Aplicaciones de Microsoft 365 para empresas y Windows 10 | Seguridad y cumplimiento |
|:-------|:-----|:-----|:-----|
| Nivel 1: Base de referencia  | Directivas de acceso condicional de SharePoint y Exchange Online <BR> Permisos en los sitios de SharePoint | Etiquetas de confidencialidad <BR> BitLocker <BR> Windows Information Protection | Directivas de acceso condicional de dispositivos y directivas de administración de aplicaciones móviles |
| Nivel 2: Confidencial | Nivel 1 más: <BR> <BR> Etiquetas de confidencialidad <BR> Las etiquetas de retención de Microsoft 365 en los sitios de SharePoint <BR> Prevención de pérdida de datos para SharePoint y Exchange Online <BR> Sitios de SharePoint aislados  | Nivel 1 más: <BR> <BR> Etiquetas de confidencialidad en activos digitales  | Nivel 1 |
| Nivel 3: Altamente regulado | Nivel 2 más: <BR><BR> Proporcionar su propio cifrado y protección de clave (BYOK) para la información secreta comercial <BR> Azure Key Vault para aplicaciones de línea de negocio que interactúan con los servicios de Microsoft 365 | Nivel 2 | Nivel 1 |
|||||

Esta es la configuración resultante de la protección de la información de contoso.

![Configuración de protección de información resultante de Contoso](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Paso siguiente

[Vea](contoso-security-summary.md) cómo contoso usa las características de seguridad de Microsoft 365 para empresas para la administración de identidad y acceso, la protección contra amenazas, la protección de la información y la administración de la seguridad.

## <a name="see-also"></a>Recursos adicionales

[Plan de seguridad](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Información general de Microsoft 365 para empresas](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
