---
title: Referencia de sugerencias de directiva de prevención de pérdida de datos
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Obtenga información sobre cómo agregar una sugerencia de directiva a una directiva de prevención de pérdida de datos (DLP) para notificar a un usuario que está trabajando con contenido que entra en conflicto con una directiva DLP.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876825"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>Referencia de sugerencias de directiva de prevención de pérdida de datos

Las sugerencias de directiva DLP en Outlook Web Access se admiten para todas las condiciones, excepciones y acciones que se aplican a la carga de trabajo de Exchange en una directiva DLP excepto las siguientes:

**Condiciones:**

- Sender Is
- Dominio del remitente es
- Recipient es miembro de
- El encabezado contiene palabras o frases
- El encabezado coincide con los patrones
- El tamaño del documento es igual o mayor que
- El tipo de mensaje es
- La importancia del mensaje es
- El juego de caracteres de contenido contiene palabras
- Asunto o cuerpo contiene palabras o frases
- Asunto o cuerpo coincide con patrones
- El juego de caracteres de contenido contiene palabras
- El contenido se recibe desde
- Ha invalidado el remitente la sugerencia de directiva
- El tamaño del mensaje es igual o mayor que
- El atributo SENDER AD contiene palabras o frases
- El atributo sender AD coincide con patrones
- El contenido del documento contiene palabras o frases
- El contenido del documento coincide con los patrones

**Acciones:**

- Reenviar el mensaje para su aprobación al administrador del remitente
- Reenviar el mensaje para su aprobación a aprobadores específicos
- Redirigir el mensaje a usuarios específicos
- Agregar destinatarios al cuadro Para
- Agregar destinatarios al cuadro Cc
- Agregar destinatarios al cuadro CCO
- Agregar el administrador del remitente como destinatario
- Agregar declinación de responsabilidades HTML
- Anteponer el asunto del correo electrónico
- Quitar el cifrado de mensajes de O365 y la protección de derechos
- Eliminar 

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 y versiones posteriores admiten mostrar sugerencias de directiva solo para algunas condiciones y excepciones

Actualmente, Outlook 2013 y versiones posteriores admiten mostrar sugerencias de directiva para directivas que no contienen ninguna condición o excepción aparte de las condiciones mencionadas a continuación y las excepciones correspondientes:

- El contenido contiene (solo funciona para tipos de información confidencial. No se admiten etiquetas de confidencialidad)
- El contenido se comparte

Tenga en cuenta que todas las condiciones funcionan para los correos electrónicos que se creen en la aplicación cliente de Outlook, donde coincidirán con el contenido y aplicarán acciones de protección en el contenido. Sin embargo, la presentación de sugerencias de directiva a los usuarios aún no es compatible con las condiciones que se usan aparte de las mencionadas anteriormente.

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 y versiones posteriores admiten mostrar sugerencias de directiva solo para algunos tipos de información confidencial

La lista de tipos de información confidencial listas para usar que se detectarán para mostrar sugerencias de directivas DLP en Outlook en el escritorio (2013 y versiones posteriores) son las siguientes:

- Número de enrutamiento ABA
- Número de identidad nacional (DNI) de Argentina
- Número de cuenta bancaria de Australia
- Número de cuenta médica de Australia
- Número de pasaporte de Australia
- Número de archivo de impuestos de Australia
- Clave de autenticación de Azure DocumentDB  
- Cadena de conexión de base de datos iaas de Azure y cadena SQL de conexión de Azure  
- Cadena de conexión de IoT de Azure  
- Contraseña de configuración de publicación de Azure  
- Cadena de conexión de caché de Azure Redis  
- Azure SAS  
- Cadena de conexión de Bus de servicio de Azure  
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
- Número de seguridad social de la UE (SSN) o identificador equivalente  
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
- Clasificación internacional de las enfermedades (ICD-10-CM)  
- Clasificación internacional de las enfermedades (ICD-9-CM)  
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
- SQL Server de conexión  
- Identificación nacional de Suecia
- Número de pasaporte de Suecia
- Código SWIFT
- Identificación nacional de Taiwán
- 	Número de pasaporte de Taiwán
- Certificado de residente de Taiwán (ARC/TARC)
- Código de identificación de población tailandés
- Número de identificación nacional turco
- Número de licencia de conductor de Reino Unido
- Número de registro electoral de Reino Unido
- Número de Servicio Nacional de Salud de Reino Unido
- Número de seguro nacional de Reino Unido (NINO)
- Ee.UU. / Reino Unido Passport Number
- Número de cuenta bancaria de EE. UU.
- Número de licencia de conductor de EE. UU.
- Número de identificación de contribuyente individual (ITIN) de EE. UU.
- Número de seguridad social (SSN) de EE. UU.

Tenga en cuenta que los tipos de información confidencial personalizados también se admiten para las sugerencias de directiva DLP, además de los tipos de información confidencial que se han indicado anteriormente.

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a>La prevención de pérdida de datos en el punto de conexión admite sugerencias de directiva solo para algunos tipos de información confidencial

La lista de tipos de información confidencial listas para usar que se detectarán en documentos que residen en dispositivos de extremo son los siguientes:

