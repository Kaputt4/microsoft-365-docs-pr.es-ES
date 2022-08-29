---
title: Referencia de sugerencias de directiva de prevención de pérdida de datos
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: Obtenga información sobre cómo agregar una sugerencia de directiva a una directiva de prevención de pérdida de datos (DLP) para notificar a un usuario que está trabajando con contenido que entra en conflicto con una directiva DLP.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 3d48a51311be9bf3324399a582fbb39bc4c38b8d
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405780"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>Referencia de sugerencias de directiva de prevención de pérdida de datos

Las sugerencias de directiva DLP en Outlook Web Access se admiten para todas las condiciones, excepciones y acciones que se aplican en la carga de trabajo de Exchange en una directiva DLP, excepto las siguientes:

**Condiciones:**

- El destinatario es un miembro de
- El encabezado contiene palabras o frases
- El encabezado coincide con patrones
- El tipo de mensaje es
- El juego de caracteres de contenido contiene palabras
- ¿Ha invalidado el remitente la sugerencia de directiva?
- El tamaño del mensaje es igual o mayor que
- El atributo de AD del remitente contiene palabras o frases
- El atributo de AD del remitente coincide con los patrones
- Intervalos IP del remitente
- El atributo AD de destinatario contiene palabras o frases
- El atributo de AD de destinatario coincide con los patrones
- El nombre del documento contiene palabras o frases
- El nombre del documento coincide con los patrones
- El contenido del documento contiene palabras o frases
- El contenido del documento coincide con patrones

**Acciones:**

- Reenviar el mensaje para su aprobación al administrador del remitente
- Reenviar el mensaje para su aprobación a aprobadores específicos
- Redirigir el mensaje a usuarios específicos
- Agregar destinatarios a To Box
- Adición de destinatarios a Cc Box
- Agregar destinatarios al cuadro de cco
- Agregar el administrador del remitente como destinatario
- Agregar declinación de responsabilidades de HTML
- Anteponer asunto de correo electrónico
- Eliminación del cifrado de mensajes de O365 y la protección de derechos

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 y versiones posteriores admiten la presentación de sugerencias de directiva solo para algunas condiciones y excepciones

Actualmente, Outlook 2013 y versiones posteriores admiten la presentación de sugerencias de directivas para directivas que no contienen ninguna condición o excepción aparte de las condiciones mencionadas a continuación y las excepciones correspondientes:

- El contenido contiene (solo funciona para tipos de información confidencial. No se admiten etiquetas de confidencialidad)
- El contenido se comparte

Tenga en cuenta que todas las condiciones funcionan para los correos electrónicos creados en la aplicación cliente de Outlook, donde coincidirán con el contenido y aplicarán acciones de protección en el contenido. Sin embargo, no se admite mostrar sugerencias de directiva a los usuarios para las condiciones que se usan aparte de las mencionadas anteriormente.

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 y versiones posteriores y aplicaciones de Office en escritorio que muestran sugerencias de directiva para solo algunos tipos de información confidencial

La lista de tipos de información confidencial que se detectarán para mostrar sugerencias de directiva DLP en Outlook on Desktop (2013 y versiones posteriores) y aplicaciones de Office (Word, Excel, PowerPoint) en el escritorio son las siguientes:

