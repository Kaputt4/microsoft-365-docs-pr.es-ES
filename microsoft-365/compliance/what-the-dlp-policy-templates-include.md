---
title: Qué plantillas de directiva DLP incluyen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.DLPNewPolicyFromTemplate
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: Obtenga información sobre las plantillas de directiva de prevención de pérdida de datos (DLP) de la portal de cumplimiento Microsoft Purview incluyen.
ms.openlocfilehash: ab3d0f4fa131f32c1916df0c973a6b0dab3f1654
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633353"
---
# <a name="what-the-dlp-policy-templates-include"></a>Qué incluyen las plantillas de directiva DLP

Prevención de pérdida de datos de Microsoft Purview (DLP) en el portal de cumplimiento Microsoft Purview incluye plantillas de directivas listas para usar que abordan los requisitos de cumplimiento comunes, como ayudarle a proteger la información confidencial sujeta al seguro médico de EE. UU. Ley (HIPAA), Ley Gramm-Leach-Bliley (GLBA) o Ley Patriota de los Estados Unidos. En este artículo se enumeran todas las plantillas de directiva, qué tipos de información confidencial buscan y cuáles son las condiciones y acciones predeterminadas. En este artículo no se incluyen todos los detalles de cómo se configura cada plantilla de directiva; en su lugar, el artículo presenta suficiente información para ayudarle a decidir qué plantilla es el mejor punto de partida para su escenario. Recuerde que puede personalizar estas plantillas de directiva para satisfacer sus requisitos específicos.
  
## <a name="australia-financial-data"></a>Datos financieros de Australia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de archivo de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo 500  <br/>  Número de archivo de impuestos de Australia: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria de Australia: recuento mínimo 10, recuento máximo 500  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-health-records-act-hrip-act"></a>Ley de registros de salud de Australia (Ley HRIP)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|HRIP de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de archivo de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta médica de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|HRIP de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de archivo de impuestos de Australia: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta médica de Australia: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-personally-identifiable-information-pii-data"></a>Datos de identificación personal (PII) de Australia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de archivo de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de licencia de conducir de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de archivo de impuestos de Australia: recuento mínimo 10, recuento máximo 500  <br/>  Número de licencia de conducir de Australia: número mínimo 10, número máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-privacy-act"></a>Ley de privacidad de Australia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Privacidad de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de licencia de conducir de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Privacidad de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de licencia de conducir de Australia: número mínimo 10, número máximo 500  <br/>  Número de pasaporte de Australia: recuento mínimo 10, recuento máximo 500 <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-financial-data"></a>Datos financieros de Canadá

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Datos financieros de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-health-information-act-hia"></a>Ley de información sobre salud (HIA) de Canadá

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|HIA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|HIA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-health-act-phipa---ontario"></a>Ley sobre salud personal de Canadá (PHIPA) - Ontario

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PHIPA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PHIPA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-health-information-act-phia---manitoba"></a>Ley de información sobre salud personal de Canadá (PHIA) - Manitoba

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PHIA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PHIA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro social de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 10, recuento máximo 500 <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-information-protection-act-pipa"></a>Ley de protección de información personal de Canadá (PIPA)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PIPA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIPA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-information-protection-act-pipeda"></a>Ley de protección de información personal de Canadá (PIPEDA)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PIPEDA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de licencia de conducir de Canadá: número mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIPEDA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de licencia de conducir de Canadá: número mínimo 10, número máximo 500 <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo 500 <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 10, recuento máximo 500 <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personally-identifiable-information-pii-data"></a>Datos de identificación personal de Canadá (PII)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de licencia de conducir de Canadá: número mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de licencia de conducir de Canadá: número mínimo 10, número máximo 500  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de servicio de mantenimiento de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  Número de identificación de salud personal (PHIN) de Canadá: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-data-protection-act"></a>Ley de protección de datos de Francia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|DPA de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Tarjeta nacional de identificación (CNI) de Francia: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social de Francia (INSEE): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|DPA de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Tarjeta nacional de identificación (CNI) de Francia: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de Francia (INSEE): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-financial-data"></a>Datos financieros de Francia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Francia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro social de Francia (INSEE): recuento mínimo 1, recuento máximo 9  <br/>  Número de licencia de conducir de Francia: número mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Francia: recuento mínimo 1, recuento máximo 9  <br/>  Tarjeta nacional de identificación (CNI) de Francia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro social de Francia (INSEE): recuento mínimo 10, recuento máximo 500  <br/>  Número de licencia de conducir de Francia: número mínimo 10, número máximo 500  <br/>  Número de pasaporte de Francia: recuento mínimo 10, recuento máximo 500  <br/>  Tarjeta nacional de identificación (CNI) de Francia: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="general-data-protection-regulation-gdpr"></a>Reglamento general de protección de datos (RGPD)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Contenido confidencial de la UE de bajo volumen encontrado  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de licencia de conducir de la UE: número mínimo 1, recuento máximo 9  <br/>  Número de identificación nacional de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguridad social de la UE (SSN) o identificador equivalente: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación fiscal (TIN) de la UE: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Envío de informes de incidentes al administrador  <br/> |
|Se encontró un gran volumen de contenido confidencial de la UE  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo 500  <br/>  Número de licencia de conducir de la UE: número mínimo 10, número máximo 500  <br/>  Número de identificación nacional de la UE: recuento mínimo 10, recuento máximo 500  <br/>  Número de pasaporte de la UE: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguridad social de la UE (SSN) o identificador equivalente: recuento mínimo 10, recuento máximo 500  <br/>  Número de identificación fiscal de la UE (TIN): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Restringir el acceso de usuarios externos al contenido  <br/>  Notificar a los usuarios con sugerencias de directiva y correo electrónico  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Envío de informes de incidentes al administrador  <br/> |
   
