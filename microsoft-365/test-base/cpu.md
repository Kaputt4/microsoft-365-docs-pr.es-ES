---
title: Análisis de regresión de CPU
description: Descripción de resultados de regresión y métricas para el consumo de CPU
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322995"
---
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="1679e-103">Análisis de regresión inteligente de CPU</span><span class="sxs-lookup"><span data-stu-id="1679e-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="1679e-104">El uso de la CPU puede indicar si una aplicación se ve afectada por una actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1679e-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="1679e-105">Test Base for Microsoft 365 proporciona a los desarrolladores de software información sobre las regresión de rendimiento de la CPU que se producen cuando su aplicación se ejecuta en distintas versiones de una próxima actualización del sistema operativo Windows (SO).</span><span class="sxs-lookup"><span data-stu-id="1679e-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="1679e-106">Estas regresión de CPU permiten a los desarrolladores detectar y resolver problemas de aplicaciones (y posibles errores) antes de implementar la actualización del sistema operativo de forma general, lo que evita una mala experiencia para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="1679e-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="1679e-107">Cómo funciona el análisis de regresión de CPU</span><span class="sxs-lookup"><span data-stu-id="1679e-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="1679e-108">Como usuario de Test Base, puede cargar los archivos binarios de la aplicación (en un solo archivo .zip), junto con scripts de prueba asociados y seleccionar la versión del sistema operativo de Windows con la que desea probar la aplicación en el portal base de pruebas de Azure.</span><span class="sxs-lookup"><span data-stu-id="1679e-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="1679e-109">A continuación, el servicio Base de prueba ejecuta los scripts de prueba y realiza el análisis **de regresión de cpu.**</span><span class="sxs-lookup"><span data-stu-id="1679e-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="1679e-110">El servicio comprueba si el uso de la CPU para la aplicación en la versión anterior a la versión de la actualización del sistema operativo de destino está en línea con el uso de la CPU para la versión publicada del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1679e-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="1679e-111">El uso de LA CPU no es una comparación 100 % como para similares, ya que los procesos que se ejecutan en las dos versiones del sistema operativo pueden o no ser una coincidencia exacta debido a versiones del sistema operativo diferentes; sin embargo, el análisis realizado por Test Base puede mostrar si el uso de la CPU para la aplicación se ve afectado por una próxima actualización del sistema operativo y específicamente qué procesos han retrocedido de las ejecuciones de pruebas anteriores.</span><span class="sxs-lookup"><span data-stu-id="1679e-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="1679e-112">En la instantánea siguiente, hay dos versiones del sistema operativo con las que se comparan los usos de CPU para la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="1679e-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="1679e-113">La pestaña Uso de cpu muestra los límites superior e inferior de uso de ambas versiones en percentiles 90 y 10 respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1679e-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="1679e-114">Los gráficos muestran la serie temporal de uso de CPU junto con el uso promedio.</span><span class="sxs-lookup"><span data-stu-id="1679e-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="1679e-115">Los clientes ahora pueden usar la funcionalidad para determinar si el uso de la CPU de su aplicación se ha visto afectado por las actualizaciones del sistema operativo y, específicamente, qué procesos han retrocedido respecto a su ejecución anterior.</span><span class="sxs-lookup"><span data-stu-id="1679e-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![Análisis de regresión de CPU](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="1679e-117">Identificación de procesos relevante</span><span class="sxs-lookup"><span data-stu-id="1679e-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="1679e-118">Aquí se explica cómo identificar procesos regresivos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1679e-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="1679e-119">El análisis de la regresión del rendimiento requiere realizar un seguimiento de diferentes tipos de contadores de rendimiento para cada proceso que se ejecuta en una máquina virtual durante la ejecución de prueba.</span><span class="sxs-lookup"><span data-stu-id="1679e-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="1679e-120">Este análisis captura una gran cantidad de variables para una gran cantidad de procesos para una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="1679e-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="1679e-121">No todos los procesos están asociados a una ejecución o aplicación.</span><span class="sxs-lookup"><span data-stu-id="1679e-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="1679e-122">Para evitar este desafío, se aplica un algoritmo de clasificación de información mutua que usa la probabilidad y la teoría de la información para averiguar qué procesos son más relevantes para una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="1679e-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="1679e-123">Una aplicación puede considerarse un tipo de variable aleatoria discreta mientras que un proceso se considera otro tipo de variable aleatoria discreta.</span><span class="sxs-lookup"><span data-stu-id="1679e-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="1679e-124">La asociación de las dos variables aleatorias se mide usando probabilidades condicionales para la relevancia.</span><span class="sxs-lookup"><span data-stu-id="1679e-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="1679e-125">A continuación, los procesos se muestran en el orden de su relevancia para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="1679e-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="1679e-126">También puede elegir entre los favoritos un subconjunto de procesos que se pueden supervisar, de forma predeterminada, junto con los procesos relevantes para el análisis de regresión de la CPU.</span><span class="sxs-lookup"><span data-stu-id="1679e-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="1679e-127">Una vez detectada una regresión, puede descargar el kit de herramientas Windows analizador de rendimiento y analizar los motivos de las regresión del rendimiento de la CPU.</span><span class="sxs-lookup"><span data-stu-id="1679e-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="1679e-128">El analizador Windows rendimiento toma el registro de seguimiento de eventos (ETL) como entradas y estos archivos .etl están disponibles en los archivos de registro que se pueden descargar para las ejecuciones de prueba en el portal.</span><span class="sxs-lookup"><span data-stu-id="1679e-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="1679e-129">Si desea obtener más información sobre cómo depurar el rendimiento de la CPU, consulte la Windows analizador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1679e-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

