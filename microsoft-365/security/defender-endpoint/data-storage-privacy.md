---
title: Microsoft Defender para punto de conexión almacenamiento de datos y privacidad
description: Obtenga información sobre cómo Microsoft Defender para punto de conexión controla la privacidad y los datos que recopila.
keywords: Microsoft Defender para punto de conexión, almacenamiento y privacidad de datos, almacenamiento, privacidad, licencias, geolocalización, retención de datos, datos
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: d736a87b1596beff1c252c05d0b90526289ce230
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67699068"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Microsoft Defender para punto de conexión almacenamiento de datos y privacidad

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

En esta sección se tratan algunas de las preguntas más frecuentes sobre privacidad y control de datos para Defender para punto de conexión.

> [!NOTE]
> En este documento se explican los detalles de privacidad y almacenamiento de datos relacionados con Defender para punto de conexión. Para obtener más información relacionada con Defender para punto de conexión y otros productos y servicios como Antivirus de Microsoft Defender y Windows, consulte [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=827576). Consulta también [Preguntas más frecuentes sobre privacidad de Windows](https://go.microsoft.com/fwlink/?linkid=827577) para obtener más información.

## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>¿Qué datos recopila Microsoft Defender para punto de conexión?

Microsoft Defender para punto de conexión recopilará y almacenará información de los dispositivos configurados en un inquilino dedicado y segregado del cliente específico del servicio con fines de administración, seguimiento e informes.

La información recopilada incluye datos de archivo (como nombres de archivo, tamaños y hashes), datos de proceso (procesos en ejecución, hash), datos del Registro, datos de conexión de red (puertos y direcciones IP del host) y detalles del dispositivo (como identificadores de dispositivo, nombres y la versión del sistema operativo).

Microsoft almacena estos datos de forma segura en Microsoft Azure y los mantiene de acuerdo con las prácticas de privacidad de Microsoft y las [directivas del Centro de confianza de Microsoft](https://go.microsoft.com/fwlink/?linkid=827578).

Estos datos permiten que Defender para punto de conexión:

- Identificación proactiva de indicadores de ataque (E/SA) en la organización
- Generar alertas si se detectó un posible ataque
- Proporcione a las operaciones de seguridad una vista de dispositivos, archivos y direcciones URL relacionadas con las señales de amenazas de la red, lo que le permite investigar y explorar la presencia de amenazas de seguridad en la red.

Microsoft no usa sus datos para la publicidad.

## <a name="data-protection-and-encryption"></a>Cifrado y protección de datos

El servicio Defender para punto de conexión usa tecnologías de protección de datos de última generación que se basan en la infraestructura de Microsoft Azure.

Hay diversos aspectos relacionados con la protección de datos que nuestro servicio se encarga de. El cifrado es uno de los más críticos e incluye el cifrado de datos en reposo, el cifrado en vuelo y la administración de claves con Key Vault. Para obtener más información sobre otras tecnologías usadas por el servicio Defender para punto de conexión, consulte [Introducción al cifrado de Azure](/azure/security/security-azure-encryption-overview).

En todos los escenarios, los datos se cifran mediante [el cifrado AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) de 256 bits como mínimo.

## <a name="data-storage-location"></a>Ubicación del almacenamiento de datos

Defender para punto de conexión opera en los centros de datos de Microsoft Azure en la Unión Europea, el Reino Unido o en la Estados Unidos. Los datos del cliente recopilados por el servicio pueden almacenarse en: (a) la ubicación geográfica del inquilino tal como se identifica durante el aprovisionamiento o, (b) si Defender para punto de conexión usa otro servicio en línea de Microsoft para procesar dichos datos, la geolocalización definida por las reglas de almacenamiento de datos de ese otro servicio en línea.

Los datos del cliente en forma seudonimizada también se pueden almacenar en los sistemas centrales de almacenamiento y procesamiento en el Estados Unidos.

Una vez configurado, no se puede cambiar la ubicación donde se almacenan los datos. Esto proporciona una manera cómoda de minimizar el riesgo de cumplimiento seleccionando activamente las ubicaciones geográficas donde residirán los datos.

## <a name="is-my-data-isolated-from-other-customer-data"></a>¿Están mis datos aislados de otros datos del cliente?

Sí, los datos están aislados mediante la autenticación de acceso y la segregación lógica basada en el identificador de cliente. Cada cliente solo puede acceder a los datos recopilados de su propia organización y a los datos genéricos que proporciona Microsoft.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>¿Cómo evita Microsoft las actividades internas malintencionadas y el abuso de roles con privilegios elevados?

Los desarrolladores y administradores de Microsoft tienen, por diseño, privilegios suficientes para llevar a cabo sus tareas asignadas para operar y evolucionar el servicio. Microsoft implementa combinaciones de controles preventivos, detectives y reactivos, incluidos los siguientes mecanismos para ayudar a proteger contra la actividad administrativa o de desarrolladores no autorizados:

- Control de acceso estricto a datos confidenciales
- Combinaciones de controles que mejoran en gran medida la detección independiente de actividad malintencionada
- Varios niveles de supervisión, registro e informes

Además, Microsoft realiza comprobaciones en segundo plano de cierto personal de operaciones y limita el acceso a aplicaciones, sistemas e infraestructura de red en proporción al nivel de verificación en segundo plano. El personal de operaciones sigue un proceso formal cuando es necesario acceder a la cuenta de un cliente o a información relacionada en el cumplimiento de sus obligaciones.

El acceso a los datos de los servicios implementados en los centros de datos de Microsoft Azure Government solo se concede al personal operativo que ha sido evaluado y aprobado para controlar datos sujetos a ciertas regulaciones y requisitos gubernamentales, como FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4 y CJIS.

## <a name="is-data-shared-with-other-customers"></a>¿Se comparten datos con otros clientes?

No. Los datos del cliente están aislados de otros clientes y no se comparten. Sin embargo, la información sobre los datos resultantes del procesamiento de Microsoft, y que no contienen datos específicos del cliente, podría compartirse con otros clientes. Cada cliente solo puede acceder a los datos recopilados de su propia organización y a los datos genéricos que proporciona Microsoft.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>¿Cuánto tiempo almacenará Microsoft mis datos? ¿Qué es la directiva de retención de datos de Microsoft?

### <a name="at-service-onboarding"></a>Incorporación del servicio

De forma predeterminada, los datos se conservan durante 180 días; sin embargo, puede especificar la directiva de retención de datos para los datos. Esto determina cuánto tiempo Microsoft Defender para punto de conexión almacenarán los datos. Hay una flexibilidad de elegir entre un mes y seis meses para satisfacer las necesidades de cumplimiento normativo de su empresa.

### <a name="at-contract-termination-or-expiration"></a>Al finalizar o expirar el contrato

Sus datos se conservarán y estarán disponibles mientras la licencia esté en período de gracia o en modo suspendido. Al final de este período, esos datos se borrarán de los sistemas de Microsoft para que sean irrecuperables, a más tardar 180 días después de la finalización o expiración del contrato.

### <a name="advanced-hunting-data"></a>Datos de búsqueda avanzada

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar.

## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>¿Puede Microsoft ayudarnos a mantener el cumplimiento normativo?

Microsoft proporciona a los clientes información detallada sobre los programas de seguridad y cumplimiento de Microsoft, incluidos los informes de auditoría y los paquetes de cumplimiento, para ayudar a los clientes a evaluar los servicios de Defender para punto de conexión en función de sus propios requisitos legales y normativos. Defender for Endpoint ha logrado una serie de certificaciones, incluidas ISO, SOC, FedRAMP High y PCI, y continúa buscando certificaciones nacionales, regionales y específicas del sector adicionales.

Al proporcionar a los clientes servicios compatibles y comprobados de forma independiente, Microsoft facilita a los clientes el cumplimiento de la infraestructura y las aplicaciones que ejecutan.

Para obtener más información sobre los informes de certificación de Defender para punto de conexión, consulte [El Centro de confianza de Microsoft](https://servicetrust.microsoft.com/). 

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-datastorage-belowfoldlink)