## <a name="germany-financial-data"></a>Datos financieros de Alemania

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Datos financieros de Alemania: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Alemania: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="germany-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Alemania

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Alemania: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de licencia de conducir alemán: número mínimo 1, número máximo 9  <br/>  Número de pasaporte alemán: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Alemania: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de licencia de conducir alemán: número mínimo 10, número máximo 500  <br/>  Número de pasaporte alemán: número mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-financial-data"></a>Datos financieros de Israel

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Datos financieros de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 10, recuento máximo 500  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo 500  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Israel

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Id. nacional de Israel: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Id. nacional de Israel: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-protection-of-privacy"></a>Protección de privacidad en Israel

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Privacidad de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Id. nacional de Israel: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Privacidad de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Id. nacional de Israel: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-financial-data"></a>Datos financieros de Japón

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Japón: recuento mínimo 10, recuento máximo 500  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-personally-identifiable-information-pii-data"></a>Datos de identificación personal (PII) de Japón

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residentes de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social de Japón (SIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residentes de Japón: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de Japón (SIN): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-protection-of-personal-information"></a>Protección de información personal de Japón

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PPI de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residentes de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social de Japón (SIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PPI de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residentes de Japón: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de Japón (SIN): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="pci-data-security-standard-pci-dss"></a>Estándar de seguridad de datos PCI (PCI DSS)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PCI DSS: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PCI DSS: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia---anti-cyber-crime-law"></a>Ley contra el crimen cibernético de Arabia Saudí

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|ACC de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|ACC de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia-financial-data"></a>Datos financieros de Arabia Saudí

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Arabia Saudí

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Id. nacional de Arabia Saudita: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Id. nacional de Arabia Saudita: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-access-to-medical-reports-act"></a>Ley de acceso a informes médicos del Reino Unidos

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|AMRA de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  ESPAÑA. Número del servicio nacional de salud: recuento mínimo 1, recuento máximo 9  <br/>  ESPAÑA. Número de seguro nacional (NINO): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|AMRA de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  ESPAÑA. Número de servicio nacional de salud: recuento mínimo 10, recuento máximo 500  <br/>  ESPAÑA. Número de seguro nacional (NINO): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-data-protection-act"></a>Ley de protección de datos del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|DPA de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  ESPAÑA. Número de seguro nacional (NINO): recuento mínimo 1, recuento máximo 9  <br/>  Estados Unidos/ Reino Unido Número de pasaporte: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|DPA de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  ESPAÑA. Número de seguro nacional (NINO): recuento mínimo 10, recuento máximo 500  <br/>  Estados Unidos/ Reino Unido Número de pasaporte: recuento mínimo 10, recuento máximo 500  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-financial-data"></a>Datos financieros del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Financiero de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT :recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo 500  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-personal-information-online-code-of-practice-piocp"></a>Código de prácticas en línea de información personal (PIOCP) del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PIOCP de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  ESPAÑA. Número de seguro nacional (NINO): recuento mínimo 1, recuento máximo 9  <br/>  ESPAÑA. Número del servicio nacional de salud: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIOCP de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  ESPAÑA. Número de seguro nacional (NINO): recuento mínimo 10, recuento máximo 500  <br/>  ESPAÑA. Número de servicio nacional de salud: recuento mínimo 10, recuento máximo 500  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  ESPAÑA. Número de seguro nacional (NINO): recuento mínimo 1, recuento máximo 9  <br/>  Estados Unidos/ Reino Unido Número de pasaporte: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  ESPAÑA. Número de seguro nacional (NINO): recuento mínimo 10, recuento máximo 500  <br/>  Estados Unidos/ Reino Unido Número de pasaporte: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-privacy-and-electronic-communications-regulations"></a>Normas de comunicaciones electrónicas y privacidad del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PECR de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PECR de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-federal-trade-commission-ftc-consumer-rules"></a>Normas del consumidor de la Comisión Federal de Comercio de los EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Reglas de la FTC de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de enrutamiento de ABA: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Reglas de la FTC de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo 500  <br/>  Número de enrutamiento de ABA: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-financial-data"></a>Datos financieros de EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Datos financieros - Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de enrutamiento de ABA: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros - Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo 500  <br/>  Número de enrutamiento de ABA: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-gramm-leach-bliley-act-glba"></a>Ley Gramm-Leach-Bliley (GLBA) de EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|GLBA de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de contribuyente individual (ITIN) de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social (SSN) de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|GLBA de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo 500  <br/>  Número de identificación de contribuyente individual (ITIN) de EE. UU.: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de EE. UU. (SSN): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-health-insurance-act-hipaa"></a>Ley de seguros de salud (HIPAA) de los EE. UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|El contenido coincide con hipaa de EE. UU.  <br/> | Contiene cualquiera de las siguientes informaciones confidenciales:  <br/>  Número de seguro social (SSN) de EE. UU.: recuento mínimo 1, recuento máximo de cualquier  <br/>  Número de la Agencia antidrogas (DEA): recuento mínimo 1, recuento máximo de cualquier  <br/> **AND** <br/>  El contenido contiene cualquiera de estos términos:  <br/>  Clasificación internacional de enfermedades (ICD-9-CM): recuento mínimo 1, recuento máximo cualquiera  <br/>  Clasificación internacional de enfermedades (ICD-10-CM): recuento mínimo 1, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
   
## <a name="us-patriot-act"></a>Ley Patriota de los EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Ley Patriota de los EE.UU.: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de contribuyente individual (ITIN) de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social (SSN) de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Ley Patriota de los EE.UU.: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo 500  <br/>  Número de identificación de contribuyente individual (ITIN) de EE. UU.: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de EE. UU. (SSN): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Estados Unidos

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|PII de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de identificación de contribuyente individual (ITIN) de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro social (SSN) de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Estados Unidos/ Reino Unido Número de pasaporte: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de identificación de contribuyente individual (ITIN) de EE. UU.: recuento mínimo 10, recuento máximo 500  <br/>  Número de seguro social de EE. UU. (SSN): recuento mínimo 10, recuento máximo 500  <br/>  Estados Unidos/ Reino Unido Número de pasaporte: recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-state-breach-notification-laws"></a>Leyes de notificación de incumplimiento estatal de EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Incumplimientos estatales de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de licencia de conducir de EE. UU.: número mínimo 1, recuento máximo 9  <br/>  Número de seguro social (SSN) de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Incumplimientos estatales de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo 500  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo 500  <br/>  Número de licencia de conducir de EE. UU.: número mínimo 10, número máximo 500  <br/>  Número de seguro social de EE. UU. (SSN): recuento mínimo 10, recuento máximo 500 <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-state-social-security-number-confidentiality-laws"></a>Leyes de confidencialidad sobre el número de Seguridad Social de EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Acciones**|
|:-----|:-----|:-----|
|Leyes sobre el SSN de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro social (SSN) de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Leyes sobre el SSN de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro social de EE. UU. (SSN): recuento mínimo 10, recuento máximo 500  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   

