---
title: 'Paso 2: Configurar la clasificación para el entorno'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure varias formas de clasificar los datos de su organización.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871357"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Paso 2: Configurar la clasificación para el entorno

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

En este paso, trabajará con los equipos legales y de cumplimiento para definir un esquema de clasificación para los datos de su organización.

## <a name="microsoft-classifications"></a>Clasificaciones de Microsoft

Microsoft 365 incluye tres tipos de clasificación:

- Tipos de información confidencial de Office 365
- Etiquetas de Office 365
- Etiquetas y protección de Azure Information Protection

### <a name="sensitive-information-types-for-office-365"></a>Tipos de información confidencial de Office 365

Los tipos de información confidencial de Office 365 definen cómo los procesos automatizados (por ejemplo, la búsqueda) reconocen tipos de información específicos (por ejemplo, los números de servicios de salud y de tarjetas de crédito). Los tipos de información confidencial se usan para buscar información confidencial y aplicar reglas y directivas de prevención de pérdida de datos para proteger estos datos. Para obtener más información, vea [Información general sobre directivas de prevención de pérdida de datos](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Por ejemplo, los tipos de información confidencial son especialmente útiles para cumplir los requisitos de cumplimiento y normativas, por ejemplo, para el Reglamento general de protección de datos (RGPD).

### <a name="office-365-labels"></a>Etiquetas de Office 365
Puede usar etiquetas de Office 365 para datos personales y para archivos de secretos empresariales muy regulados almacenados en SharePoint Online y OneDrive para la Empresa. Para obtener más información, incluido cómo crearlas, vea [Información general de etiquetas](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).

Si decide usar etiquetas de Office 365, debe configurar al menos una para cada nivel de protección. Por ejemplo, cree tres etiquetas para:

- Línea base
- Confidencial
- Extremadamente regulado

### <a name="azure-information-protection-labels-and-protection"></a>Etiquetas y protección de Azure Information Protection

Puede usar etiquetas de Azure Information Protection para clasificar y, opcionalmente, proteger correos electrónicos y documentos de su organización. Estas etiquetas se pueden aplicar a documentos almacenados fuera de Office 365. Los administradores que definen reglas y condiciones pueden aplicar automáticamente estas etiquetas, los usuarios las pueden aplicar manualmente o se puede usar una combinación donde los usuarios reciben recomendaciones.

Para planear e implementar etiquetas y protección de Azure Information Protection, siga este procedimiento:

1. Revise los [requisitos de Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Siga el [mapa de ruta de implementación para clasificación, etiquetado y protección](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Para obtener más información, vea la [biblioteca de documentación de Azure Information Protection](https://docs.microsoft.com/information-protection/).

## <a name="classification-for-gdpr"></a>Clasificación para el RGPD

Para obtener un esquema de clasificación de ejemplo que incluye datos personales para el RGPD, consulte [Diseño de un esquema de clasificación de datos personales](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía del entorno de pruebas: clasificación de datos](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondientes a este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Configurar una mayor seguridad para Office 365](infoprotect-configure-increased-security-office-365.md)|