- Número de enrutamiento ABA
- Número de identidad nacional (DNI) de Argentina
- Número de cuenta bancaria de Australia
- Número de cuenta médica de Australia
- Número de pasaporte de Australia
- Número de archivo de impuestos de Australia
- Clave de autenticación de Azure DocumentDB  
- Cadena de conexión de base de datos iaas de Azure y cadena de conexión de Azure SQL  
- Cadena de conexión de Azure IoT  
- Contraseña de configuración de publicación de Azure  
- Cadena de conexión de Azure Redis Cache  
- Azure SAS  
- Azure Service Bus cadena de conexión  
- Clave de cuenta de Azure Storage  
- Clave de cuenta de Azure Storage (genérica)  
- Número nacional de Bélgica
- Número CPF de Brasil
- Número de entidad jurídica de Brasil (CNPJ)
- 	Tarjeta de identificación nacional de Brasil (RG)
- Número de cuenta bancaria de Canadá
- Número de licencia de conductor de Canadá
- Número de servicio de salud de Canadá
- Número de pasaporte de Canadá
- Número de Identificación Personal de salud en Canadá (PHIN)
- Número de seguridad social de Canadá
- 	Número de tarjeta de identidad de Chile
- 	Número de tarjeta de identidad de residente de China (PRC)
- Número de tarjeta de crédito
- Número de tarjeta de identidad de Croacia  
- Número de identificación personal de Croacia (OIB)  
- Número de identidad personal checo  
- Número de identificación personal de Dinamarca
- Número de la Drug Enforcement Agency (DEA)
- Número de tarjeta de débito de la UE
- Número de licencia de conducir de la UE  
- Número de identificación nacional de la UE  
- Número de pasaporte de la UE  
- Número de seguro social (SSN) de la UE o identificador equivalente  
- Número de identificación fiscal de la UE (TIN)  
- Identificación nacional de Finlandia
- Número de pasaporte de Finlandia
- Número de licencia de conductor de Francia
- Tarjeta de identificación nacional de Francia (CNI)
- Número de pasaporte de Francia
- Número de la Seguridad Social de Francia (INSEE)
- Número de licencia de conductor de Alemania
- Número de pasaporte de Alemania
- Número de documento de identidad de Alemania
- Tarjeta de identificación nacional de Grecia  
- Número de tarjeta de identidad de Hong Kong (HKID)
- Número de cuenta permanente de India (PAN)
- Número de identificación único (Aadhaar) de la India
- Número de tarjeta de identidad (KTP) de Indonesia
- Número de cuenta bancaria internacional (IBAN)
- Clasificación internacional de enfermedades (ICD-10-CM)  
- Clasificación internacional de enfermedades (ICD-9-CM)  
- Dirección IP
- Número de servicio público personal (PPS) de Irlanda 
- Número de cuenta bancaria de Israel
- Identificación nacional de Israel
- Número de licencia de conductor de Italia
- Número de cuenta bancaria de Japón
- Número de licencia de conductor de Japón
- Número de pasaporte de Japón
- Número de registro de residente de Japón
- Número de Seguridad Social de Japón (SIN)
- Número de tarjeta de residencia japonesa
- Número de tarjeta de identidad de Malasia
- Número de servicio del ciudadano (BSN) de Países Bajos  
- Número de Ministerio de salud de Nueva Zelanda
- Número de identidad de Noruega  
- Número de id. universal unificado de Filipinas
- Tarjeta de identificación de Polonia
- Identificación nacional de Polonia (PESEL)
- Pasaporte de Polonia
- Número de tarjeta del ciudadano de Portugal
- Identificación nacional de Arabia Saudí
- Número de tarjeta de identidad de registro nacional (NRIC) de Singapur
- Número de identificación de Sudáfrica  
- Número de registro de residente de Corea del Sur
- Número de la Seguridad Social de España (NSS)
- SQL Server cadena de conexión  
- Identificación nacional de Suecia
- Número de pasaporte de Suecia
- Código SWIFT
- Identificación nacional de Taiwán
- 	Número de pasaporte de Taiwán
- Certificado de residente de Taiwán (ARC/TARC)
- Código de identificación de población tailandesa
- Número de identificación nacional turco
- Número de licencia de conductor de Reino Unido
- Número de registro electoral de Reino Unido
- Número de Servicio Nacional de Salud de Reino Unido
- Número de seguro nacional de Reino Unido (NINO)
- Estados Unidos/ Reino Unido Passport Number
- Número de cuenta bancaria de EE. UU.
- Número de licencia de conductor de EE. UU.
- Número de identificación de contribuyente individual (ITIN) de EE. UU.
- Número de seguridad social (SSN) de EE. UU.