- Número de enrutamiento ABA 
- Número de identidad nacional (DNI) de Argentina 
- Número de cuenta bancaria de Australia 
- Número de cuenta médica de Australia 
- Número de pasaporte de Australia 
- Número de archivo de impuestos de Australia 
- Número de empresa de Australia 
- Número de compañía australiana 
- Número de licencia de conducir de Austria 
- Tarjeta de identidad de Austria 
- Número de pasaporte de Austria 
- Número de seguridad social de Austria 
- Número de identificación fiscal de Austria 
- Número de impuesto sobre el valor agregado (IVA) de Austria 
- Clave de autenticación de Azure DocumentDB 
- Cadena de conexión de base de datos iaas de Azure y cadena SQL de conexión de Azure 
- Cadena de conexión de IoT de Azure 
- Contraseña de configuración de publicación de Azure 
- Cadena de conexión de caché de Azure Redis 
- Azure SAS 
- Cadena de conexión de Bus de servicio de Azure 
- Clave de cuenta de Azure Storage 
- Clave de cuenta de Azure Storage (genérica) 
- Número de licencia de conducir de Bélgica 
- Número nacional de Bélgica 
- Número de pasaporte de Bélgica 
- Número de impuestos sobre el valor agregado de Bélgica 
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
- Firma de acceso compartido de cuenta de Azure Storage CSCAN-AZURE0060 
- Clave simétrica general CSCAN-GENERAL0140 
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
- Número de seguridad social de la UE (SSN) o identificador equivalente 
- Número de identificación fiscal de la UE (TIN) 
- Número de licencia de conducir de Finlandia 
- Número de seguro de salud europeo de Finlandia 
- Identificación nacional de Finlandia 
- Número de pasaporte de Finlandia 
- Número de licencia de conductor de Francia 
- Número de seguro de salud de Francia 
- Tarjeta de identificación nacional de Francia (CNI) 
- Número de pasaporte de Francia 
- Número de la Seguridad Social de Francia (INSEE) 
- Número de identificación fiscal de Francia (numéro SPI). 
- Número de impuestos de valor agregado de Francia 
- Número de licencia de conductor de Alemania 
- Número de pasaporte de Alemania 
- Número de documento de identidad de Alemania 
- Número de identificación fiscal de Alemania 
- Número de impuestos al valor agregado de Alemania 
- Número de licencia de conducir de Grecia 
- Tarjeta de identificación nacional de Grecia 
- Número de pasaporte de Grecia 
- Número de seguridad social de Grecia (AMKA) 
- Número de identificación fiscal griego 
- Número de tarjeta de identidad de Hong Kong (HKID) 
- Número de seguridad social húngaro (TAJ) 
- Número de impuestos de valor agregado húngaro 
- Número de licencia de conducir de Hungría 
- Número de pasaporte de Hungría 
- Número de identificación personal de Hungría 
- Número de identificación fiscal de Hungría 
- Número de cuenta permanente de India (PAN) 
- Número de identificación único (Aadhaar) de la India 
- Número de tarjeta de identidad (KTP) de Indonesia 
- Número de cuenta bancaria internacional (IBAN) 
- Clasificación internacional de las enfermedades (ICD-10-CM) 
- Clasificación internacional de las enfermedades (ICD-9-CM) 
- Dirección IP 
- Número de licencia de conducir de Irlanda 
- Número de pasaporte de Irlanda 
- Número de servicio público personal (PPS) de Irlanda 
- Número de cuenta bancaria de Israel 
- Identificación nacional de Israel 
- Número de licencia de conductor de Italia 
- Código fiscal de Italia 
- Número de pasaporte de Italia 
- Número de impuestos de valor agregado de Italia 
- Número de cuenta bancaria de Japón 
- Número de licencia de conductor de Japón 
- Número de pasaporte de Japón 
- Número de registro de residente de Japón 
- Número de Seguridad Social de Japón (SIN) 
- Japonés Mi número corporativo 
- Japonés Mi número personal 
- Número de tarjeta de residencia japonesa 
- Número de licencia de conductor de Letonia 
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
- Número de impuestos de valor agregado neerlandés 
- Número de cuenta bancaria de Nueva Zelanda 
- Número de licencia de conducir de Nueva Zelanda 
- Número de ingresos adicionales de Nueva Zelanda 
- Número de Ministerio de salud de Nueva Zelanda 
- Número de bienestar social de Nueva Zelanda 
- Número de identidad de Noruega 
- Número de id. universal unificado de Filipinas 
- Número de licencia de conducir de Polonia 
- Tarjeta de identificación de Polonia 
- Identificación nacional de Polonia (PESEL) 
- Pasaporte de Polonia 
- Número de identificación fiscal de Polonia 
- Número regon polaco 
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
- Número único de ciudadano principal de Eslovenia 
- Número de identificación de Sudáfrica 
- Número de registro de residente de Corea del Sur 
- DNI de España 
- Número de licencia de conducir de España 
- Número de pasaporte de España 
- Número de la Seguridad Social de España (NSS) 
- Número de identificación fiscal de España 
- SQL Server de conexión 
- Número de licencia de conducir de Suecia 
- Identificación nacional de Suecia 
- Número de pasaporte de Suecia 
- Número de identificación fiscal de Suecia 
- Código SWIFT 
- Número de seguro social suizo AHV 
- Identificación nacional de Taiwán 
- 	Número de pasaporte de Taiwán 
- Certificado de residente de Taiwán (ARC/TARC) 
- Código de identificación de población tailandés 
- Número de identificación nacional turco 
- Número de licencia de conductor de Reino Unido 
- Número de registro electoral de Reino Unido 
- Número de Servicio Nacional de Salud de Reino Unido 
- Número de seguro nacional de Reino Unido (NINO) 
- Reino Unido Número de referencia de contribuyente único 
- Ee.UU. / Reino Unido Passport Number 
- Número de cuenta bancaria de EE. UU. 
- Número de licencia de conductor de EE. UU. 
- Número de identificación de contribuyente individual (ITIN) de EE. UU. 
- Número de seguridad social (SSN) de EE. UU. 
- Número de pasaporte de Ucrania (nacional) 
- Número de pasaporte de Ucrania (internacional) 
 
