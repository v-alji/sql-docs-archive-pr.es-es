---
title: Establecer las opciones de herramienta y el diseño | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 43e97ce0-97bc-4a27-9485-5bbeb7190b85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 96d853a85b8ee4d451c55d7ea59af3755887be22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747351"
---
# <a name="setting-tool-options-and-layout"></a><span data-ttu-id="08184-102">Configurar las opciones de herramienta y el diseño</span><span class="sxs-lookup"><span data-stu-id="08184-102">Setting Tool Options and Layout</span></span>
  <span data-ttu-id="08184-103">Puede definir opciones que permiten configurar lo que mostrará la interfaz gráfica de usuario (GUI) del Asistente para la optimización de motor de base de datos al iniciarse, las fuentes utilizadas y otras funciones para facilitar el uso.</span><span class="sxs-lookup"><span data-stu-id="08184-103">You can set options that configure what the Database Engine Tuning Advisor graphical user interface (GUI) displays on startup, the font it uses, and other tool functionality to best support how you use it.</span></span> <span data-ttu-id="08184-104">Las prácticas de esta página le permitirán familiarizarse con las opciones que puede configurar y el modo de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="08184-104">The practices on this page familiarize you with the options you can set, and how to set them.</span></span>  
  
### <a name="set-the-tool-options"></a><span data-ttu-id="08184-105">Configurar las opciones de herramienta</span><span class="sxs-lookup"><span data-stu-id="08184-105">Set the tool options</span></span>  
  
1.  <span data-ttu-id="08184-106">Inicie el Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="08184-106">Start the Database Engine Tuning Advisor.</span></span> <span data-ttu-id="08184-107">En el menú **Inicio** de Windows, elija **Todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]y **Herramientas de rendimiento**, y haga clic en **Asistente para la optimización de motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="08184-107">On the Windows **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and click **Database Engine Tuning Advisor**.</span></span>  
  
2.  <span data-ttu-id="08184-108">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="08184-108">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="08184-109">En el cuadro de diálogo **Opciones** , observe las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="08184-109">In the **Options** dialog box, view the following options:</span></span>  
  
    -   <span data-ttu-id="08184-110">Expanda la lista **Al iniciar** para ver lo que muestra el Asistente para la optimización de motor de base de datos cuando se inicia.</span><span class="sxs-lookup"><span data-stu-id="08184-110">Expand the **On startup** list to view what Database Engine Tuning Advisor can display when it is started.</span></span> <span data-ttu-id="08184-111">De forma predeterminada, está seleccionada la opción **Mostrar una nueva sesión** .</span><span class="sxs-lookup"><span data-stu-id="08184-111">By default, **Show a new session** is selected.</span></span>  
  
    -   <span data-ttu-id="08184-112">Haga clic en **cambiar fuente** para ver las fuentes que puede elegir para las listas de bases de datos y tablas en la pestaña **General** . Las fuentes que elija para esta opción también se usan en Asistente para la optimización de motor de base de datos cuadrículas de recomendaciones e informes después de haber realizado la optimización.</span><span class="sxs-lookup"><span data-stu-id="08184-112">Click **Change Font** to see what fonts you can choose for the lists of databases and tables on the **General** tab. The fonts you choose for this option also are used in Database Engine Tuning Advisor recommendation grids and reports after you have performed tuning.</span></span> <span data-ttu-id="08184-113">De forma predeterminada, el asistente utiliza las fuentes del sistema.</span><span class="sxs-lookup"><span data-stu-id="08184-113">By default, Database Engine Tuning Advisor uses system fonts.</span></span>  
  
    -   <span data-ttu-id="08184-114">La opción **Número de elementos en las listas usadas más recientemente** puede establecerse entre **1** y **10**.</span><span class="sxs-lookup"><span data-stu-id="08184-114">The **Number of items in most recently used lists** can be set between **1** and **10**.</span></span> <span data-ttu-id="08184-115">De esta manera, se establece el número máximo de elementos en las listas que se muestran cuando hace clic en **Sesiones recientes** o **Archivos recientes** del menú **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="08184-115">This sets the maximum number of items in the lists displayed by clicking **Recent Sessions** or **Recent Files** on the **File** menu.</span></span> <span data-ttu-id="08184-116">De forma predeterminada, el valor de esta opción es **4**.</span><span class="sxs-lookup"><span data-stu-id="08184-116">By default, this option is set to **4**.</span></span>  
  
    -   <span data-ttu-id="08184-117">Cuando la opción **Recordar mis últimas opciones de optimización** está activada, el Asistente para la optimización de motor de base de datos utiliza de forma predeterminada las opciones de optimización que especificó en la última sesión de optimización y las aplica a la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="08184-117">When **Remember my last tuning options** is checked, by default Database Engine Tuning Advisor uses the tuning options you specified for your last tuning session for the next tuning session.</span></span> <span data-ttu-id="08184-118">Desactive esta casilla para utilizar las opciones de optimización predeterminadas del asistente.</span><span class="sxs-lookup"><span data-stu-id="08184-118">Clear this check box to use Database Engine Tuning Advisor tuning option defaults.</span></span> <span data-ttu-id="08184-119">Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="08184-119">By default, this option is selected.</span></span>  
  
    -   <span data-ttu-id="08184-120">La opción **Preguntar antes de eliminar permanentemente las sesiones** está activada de forma predeterminada para impedir la eliminación accidental de sesiones de optimización.</span><span class="sxs-lookup"><span data-stu-id="08184-120">By default, **Ask before permanently deleting sessions** is checked to avoid accidentally deleting tuning sessions.</span></span>  
  
    -   <span data-ttu-id="08184-121">La opción **Preguntar antes de detener análisis de sesión** está activada de forma predeterminada para impedir la detención accidental de la sesión de optimización antes de que el Asistente para la optimización de motor de base de datos haya terminado de analizar la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="08184-121">By default, **Ask before stopping session analysis** is checked to avoid accidentally stopping a tuning session before Database Engine Tuning Advisor has finished analyzing a workload.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="08184-122">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="08184-122">Next Lesson</span></span>  
 [<span data-ttu-id="08184-123">Lección 2: Usar el Asistente para la optimización de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="08184-123">Lesson 2: Using Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
