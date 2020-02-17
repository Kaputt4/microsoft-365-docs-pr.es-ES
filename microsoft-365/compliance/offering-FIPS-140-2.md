---
title: Publicación del estándar federal de procesamiento de información (FIPS) 140-2
description: Microsoft certifica que sus módulos criptográficos cumplen con el estándar federal de procesamiento de información estadounidense.
keywords: Microsoft 365, cumplimiento, ofertas
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 1a1e8b19ff214d29dc8a309cce4f79de92cf8155
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071297"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a>Publicación del estándar federal de procesamiento de información (FIPS) 140-2

## <a name="fips-140-2-standard-overview"></a>Información general sobre FIPS 140-2 estándar

La publicación del estándar federal de procesamiento de información (FIPS) 140-2 es un estándar del gobierno de Estados Unidos que define los requisitos mínimos de seguridad para los módulos criptográficos de los productos de tecnología de la información, tal como se define en la sección 5131 de la información Ley de reforma de la administración tecnológica de 1996.

El [programa de validación de módulos criptográficos](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (CMVP), un esfuerzo conjunto del Instituto Nacional de normas y tecnología de los Estados Unidos (NIST) y el centro canadiense para la seguridad del ciberespacio (CCCS), valida los módulos criptográficos *según los requisitos de seguridad para los módulos criptográficos* estándar (por ejemplo, FIPS 140-2) y los estándares de criptografía FIPS relacionados. Los requisitos de seguridad de FIPS 140-2 cubren 11 áreas relacionadas con el diseño y la implementación de un módulo criptográfico. El laboratorio de información de NIST opera un programa relacionado que valida los algoritmos criptográficos aprobados por FIPS en el módulo.

## <a name="microsofts-approach-to-fips-140-2-validation"></a>Enfoque de Microsoft para la validación de FIPS 140-2

Microsoft mantiene un compromiso activo para cumplir los requisitos de 140-2, con módulos criptográficos validados desde el principio del estándar de 2001. Microsoft valida sus módulos criptográficos en el [programa de validación de módulo criptográfico](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) del Instituto Nacional de normas y tecnología (NIST) (CMVP). Varios productos de Microsoft, incluidos muchos servicios en la nube, usan estos módulos criptográficos.

Para obtener información técnica sobre los módulos criptográficos de Microsoft Windows, la Directiva de seguridad de cada módulo y el catálogo de los detalles del certificado CMVP, consulte el [contenido de Windows y Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

## <a name="microsoft-in-scope-cloud-services"></a>En el ámbito de los Servicios en la nube de Microsoft 

Mientras que la guía de implementación de CMVP FIPS 140-2 actual excluye una validación de FIPS 140-2 para un servicio en la nube; los proveedores de servicios de nube pueden elegir obtener y operar módulos criptográficos de FIPS 140 validados para los elementos informáticos que componen su servicio en la nube. Los servicios en línea de Microsoft que incluyen componentes, que se han validado por FIPS 140-2, entre otros:

- [Azure y Azure Government](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [Dynamics 365 y Dynamics 365 Government](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [Office 365, Office 365 Administración Pública para Estados Unidos y Office 365 U.S. Government Defense](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Cuál es la diferencia entre "FIPS 140 validado" y "compatible con FIPS 140"?**

"FIPS 140 validado" significa que el módulo de cifrado o un producto que incrusta el módulo ha sido validado ("certificado") por el CMVP como cumple los requisitos de FIPS 140-2. "Compatible con FIPS 140" es un término de la industria para los productos de ti que dependen de los productos validados FIPS 140 para la funcionalidad criptográfica.

**¿Cuándo emprende Microsoft una validación de FIPS 140?**

La cadencia para iniciar una validación de módulo se alinea con las actualizaciones de características de Windows 10 y Windows Server. A medida que la industria del software evolucionó, los sistemas operativos se publican con más frecuencia con las actualizaciones de software mensuales. Microsoft se ocupa de la validación de las versiones de características, pero entre versiones, busca minimizar los cambios en los módulos criptográficos.

**¿Qué equipos se incluyen en una validación de FIPS 140?**

Microsoft valida los módulos criptográficos en una muestra representativa de configuraciones de hardware que ejecutan Windows 10 y Windows Server. La práctica común de la industria es aceptar esta validación de FIPS 140-2 cuando un entorno usa hardware, que es similar a los ejemplos que se usan para el proceso de validación.

**Hay muchos módulos que se enumeran en el sitio web NIST. ¿Cómo sé cuál de ellos se aplica a mi agencia?**

Si necesita usar módulos criptográficos validados mediante FIPS 140-2, debe comprobar que la versión que usa aparece en la lista de validación. CMVP y Microsoft mantienen una lista de los módulos criptográficos validados, organizados por versión del producto, junto con instrucciones para identificar los módulos que se instalan en un sistema Windows. Para obtener más información sobre cómo configurar los sistemas para que sean compatibles, consulte el [contenido de Windows y Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

**¿Qué significa "cuando funciona en modo FIPS" en un certificado?**

Esta advertencia informa al lector de que es necesario seguir las reglas de configuración y seguridad necesarias para usar el módulo criptográfico de forma coherente con la Directiva de seguridad FIPS 140-2. Cada módulo tiene su propia Directiva de seguridad (una especificación precisa de las reglas de seguridad en las que operará) y emplea algoritmos de cifrado aprobados, administración de claves de cifrado y técnicas de autenticación. Las reglas de seguridad se definen en la Directiva de seguridad de cada módulo. Para obtener más información, incluidos vínculos a la Directiva de seguridad para cada módulo validado a través de CMVP, consulte el [contenido de Windows y Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

**¿FedRAMP requiere la validación de FIPS 140-2?**

Sí, el programa de administración de riesgos y autorización Federal (FedRAMP) se basa en las líneas base de control definidas por [NIST SP 800-53 revisión 4](https://nvd.nist.gov/800-53/Rev4/), incluida la [protección criptográfica SC-13](https://nvd.nist.gov/800-53/Rev4/control/SC-13) , que exige el uso de criptografía validada por FIPS o criptografía aprobada por NSA.

**¿Cómo admite Microsoft Azure FIPS 140-2?**

Azure se ha creado con una combinación de hardware, sistemas operativos (Linux y Windows) disponibles en el mercado y la versión específica de Windows de Azure. A través del [ciclo de vida de desarrollo de seguridad](https://www.microsoft.com/securityengineering/sdl/) de Microsoft (SDL), todos los servicios de Azure usan algoritmos aprobados de FIPS 140-2 para la seguridad de datos, ya que el sistema operativo usa algoritmos aprobados de FIPS 140-2 mientras operan en una nube de Hyper-Scale.

**¿Puedo usar el cumplimiento de Microsoft para FIPS 140-2 en el proceso de certificación de mi agencia?**

Para cumplir con FIPS 140-2, el sistema debe estar configurado para ejecutarse en un modo de funcionamiento aprobado por FIPS, que incluye garantizar que un módulo criptográfico use solo algoritmos aprobados por FIPS. Para obtener más información sobre cómo configurar los sistemas para que sean compatibles, consulte el [contenido de Windows y Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

**¿Cuál es la relación entre FIPS 140-2 y Common Criteria?**

Se trata de dos estándares de seguridad independientes con fines distintos, pero complementarios. FIPS 140-2 está diseñado específicamente para validar módulos criptográficos de software y hardware, mientras que los criterios comunes están diseñados para evaluar las funciones de seguridad de los productos de hardware y software de ti. Las evaluaciones de criterios comunes suelen basarse en validaciones de FIPS 140-2 para proporcionar seguridad de que la funcionalidad criptográfica básica se ha implementado correctamente.

## <a name="resources"></a>Recursos

- [Requisitos de seguridad de FIPS PUB 140-2 para módulos criptográficos](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [Programa de validación de módulo criptográfico NIST](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [Windows, Windows Server y FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [Cumplimiento normativo en el Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Descargar el documento de información general de la oferta

¿Necesita el documento de información general de esta oferta? Descargue el [PDF](https://download.microsoft.com/download/B/7/2/B7226B91-1A56-41E4-AC01-43FCFEE50B7F/FIPS_Compliance_Backgrounder.pdf).
