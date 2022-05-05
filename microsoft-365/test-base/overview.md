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
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 13eaea1e62dd030f86e08d885ad743d673d6142c
ms.sourcegitcommit: b16520d8bfe04b29274f7a129d90ef116bb77f69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "65231701"
---
# <a name="what-is-test-base-for-microsoft-365"></a>¿Qué es Test Base para Microsoft 365?

Test Base es un servicio de Azure que permite realizar pruebas de aplicaciones controladas por datos al tiempo que proporciona a los usuarios acceso a pruebas inteligentes desde cualquier lugar del mundo.

Se recomienda que las siguientes entidades incorporen sus aplicaciones, archivos binarios y scripts de prueba a la base de pruebas para Microsoft 365 servicio: proveedores de software independientes (ISV), integradores de sistemas (SIs) para validar sus aplicaciones y profesionales de TI que quieran validar sus aplicaciones de línea de negocio (LOB) mediante la integración con Microsoft Intune.

## <a name="why-test-your-application-with-test-base"></a>¿Por qué probar la aplicación con Test Base?

La base de pruebas para Microsoft 365 servicio puede adaptarse a la expansión de la matriz de pruebas según sea necesario, por lo que tendrá confianza en la integridad, compatibilidad y facilidad de uso de las aplicaciones.

Test Base permite que la aplicación siga funcionando según lo esperado, incluso cuando las dependencias de la plataforma varían y el servicio de actualización de Windows aplica nuevas actualizaciones. Con Test Base, puede evitar el agravamiento, los compromisos de tiempo prolongados y los gastos de configuración y mantenimiento de un entorno de laboratorio complejo para probar las aplicaciones.

Además, puede probar automáticamente la compatibilidad con las actualizaciones de seguridad y características para Windows mediante máquinas virtuales seguras (VM) y, al mismo tiempo, obtener acceso a inteligencia de primer nivel para probar las aplicaciones. También puede probar la compatibilidad de las aplicaciones con las actualizaciones de seguridad de Windows de versión preliminar mediante el envío de una solicitud para obtener el acceso.

## <a name="how-does-test-base-work"></a>¿Cómo funciona Test Base?

Para registrarse en el servicio Base de pruebas, consulte [Creación de una nueva cuenta de Base de prueba](createAccount.md).

Una vez que un cliente se ha inscrito en el servicio Base de pruebas, es muy sencillo empezar a cargar paquetes de aplicación para realizar pruebas.

Después de una carga correcta, los paquetes se prueban con Windows actualizaciones de versión preliminar.

Una vez completadas correctamente las pruebas iniciales, el cliente puede profundizar con información sobre el rendimiento y el análisis de regresión para detectar si las actualizaciones de contenido de versión preliminar han degradado el rendimiento de las aplicaciones de alguna manera.

Sin embargo, si el paquete no pudo realizar ninguna prueba, el cliente también puede aprovechar Ideas de regresiones de memoria o CPU para corregir el error y, a continuación, actualizar el paquete según sea necesario.

Con Test Base, el cliente puede usar una única ubicación para administrar todos los paquetes que se prueban, lo que también puede facilitar la carga y actualización de paquetes para generar nuevas versiones de la aplicación según sea necesario.

> [!NOTE]
> **Para que los clientes puedan aprovechar el contenido de actualización de versión preliminar, deben solicitar específicamente acceso a él. Una vez aprobada la solicitud de acceso a las actualizaciones de versión preliminar, los paquetes cargados se programarán automáticamente para que se prueben con la versión preliminar Windows actualizaciones de las versiones del sistema operativo seleccionadas durante la incorporación**.

A continuación, a medida que están disponibles nuevas Windows actualizaciones de versión preliminar, los paquetes de aplicación se prueban automáticamente con nuevo contenido de versión preliminar. A partir de entonces, puede ser necesaria una ronda adicional de información. Si los clientes no solicitan acceso específicamente, los paquetes de aplicación se probarán solo con la versión publicada actual de Windows.

Una vez que los paquetes se prueban correctamente, los clientes pueden entregarlos a sus clientes de software y a los usuarios finales con confianza y la garantía de que Test Base hizo su trabajo.

## <a name="next-steps"></a>Siguientes pasos

Siga el vínculo para empezar.
> [!div class="nextstepaction"]
> [Creación de una nueva cuenta base de prueba | Microsoft Docs](createaccount.md)
