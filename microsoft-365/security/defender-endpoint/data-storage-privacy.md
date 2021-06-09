---
title: Privacidad y almacenamiento de datos de Microsoft Defender para endpoint
description: Obtenga información sobre cómo Microsoft Defender para endpoint controla la privacidad y los datos que recopila.
keywords: Microsoft Defender para endpoint, almacenamiento de datos y privacidad, almacenamiento, privacidad, licencias, geolocalización, retención de datos, datos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0258b2cdbff4a8b20be42e508863985c7402f609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845515"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Privacidad y almacenamiento de datos de Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

En esta sección se tratan algunas de las preguntas más frecuentes sobre privacidad y tratamiento de datos para Defender for Endpoint.
> [!NOTE]
> En este documento se explican los detalles de privacidad y almacenamiento de datos relacionados con Defender for Endpoint. Para obtener más información relacionada con Defender para Endpoint y otros productos y servicios como Antivirus de Microsoft Defender y Windows 10, vea [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=827576). Consulta también [Windows 10 preguntas más frecuentes sobre privacidad](https://go.microsoft.com/fwlink/?linkid=827577) para obtener más información.


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>¿Qué datos recopila Microsoft Defender para Endpoint?

Microsoft Defender para endpoint recopilará y almacenará información de los dispositivos configurados en un inquilino dedicado y segregado del cliente específico para el servicio con fines de administración, seguimiento e informes. 

La información recopilada incluye datos de archivos (como nombres de archivo, tamaños y hashes), datos de proceso (procesos en ejecución, hashes), datos del Registro, datos de conexión de red (puertos y DIRECCIONES IP de host) y detalles del dispositivo (como identificadores de dispositivo, nombres y la versión del sistema operativo).

Microsoft almacena estos datos de forma segura en Microsoft Azure y los mantiene de acuerdo con las prácticas de privacidad de Microsoft y las directivas [del Centro de confianza de Microsoft](https://go.microsoft.com/fwlink/?linkid=827578).

Estos datos permiten a Defender for Endpoint:
- Identificar proactivamente los indicadores de ataque (IOA) en su organización
- Generar alertas si se detectó un posible ataque
- Proporcione a sus operaciones de seguridad una vista de dispositivos, archivos y direcciones URL relacionadas con las señales de amenaza de la red, lo que le permite investigar y explorar la presencia de amenazas de seguridad en la red.

Microsoft no usa los datos para la publicidad.

## <a name="data-protection-and-encryption"></a>Protección y cifrado de datos
El servicio Defender for Endpoint usa tecnologías de protección de datos de última generación que se basan en Microsoft Azure infraestructura. 

Hay varios aspectos relevantes para la protección de datos que nuestro servicio se encarga de. El cifrado es uno de los más críticos e incluye cifrado de datos en reposo, cifrado en vuelo y administración de claves con Key Vault. Para obtener más información sobre otras tecnologías usadas por el servicio Defender for Endpoint, vea [Introducción al cifrado de Azure](/azure/security/security-azure-encryption-overview). 

En todos los escenarios, los datos se cifran con cifrado [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) de 256 bits como mínimo.


## <a name="data-storage-location"></a>Ubicación del almacenamiento de datos

Defender for Endpoint funciona en los centros Microsoft Azure de datos de la Unión Europea, reino unido o Estados Unidos. Los datos de cliente recopilados por el servicio pueden almacenarse en: (a) la ubicación geográfica del inquilino identificada durante el aprovisionamiento o, (b) si Defender para endpoint usa otro servicio en línea de Microsoft para procesar dichos datos, la geolocalización definida por las reglas de almacenamiento de datos de ese otro servicio en línea.

Los datos de los clientes con seudónimo también pueden almacenarse en los sistemas centrales de almacenamiento y procesamiento en los Estados Unidos.

Una vez configurado, no se puede cambiar la ubicación donde se almacenan los datos. Esto proporciona una forma cómoda de minimizar el riesgo de cumplimiento seleccionando activamente las ubicaciones geográficas donde residirán los datos. 

## <a name="is-my-data-isolated-from-other-customer-data"></a>¿Mis datos están aislados de otros datos de clientes?
Sí, los datos se aíslan mediante la autenticación de acceso y la segregación lógica basada en el identificador del cliente. Cada cliente solo puede acceder a los datos recopilados de su propia organización y a los datos genéricos que Proporciona Microsoft.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>¿Cómo evita Microsoft actividades de insider malintencionadas y el uso indebido de roles de privilegios altos?

Los desarrolladores y administradores de Microsoft tienen, por diseño, privilegios suficientes para llevar a cabo sus tareas asignadas para operar y desarrollar el servicio. Microsoft implementa combinaciones de controles preventivos, de detective y reactivos, incluidos los siguientes mecanismos para ayudar a proteger contra desarrolladores no autorizados o actividades administrativas:

- Control de acceso estrecho a datos confidenciales
- Combinaciones de controles que mejoran en gran medida la detección independiente de actividad malintencionada
- Varios niveles de supervisión, registro e informes

Además, Microsoft lleva a cabo comprobaciones de comprobación en segundo plano de cierto personal de operaciones y limita el acceso a aplicaciones, sistemas e infraestructura de red en proporción al nivel de verificación en segundo plano. El personal de operaciones sigue un proceso formal cuando se les exige tener acceso a la cuenta de un cliente o a la información relacionada en el rendimiento de sus funciones.

El acceso a los datos de los servicios implementados en centros de datos de gobierno de Microsoft Azure solo se concede al personal operativo que ha sido sometido a una pantalla y a una aprobación para controlar los datos que están sujetos a determinadas normativas y requisitos gubernamentales, como FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4 y CJIS.


## <a name="is-data-shared-with-other-customers"></a>¿Los datos se comparten con otros clientes?
No. Los datos del cliente están aislados de otros clientes y no se comparten. Sin embargo, es posible que se compartan con otros clientes información sobre los datos resultantes del procesamiento de Microsoft y que no contienen datos específicos del cliente. Cada cliente solo puede acceder a los datos recopilados de su propia organización y a los datos genéricos que Proporciona Microsoft.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>¿Cuánto tiempo almacenará Microsoft mis datos? ¿Qué es la directiva de retención de datos de Microsoft?
**En la incorporación de servicios**<br>
De forma predeterminada, los datos se conservan durante 180 días; sin embargo, puede especificar la directiva de retención de datos para los datos. Esto determina el tiempo que Window Defender para Endpoint almacenará los datos. Hay una flexibilidad de elegir entre un mes y seis meses para satisfacer las necesidades de cumplimiento normativo de su empresa.

**Al finalizar o expirar el contrato**<br>
Los datos se conservarán y estarán disponibles mientras la licencia esté en período de gracia o en modo suspendido. Al final de este período, esos datos se borrarán de los sistemas de Microsoft para que sean irrecuperables, como máximo 180 días después de la finalización o expiración del contrato.

**Datos de búsqueda avanzada**<br>
La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar.


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>¿Puede Microsoft ayudarnos a mantener el cumplimiento normativo?

Microsoft proporciona a los clientes información detallada sobre los programas de seguridad y cumplimiento de Microsoft, incluidos los informes de auditoría y los paquetes de cumplimiento, para ayudar a los clientes a evaluar los servicios de Defender for Endpoint con sus propios requisitos legales y normativos. Defender for Endpoint ha logrado varias certificaciones, incluidas ISO, SOC, FedRAMP High y PCI, y sigue buscando certificaciones adicionales nacionales, regionales y específicas del sector.

Al proporcionar a los clientes servicios compatibles y comprobados independientemente, Microsoft facilita a los clientes el cumplimiento de la infraestructura y las aplicaciones que ejecutan.

Para obtener más información sobre los informes de certificación de Defender for Endpoint, vea [Centro de confianza de Microsoft](https://servicetrust.microsoft.com/). 

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