Tenga en cuenta que los tipos de información confidencial personalizados también se detectarán además de los tipos de información confidencial que se han indicado anteriormente.

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Matriz de soporte técnico para sugerencias de directivas dlp en aplicaciones de Microsoft

|**Aplicación y plataforma**|**Compatibilidad con sugerencias de directiva DLP**|**Tipos de información confidencial admitidos**|**Predicados y acciones admitidas**|**Comments**|
|:--|:--|:--|:--|:--|
|**Outlook Web Access**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Todo|Subset|Consulta [Referencia de sugerencias de directiva de prevención de pérdida de datos](#data-loss-prevention-policy-tips-reference)|
|**Outlook Win32 (Outlook 2013 y posteriores)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Subset|Vea [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) y versiones posteriores admite mostrar sugerencias de directiva solo para algunas condiciones y excepciones, [y Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) y versiones posteriores admite mostrar sugerencias de directiva solo para algunos tipos de información confidencial para obtener detalles sobre la compatibilidad con tipos de información confidencial y condiciones dlp y acciones admitidas para mostrar sugerencias de directivas DLP en Outlook Win32.|
|**Outlook Mobile (iOS, Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Ninguno|Ninguno|Las sugerencias de directivas DLP no se admiten en Outlook mobile|
|**Cliente web de Sharepoint Online/One Drive para empresas**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Todo|Todos los predicados y acciones de SPO/ODB en DLP||
|**Cliente Win32/ One Drive for Business Win32 de Sharepoint**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Ninguno|Ninguno|Las sugerencias de directivas DLP no se admiten en aplicaciones cliente de escritorio de Sharepoint o OneDrive|
|**Word, Excel, Cliente web de Powerpoint**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Todo|Todos los predicados y acciones de SPO/ODB en DLP|La sugerencia de directiva DLP se admite si el documento está hospedado en SPO o en la aplicación web de ODB y la directiva DLP ya está estampada.|
|**Word, Excel, Cliente móvil de Powerpoint**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Ninguno|Ninguno|Las sugerencias de directivas DLP no se admiten en aplicaciones móviles para Office.|
|**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Todo|Todos los predicados de Teams en la directiva DLP|Las sugerencias de directiva mostrarán cuándo se marca un mensaje como "Este mensaje se ha marcado. ¿Qué puedo hacer?" Al hacer clic en el vínculo, el usuario puede revisar los tipos de información confidencial detectados e invalidar o notificar un problema si lo permite el administrador. Tenga en cuenta que no se muestran sugerencias de directiva para archivos. Cuando el destinatario intenta obtener acceso al documento, es posible que se les deniegue el acceso si no se permite.|
|**Dispositivos de extremo de Win32**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Todos los predicados y acciones dlp de extremo en la directiva DLP|Consulte [Prevención de pérdida de datos en el punto de conexión admite sugerencias de directiva solo para algunos tipos de información confidencial](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)|
|**Dispositivos Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Ninguno|Ninguno|La prevención de pérdida de datos no es aplicable en dispositivos Mac hoy en día|
|**Aplicaciones en la nube de terceros**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Ninguno|Ninguno|Prevención de pérdida de datos|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Ninguno|Ninguno||
|**Word, Excel, Cliente de Powerpoint Win32**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Subset|Subset|Las sugerencias de directiva para aplicaciones cliente WXP funcionarán para documentos almacenados en Sitios de Sharepoint Online o One Drive para empresas para todas las directivas DLP que tengan exactamente lo siguiente o un subconjunto de condiciones o acciones en la directiva DLP:</br> <ul><li>El contenido contiene tipos de información confidencial</li><li>Ámbito de acceso (el contenido se comparte interna o externamente)</li><li>Notificar al usuario (sugerencias de directiva/notificaciones de usuario)</li><li>Bloquear a todos</li><li>Informes de incidentes</li></ul></br> Si hay alguna otra condición o acción, la sugerencia de directiva DLP para esa directiva no aparecerá en las aplicaciones de escritorio de Word, Excel o PowerPoint.|
||||||