Tenga en cuenta que algunos tipos de información confidencial personalizados también se admiten para sugerencias de directiva DLP, además de los tipos de información confidencial integrados anteriormente.

> [!NOTE]
> No todos los elementos de tipos de información confidencial personalizados son compatibles con todas las versiones de Office. Los elementos de entidad para los SIT personalizados, como Functions, pueden provocar incompatibilidad.

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>Prevención de pérdida de datos en dispositivos de punto de conexión admite sugerencias de directiva solo para algunos tipos de información confidencial

La lista de tipos de información confidencial que se detectarán en los documentos que residen en dispositivos de punto de conexión es la siguiente:

- Número de enrutamiento ABA 
- Número de identidad nacional (DNI) de Argentina 
- Número de cuenta bancaria de Australia 
- Número de cuenta médica de Australia 
- Número de pasaporte de Australia 
- Número de archivo de impuestos de Australia 
- Número de negocio de Australia 
- Número de empresa australiano 
- Número de licencia de conducir de Austria 
- Tarjeta de identidad de Austria 
- Número de pasaporte de Austria 
- Número de seguro social de Austria 
- Número de identificación fiscal de Austria 
- Número del impuesto sobre el valor añadido (IVA) de Austria 
- Clave de autenticación de Azure DocumentDB 
- Cadena de conexión de base de datos iaas de Azure y cadena de conexión de Azure SQL 
- Cadena de conexión de Azure IoT 
- Contraseña de configuración de publicación de Azure 
- Cadena de conexión de Azure Redis Cache 
- Azure SAS 
- Azure Service Bus cadena de conexión 
- Clave de cuenta de Azure Storage 
- Clave de cuenta de Azure Storage (genérica) 
- Número de licencia de conducir de Bélgica 
- Número nacional de Bélgica 
- Número de pasaporte de Bélgica 
- Número de impuestos sobre el valor añadido de Bélgica 
- Número CPF de Brasil 
- Número de entidad jurídica de Brasil (CNPJ) 
- 	Tarjeta de identificación nacional de Brasil (RG) 
- Número de licencia de conducir de Bulgaria 
- Número de pasaporte de Bulgaria 
- Número civil uniforme de Bulgaria 
- Número de cuenta bancaria de Canadá 
- Número de licencia de conductor de Canadá 
- Número de servicio de salud de Canadá 
- Número de pasaporte de Canadá 
- Número de Identificación Personal de salud en Canadá (PHIN) 
- Número de seguridad social de Canadá 
- 	Número de tarjeta de identidad de Chile 
- 	Número de tarjeta de identidad de residente de China (PRC) 
- Número de tarjeta de crédito 
- Número de licencia de conducir de Croacia 
- Número de tarjeta de identidad de Croacia 
- Número de tarjeta de identificación nacional de Croacia 
- Número de pasaporte de Croacia 
- Número de identificación personal de Croacia (OIB) 
- Firma de acceso compartido de la cuenta de Azure Storage CSCAN-AZURE0060 
- CSCAN-GENERAL0140 Clave simétrica general 
- Número de licencia de conducir de Chipre 
- Tarjeta de identidad de Chipre 
- Número de pasaporte de Chipre 
- Número de identificación fiscal de Chipre 
- Número de licencia de conducir checo 
- Número de identidad personal checo 
- Número de pasaporte de la República Checa 
- Número de licencia de conducir de Dinamarca 
- Número de pasaporte de Dinamarca 
- Número de identificación personal de Dinamarca 
- Número de la Drug Enforcement Agency (DEA) 
- Número de licencia de conducir de Estonia 
- Número de pasaporte de Estonia 
- Código de identificación personal de Estonia 
- Número de tarjeta de débito de la UE 
- Número de licencia de conducir de la UE 
- Número de identificación nacional de la UE 
- Número de pasaporte de la UE 
- Número de seguro social (SSN) de la UE o identificador equivalente 
- Número de identificación fiscal de la UE (TIN) 
- Número de licencia de conducir de Finlandia 
- Número de seguro médico europeo de Finlandia 
- Identificación nacional de Finlandia 
- Número de pasaporte de Finlandia 
- Número de licencia de conductor de Francia 
- Número de seguro médico de Francia 
- Tarjeta de identificación nacional de Francia (CNI) 
- Número de pasaporte de Francia 
- Número de la Seguridad Social de Francia (INSEE) 
- Número de identificación fiscal de Francia (numéro SPI.) 
- Número de impuesto sobre el valor añadido de Francia 
- Número de licencia de conductor de Alemania 
- Número de pasaporte de Alemania 
- Número de documento de identidad de Alemania 
- Número de identificación fiscal de Alemania 
- Número de impuesto sobre el valor añadido de Alemania 
- Número de licencia de conducir de Grecia 
- Tarjeta de identificación nacional de Grecia 
- Número de pasaporte de Grecia 
- Número de la seguridad social de Grecia (AMKA) 
- Número de identificación fiscal griega 
- Número de tarjeta de identidad de Hong Kong (HKID) 
- Número de seguro social húngaro (TAJ) 
- Número de impuestos sobre el valor añadido húngaro 
- Número de licencia de conducir de Hungría 
- Número de pasaporte de Hungría 
- Número de identificación personal de Hungría 
- Número de identificación fiscal de Hungría 
- Número de cuenta permanente de India (PAN) 
- Número de identificación único (Aadhaar) de la India 
- Número de tarjeta de identidad (KTP) de Indonesia 
- Número de cuenta bancaria internacional (IBAN) 
- Clasificación internacional de enfermedades (ICD-10-CM) 
- Clasificación internacional de enfermedades (ICD-9-CM) 
- Dirección IP 
- Número de licencia de conducir de Irlanda 
- Número de pasaporte de Irlanda 
- Número de servicio público personal (PPS) de Irlanda 
- Número de cuenta bancaria de Israel 
- Identificación nacional de Israel 
- Número de licencia de conductor de Italia 
- Código fiscal de Italia 
- Número de pasaporte de Italia 
- Número de impuesto sobre el valor añadido de Italia 
- Número de cuenta bancaria de Japón 
- Número de licencia de conductor de Japón 
- Número de pasaporte de Japón 
- Número de registro de residente de Japón 
- Número de Seguridad Social de Japón (SIN) 
- Japonés Mi número corporativo 
- Japonés Mi número personal 
- Número de tarjeta de residencia japonesa 
- Número de licencia de conducir de Letonia 
- Número de pasaporte de Letonia 
- Código personal de Letonia 
- Número de licencia de conducir de Lituania 
- Número de pasaporte de Lituania 
- Código personal de Lituania 
- Número de licencia de conducir de Luxemburgo 
- Número de identificación nacional de Luxemburgo (personas físicas) 
- Número de identificación nacional de Luxemburgo (personas no físicas) 
- Número de pasaporte de Luxemburgo 
- Número de tarjeta de identidad de Malasia 
- Número de licencia de conducir de Malta 
- Número de tarjeta de identidad de Malta 
- Número de pasaporte de Malta 
- Número de identificación fiscal de Malta 
- Número de servicio del ciudadano (BSN) de Países Bajos 
- Número de licencia de conducir de Países Bajos 
- Número de pasaporte neerlandés 
- Número de identificación fiscal de Países Bajos 
- Número de impuestos sobre el valor añadido de los Países Bajos 
- Número de cuenta bancaria de Nueva Zelanda 
- Número de licencia de conducir de Nueva Zelanda 
- Número de ingresos interiores de Nueva Zelanda 
- Número de Ministerio de salud de Nueva Zelanda 
- Número de bienestar social de Nueva Zelanda 
- Número de identidad de Noruega 
- Número de id. universal unificado de Filipinas 
- Número de licencia de conducir de Polonia 
- Tarjeta de identificación de Polonia 
- Identificación nacional de Polonia (PESEL) 
- Pasaporte de Polonia 
- Número de identificación fiscal de Polonia 
- Número DE REGON polaco 
- Número de tarjeta del ciudadano de Portugal 
- Número de licencia de conducir de Portugal 
- Número de pasaporte de Portugal 
- Número de identificación fiscal de Portugal 
- Número de licencia de conducir de Rumania 
- Número de pasaporte de Rumania 
- Código numérico personal (CNP) de Rumania 
- Número de pasaporte ruso (nacional) 
- Número de pasaporte ruso (internacional) 
- Identificación nacional de Arabia Saudí 
- Número de tarjeta de identidad de registro nacional (NRIC) de Singapur 
- Número de licencia de conducir de Eslovaquia 
- Número de pasaporte de Eslovaquia 
- Número personal de Eslovaquia 
- Número de licencia de conducir de Eslovenia 
- Número de pasaporte de Eslovenia 
- Número de identificación fiscal de Eslovenia 
- Número del documento de identidad único de Eslovenia 
- Número de identificación de Sudáfrica 
- Número de registro de residente de Corea del Sur 
- DNI de España 
- Número de licencia de conducir de España 
- Número de pasaporte de España 
- Número de la Seguridad Social de España (NSS) 
- Número de identificación fiscal de España 
- SQL Server cadena de conexión 
- Número de licencia de conducir de Suecia 
- Identificación nacional de Suecia 
- Número de pasaporte de Suecia 
- Número de identificación fiscal de Suecia 
- Código SWIFT 
- Número de seguro social suizo AHV 
- Identificación nacional de Taiwán 
- 	Número de pasaporte de Taiwán 
- Certificado de residente de Taiwán (ARC/TARC) 
- Código de identificación de población tailandesa 
- Número de identificación nacional turco 
- Número de licencia de conductor de Reino Unido 
- Número de registro electoral de Reino Unido 
- Número de Servicio Nacional de Salud de Reino Unido 
- Número de seguro nacional de Reino Unido (NINO) 
- Reino Unido Número único de identificación fiscal 
- Estados Unidos/ Reino Unido Passport Number 
- Número de cuenta bancaria de EE. UU. 
- Número de licencia de conductor de EE. UU. 
- Número de identificación de contribuyente individual (ITIN) de EE. UU. 
- Número de seguridad social (SSN) de EE. UU. 
- Número de pasaporte de Ucrania (nacional) 
- Número de pasaporte de Ucrania (internacional) 
 
