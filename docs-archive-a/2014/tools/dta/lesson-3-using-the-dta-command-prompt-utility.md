---
title: 'Lección 3: usar la utilidad del símbolo del sistema DTA | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 30f27f4d-8852-4b12-ba62-57f63e496f1d
author: stevestein
ms.author: sstein
ms.openlocfilehash: abbde02cd73e01937e6d0669c10f2db28da8a76e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743778"
---
# <a name="lesson-3-using-the-dta-command-prompt-utility"></a><span data-ttu-id="0336f-102">Lección 3: Usar la utilidad del símbolo del sistema dta</span><span class="sxs-lookup"><span data-stu-id="0336f-102">Lesson 3: Using the dta Command Prompt Utility</span></span>
  <span data-ttu-id="0336f-103">La utilidad del símbolo del sistema **dta** ofrece funcionalidad adicional a la del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0336f-103">The **dta** command-prompt utility offers functionality in addition to that provided by the Database Engine Tuning Advisor.</span></span>  
  
 <span data-ttu-id="0336f-104">Puede utilizar las herramientas XML que desee para crear archivos de entrada para la utilidad mediante el esquema XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0336f-104">You can use your favorite XML tools to create input files for the utility by using the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="0336f-105">Este esquema se instala al instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y se encuentra en: C:\Archivos de programa (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span><span class="sxs-lookup"><span data-stu-id="0336f-105">This schema is installed when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and can be found at: C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span></span>  
  
 <span data-ttu-id="0336f-106">El esquema XML del Asistente para la optimización de motor de base de datos también se encuentra disponible en línea en el [sitio web de Microsoft](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="0336f-106">The Database Engine Tuning Advisor XML schema is also available online at [this Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span></span>  
  
 <span data-ttu-id="0336f-107">Este esquema ofrece una mayor flexibilidad a la hora de configurar opciones de optimización.</span><span class="sxs-lookup"><span data-stu-id="0336f-107">The Database Engine Tuning Advisor XML schema provides more flexibility to set tuning options.</span></span> <span data-ttu-id="0336f-108">Por ejemplo, le permite realizar análisis de escenarios condicionales.</span><span class="sxs-lookup"><span data-stu-id="0336f-108">For example, it enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="0336f-109">El análisis de escenarios condicionales conlleva especificar un conjunto de estructuras de diseño físico hipotético ya existente para la base de datos que desea optimizar y, a continuación, analizarla con el Asistente para la optimización de motor de base de datos para determinar si este diseño físico hipotético mejorará el rendimiento del procesamiento de consultas.</span><span class="sxs-lookup"><span data-stu-id="0336f-109">"What-if" analysis involves specifying a set of existing and hypothetical physical design structures for the database you want to tune, and then analyzing it with the Database Engine Tuning Advisor to find out whether this hypothetical physical design will improve query processing performance.</span></span> <span data-ttu-id="0336f-110">Este tipo de análisis tiene la ventaja de evaluar la nueva configuración sin incurrir en la sobrecarga que supone implementarla realmente.</span><span class="sxs-lookup"><span data-stu-id="0336f-110">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="0336f-111">Si el diseño físico hipotético no proporciona las mejoras de rendimiento que desea, es fácil modificarlo y volver a analizarlo hasta que logre la configuración que se ajuste a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="0336f-111">If your hypothetical physical design does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="0336f-112">Además, al usar el esquema XML del Asistente para la optimización de motor de base de datos y la utilidad del símbolo del sistema **dta** , puede incorporar la funcionalidad del asistente a los scripts y usarla con otras herramientas de diseño de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="0336f-112">In addition, using the Database Engine Tuning Advisor XML schema and the **dta** command-prompt utility, you can incorporate Database Engine Tuning Advisor functionality into scripts and use it with other database design tools.</span></span>  
  
 <span data-ttu-id="0336f-113">Esta lección no cubre el uso de la funcionalidad de entrada XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0336f-113">Using the XML input functionality of Database Engine Tuning Advisor is beyond the scope of this lesson.</span></span>  
  
 <span data-ttu-id="0336f-114">Esta lección ofrece una introducción a la sintaxis básica de la utilidad del símbolo del sistema **dta** , muestra cómo obtener acceso a la Ayuda y practicar la optimización de cargas de trabajo sencillas.</span><span class="sxs-lookup"><span data-stu-id="0336f-114">This lesson provides an introduction to the basic **dta** command-prompt utility syntax, how to access help, and practice for tuning simple workloads.</span></span>  
  
 <span data-ttu-id="0336f-115">Incluye el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="0336f-115">It contains the following topic:</span></span>  
  
-   <span data-ttu-id="0336f-116">Iniciar la utilidad del símbolo del sistema **DTA** y optimizar una carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="0336f-116">Starting the **dta** Command Prompt Utility and Tuning a Workload</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0336f-117">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="0336f-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0336f-118">Iniciar la utilidad del símbolo del sistema dta y optimizar una carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="0336f-118">Starting the dta Command Prompt Utility and Tuning a Workload</span></span>](lesson-1-1-tuning-a-workload.md)  
  
  
