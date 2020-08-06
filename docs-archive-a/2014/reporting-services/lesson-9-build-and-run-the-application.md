---
title: 'Lección 9: Compilar y ejecutar la aplicación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f52d3f3a-0b09-4b34-9112-0b3655271587
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 068deb075f0f60dde634ac29f6f8f934448dc6a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669500"
---
# <a name="lesson-9-build-and-run-the-application"></a><span data-ttu-id="dc2d5-102">Lesson 9: Build and Run the Application</span><span class="sxs-lookup"><span data-stu-id="dc2d5-102">Lesson 9: Build and Run the Application</span></span>
  <span data-ttu-id="dc2d5-103">Después de crear un filtro para los datos de la tabla de datos, el paso siguiente consiste en generar y ejecutar la aplicación del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-103">After you create a data filter for the data table, your next step is to build and run the website application.</span></span>

### <a name="to-build-and-run-the-application"></a><span data-ttu-id="dc2d5-104">Para generar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="dc2d5-104">To build and run the application</span></span>

1.  <span data-ttu-id="dc2d5-105">Pulse **CTRL+F5** para ejecutar la página Default.aspx sin depurar o pulse F5 para ejecutar la página con la depuración.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-105">Press **CTRL+F5** to run the Default.aspx page without debugging, or press F5 to run the page with debugging.</span></span>

     <span data-ttu-id="dc2d5-106">Como parte del proceso de compilación, se compila el informe y los errores detectados (por ejemplo, un error de sintaxis en una expresión usada en el informe) se agregan a la **Lista de tareas** que se encuentra en la parte inferior de la ventana de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-106">As part of the build process, the report is compiled and any errors found (such as a syntax error in an expression used in the report) are added to the **Task List** that is located at the bottom of the Visual Studio window.</span></span>

     <span data-ttu-id="dc2d5-107">La página Web aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-107">The webpage appears in the browser.</span></span> <span data-ttu-id="dc2d5-108">El control ReportViewer muestra el informe.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-108">The ReportViewer control displays the report.</span></span> <span data-ttu-id="dc2d5-109">Puede utilizar la barra de herramientas para navegar por el informe, ampliarlo y exportarlo a Excel.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-109">You can use the toolbar to browse through the report, zoom, and export the report to Excel.</span></span>

2.  <span data-ttu-id="dc2d5-110">Mantenga el mouse sobre alguna de las filas bajo la columna **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="dc2d5-110">Hover the mouse over any of the rows under **Name** column.</span></span> <span data-ttu-id="dc2d5-111">El cursor del mouse mostrará un símbolo de mano.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-111">The mouse cursor will display a Hand symbol.</span></span>

3.  <span data-ttu-id="dc2d5-112">Haga clic en un valor de la columna **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="dc2d5-112">Click a value in the **Name** column.</span></span> <span data-ttu-id="dc2d5-113">El informe secundario se muestra con los datos filtrados correspondientes.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-113">The child report is shown with the corresponding filtered data.</span></span>

4.  <span data-ttu-id="dc2d5-114">Haga clic en el icono, **Volver al informe primario**, en la barra de herramientas de **ReportViewer** para navegar de nuevo al informe **Primario** .</span><span class="sxs-lookup"><span data-stu-id="dc2d5-114">Click the icon, **Go back to parent report**, in the **ReportViewer** tool bar to navigate back to the **Parent** report.</span></span>

     <span data-ttu-id="dc2d5-115">![obtención de detalles de SSRS mediante ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "obtención de detalles de SSRS mediante ReportViewer")</span><span class="sxs-lookup"><span data-stu-id="dc2d5-115">![ssrs drill through using ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "ssrs drill through using ReportViewer")</span></span>

5.  <span data-ttu-id="dc2d5-116">Cierre el explorador para salir.</span><span class="sxs-lookup"><span data-stu-id="dc2d5-116">Close the browser to exit.</span></span>