Tenga en cuenta que los tipos de información confidencial personalizados también se detectarán además de los tipos de información confidencial de fábrica anteriores.

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Matriz de compatibilidad para sugerencias de directiva DLP en aplicaciones de Microsoft

|**Aplicación y plataforma**|**Compatibilidad con sugerencias de directiva DLP**|**Tipos de información confidencial admitidos**|**Predicados y acciones admitidos**|**Comentarios**|
|:--|:--|:--|:--|:--|
|**Outlook en la web**|:::image type="icon" source="../media/rightmrk.png" border="false":::|todo|Subconjunto||
|**Outlook Win32 (versión 2105 compilación 14026.20000 y canal semestral ver. 2102 compilación 13801.20862)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subconjunto|Subconjunto|Vea [Outlook 2013 y versiones posteriores que muestran sugerencias de directiva para algunas condiciones y excepciones](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) y [Outlook 2013 y versiones posteriores y compatibilidad con aplicaciones de Office en escritorio que muestran sugerencias de directivas para algunos tipos de información confidencial](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) para obtener detalles sobre la compatibilidad con tipos de información confidencial y condiciones DLP y acciones admitidas para mostrar sugerencias de directiva DLP en Outlook Win32.|
|**Outlook Mobile (iOS, Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|ninguno|ninguno|Las sugerencias de directiva DLP no se admiten en Outlook Mobile|
|**Cliente web de SharePoint Online/OneDrive para la Empresa**|:::image type="icon" source="../media/rightmrk.png" border="false":::|todo|todos los predicados y acciones de SPO/ODB en DLP||
|**Cliente Win32/ OneDrive para la Empresa Win32 de SharePoint**|:::image type="icon" source="../media/crsmrk.png" border="false":::|ninguno|ninguno|Las sugerencias de directiva DLP no se admiten en aplicaciones cliente de escritorio de SharePoint o OneDrive|
|**Word, Excel, Cliente web de PowerPoint**|:::image type="icon" source="../media/rightmrk.png" border="false":::|todo|todos los predicados y acciones de SPO/ODB en DLP|Se admite la sugerencia de directiva DLP si el documento está hospedado en la aplicación web SPO o ODB y la directiva DLP ya está marcada.|
|**Word, Excel, PowerPoint Mobile Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|ninguno|ninguno|Las sugerencias de directiva DLP no se admiten en aplicaciones móviles para Office.|
|**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|todo|todos los predicados de Teams en la directiva DLP|Las sugerencias de directiva se mostrarán cuando se marque un mensaje como "Este mensaje se ha marcado. ¿Qué puedo hacer?" Al hacer clic en el vínculo, el usuario puede revisar los tipos de información confidencial detectados e invalidar o notificar un problema si lo permite el administrador. Tenga en cuenta que no se muestra ninguna sugerencia de directiva para los archivos. Cuando el destinatario intenta acceder al documento, es posible que obtenga acceso denegado si no se permite.|
|**Dispositivos de punto de conexión Win32**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subconjunto|todos los predicados y acciones de DLP de punto de conexión en la directiva DLP|Consulte [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types (Prevención de pérdida de datos en el punto de conexión admite sugerencias de directivas) solo para algunos tipos de información confidencial](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types).|
|**dispositivos macOS**|solo sugerencias predeterminadas|todo|Subconjunto|Las directivas de prevención de pérdida de datos se pueden aplicar en dispositivos macOS. No se admiten sugerencias de directivas personalizadas.|
|**Aplicaciones en la nube de terceros**|:::image type="icon" source="../media/crsmrk.png" border="false":::|ninguno|ninguno|Las sugerencias de directivas de prevención de pérdida de datos no se admiten en aplicaciones en la nube de terceros|
|**Local**|:::image type="icon" source="../media/crsmrk.png" border="false":::|ninguno|ninguno||
|**Cliente Win32 de Word, Excel y PowerPoint**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Subconjunto|Subconjunto|Vea [Outlook 2013 y versiones posteriores y La compatibilidad con aplicaciones de Office en escritorio muestra sugerencias de directivas para algunos tipos de información confidencial para](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) la lista de tipos de información confidencial admitidos</br></br>Las sugerencias de directivas para las aplicaciones cliente WXP funcionarán para los documentos almacenados en SharePoint Online o OneDrive para la Empresa Sitios para todas las directivas DLP que tengan exactamente las siguientes condiciones o un subconjunto de condiciones o acciones en la directiva DLP:</br> <ul><li>El contenido contiene tipos de información confidencial</li><li>Ámbito de acceso (el contenido se comparte interna o externamente)</li><li>Notificar al usuario (sugerencias de directivas o notificaciones de usuario)</li><li>Bloquear a todos</li><li>Informes de incidentes</li></ul></br> Si hay alguna otra condición o acción, la sugerencia de directiva DLP para esa directiva no aparecerá en las aplicaciones de escritorio de Word, Excel o PowerPoint.</br>Consulte [Sugerencias de directiva en Excel, PowerPoint y Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) para obtener más detalles.|
|**Power BI**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Subconjunto|Subconjunto|Las directivas de prevención de pérdida de datos en Power BI se encuentran en versión preliminar pública. </br></br> Se admiten sugerencias de directivas y alertas de administración. |
