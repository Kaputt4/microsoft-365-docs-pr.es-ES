---
title: Información general
description: Descripción de la base de pruebas
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: d54c4ca0ca9263062e3edb0e062406e5c8d3bc68
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315841"
---
# <a name="what-is-test-base-for-microsoft-365"></a>¿Qué es Test Base para Microsoft 365?

Test Base es un servicio de Azure que permite realizar pruebas de aplicaciones controladas por datos al tiempo que proporciona a los usuarios acceso a pruebas inteligentes desde cualquier lugar del mundo.

Se recomienda a las siguientes entidades incorporar sus aplicaciones, archivos binarios y scripts de prueba en el servicio Test Base for Microsoft 365: Proveedores de software independientes (ISV), integradores de sistemas (SIs) para validar sus aplicaciones y profesionales de TI que quieran validar sus aplicaciones de línea de negocio (LOB) mediante la integración con Microsoft Intune.

## <a name="why-test-your-application-with-test-base"></a>¿Por qué probar la aplicación con Test Base?

El servicio Test Base para Microsoft 365 puede adaptarse a la expansión de la matriz de pruebas según sea necesario, por lo que tendrá confianza en la integridad, compatibilidad y facilidad de uso de las aplicaciones.

Test Base permite que la aplicación siga funcionando según lo esperado, incluso a medida que las dependencias de la plataforma varían y el servicio de actualización de Windows aplica nuevas actualizaciones. Con Test Base, puede evitar el agravamiento, los compromisos de tiempo prolongados y los gastos de configuración y mantenimiento de un entorno de laboratorio complejo para probar las aplicaciones.

Además, puede probar automáticamente la compatibilidad con las actualizaciones de características y seguridad para Windows mediante máquinas virtuales (VM) seguras, a la vez que obtiene acceso a inteligencia de primera clase para probar las aplicaciones. También puede probar la compatibilidad de las aplicaciones con las actualizaciones de seguridad de Windows de versión preliminar mediante el envío de una solicitud para obtener el acceso.

## <a name="how-does-test-base-work"></a>¿Cómo funciona Test Base?

Para registrarse en el servicio Base de pruebas, consulte [Creación de una nueva cuenta de Base de prueba](createAccount.md).

Una vez que un cliente se ha inscrito en el servicio Base de pruebas, es muy sencillo empezar a cargar paquetes de aplicación para realizar pruebas.

Después de una carga correcta, los paquetes se prueban con las actualizaciones de versión preliminar de Windows.

Una vez completadas correctamente las pruebas iniciales, el cliente puede profundizar con información sobre el rendimiento y el análisis de regresión para detectar si las actualizaciones de contenido de versión preliminar han degradado el rendimiento de las aplicaciones de alguna manera.

Sin embargo, si el paquete no pudo realizar ninguna prueba, el cliente también puede aprovechar Insights de las regresiones de memoria o CPU para corregir el error y, a continuación, actualizar el paquete según sea necesario.

Con Test Base, el cliente puede usar una única ubicación para administrar todos los paquetes que se prueban, lo que también puede facilitar la carga y actualización de paquetes para generar nuevas versiones de la aplicación según sea necesario.

> [!NOTE]
> **Para que los clientes puedan aprovechar el contenido de actualización de versión preliminar, deben solicitar específicamente acceso a él. Una vez aprobada la solicitud de acceso a las actualizaciones de versión preliminar, los paquetes cargados se programarán automáticamente para que se prueben con las actualizaciones de Windows de versión preliminar para las versiones del sistema operativo seleccionadas durante la incorporación**.

A continuación, a medida que estén disponibles nuevas actualizaciones de versión preliminar de Windows, los paquetes de aplicación se prueban automáticamente con nuevo contenido de versión preliminar. A partir de entonces, puede ser necesaria una ronda adicional de información. Si los clientes no solicitan acceso específicamente, los paquetes de aplicación se probarán solo con la versión publicada actual de Windows.

Una vez que los paquetes se prueban correctamente, los clientes pueden entregarlos a sus clientes de software y a los usuarios finales con confianza y la garantía de que Test Base hizo su trabajo.

## <a name="next-steps"></a>Siguientes pasos

Siga el vínculo para empezar.
> [!div class="nextstepaction"]
> [Creación de una nueva cuenta base de prueba | Microsoft Docs](createaccount.md)
