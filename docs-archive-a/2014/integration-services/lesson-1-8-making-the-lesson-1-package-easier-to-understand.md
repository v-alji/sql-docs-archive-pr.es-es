---
title: 'Paso 8: Facilitar la comprensión del paquete de la lección 1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e3751e53-77c7-47d0-8fe8-73ed1a53413a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fb8e2adb9062b5b777acc14df0ddc5b45884ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673119"
---
# <a name="step-8-making-the-lesson-1-package-easier-to-understand"></a><span data-ttu-id="8ab91-102">Paso 8: Facilitar la comprensión del paquete de la lección 1</span><span class="sxs-lookup"><span data-stu-id="8ab91-102">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>
  <span data-ttu-id="8ab91-103">Ahora que ha terminado la configuración del paquete de la lección 1, es una buena idea ordenar el diseño del paquete.</span><span class="sxs-lookup"><span data-stu-id="8ab91-103">Now that you have completed the configuration of the Lesson 1 package, it is a good idea to tidy up the package layout.</span></span> <span data-ttu-id="8ab91-104">Si las formas de los diseños de los flujos de datos y de control tienen tamaños aleatorios o no están alineadas o agrupadas, la funcionalidad del paquete puede resultar más difícil de comprender.</span><span class="sxs-lookup"><span data-stu-id="8ab91-104">If the shapes in the control and data flow layouts are random sizes, or if the shapes are not aligned or grouped, the functionality of package can be more difficult to understand.</span></span>  
  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="8ab91-105">Data Tools proporciona herramientas que permiten aplicar formato al diseño del paquete de forma rápida y sencilla.</span><span class="sxs-lookup"><span data-stu-id="8ab91-105">Data Tools provides tools that make it easy and quick to format the package layout.</span></span> <span data-ttu-id="8ab91-106">Las características de formato incluyen la capacidad de hacer que las formas tengan el mismo tamaño, de alinearlas y de manipular el espaciado horizontal y vertical entre las formas.</span><span class="sxs-lookup"><span data-stu-id="8ab91-106">The formatting features include the ability to make shapes the same size, align shapes, and manipulate the horizontal and vertical spacing between shapes.</span></span>  
  
 <span data-ttu-id="8ab91-107">Otra forma de mejorar la comprensión de la funcionalidad de un paquete es agregar anotaciones que la describan.</span><span class="sxs-lookup"><span data-stu-id="8ab91-107">Another way to improve the understanding of package functionality is to add annotations that describe package functionality.</span></span>  
  
 <span data-ttu-id="8ab91-108">En esta tarea usará las características de formato de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools para mejorar el diseño del flujo de datos y agregará una anotación al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="8ab91-108">In this task, you will use the formatting features in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools to improve the layout of the data flow and also add an annotation to the data flow.</span></span>  
  
### <a name="to-format-the-layout-of-the-data-flow"></a><span data-ttu-id="8ab91-109">Para aplicar formato al diseño del flujo de datos</span><span class="sxs-lookup"><span data-stu-id="8ab91-109">To format the layout of the data flow</span></span>  
  
1.  <span data-ttu-id="8ab91-110">Si el paquete de la lección 1 no está abierto todavía, haga doble clic en Lesson 1.dtsx en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="8ab91-110">If the Lesson 1 package is not already open, double-click Lesson 1.dtsx in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="8ab91-111">Haga clic en la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="8ab91-111">Click the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="8ab91-112">Coloque el cursor en la parte superior derecha de la transformación Extract Sample Currency, haga clic y, a continuación, arrastre el cursor por todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="8ab91-112">Place the cursor to the top and to the right of the Extract Sample Currency transformation, click, and then drag the cursor across all the data flow components.</span></span>  
  
4.  <span data-ttu-id="8ab91-113">En el menú **Formato** , seleccione **Igualar tamaño**y, a continuación, haga clic en **Ambos**.</span><span class="sxs-lookup"><span data-stu-id="8ab91-113">On the **Format** menu, point to **Make Same Size**, and then click **Both**.</span></span>  
  
5.  <span data-ttu-id="8ab91-114">Con los objetos del flujo de datos seleccionados, en el menú **Formato** , seleccione **Alinear**y haga clic en **Lados izquierdos**.</span><span class="sxs-lookup"><span data-stu-id="8ab91-114">With the data flow objects selected, on the **Format** menu, point to **Align**, and then click **Lefts**.</span></span>  
  
### <a name="to-add-an-annotation-to-the-data-flow"></a><span data-ttu-id="8ab91-115">Para agregar una anotación al flujo de datos</span><span class="sxs-lookup"><span data-stu-id="8ab91-115">To add an annotation to the data flow</span></span>  
  
1.  <span data-ttu-id="8ab91-116">Haga clic con el botón derecho en cualquier parte de la superficie de diseño del flujo de datos y haga clic en **Agregar anotación**.</span><span class="sxs-lookup"><span data-stu-id="8ab91-116">Right-click anywhere in the background of the data flow design surface and then click **Add Annotation**.</span></span>  
  
2.  <span data-ttu-id="8ab91-117">Escriba o pegue el texto siguiente en el cuadro de anotación.</span><span class="sxs-lookup"><span data-stu-id="8ab91-117">Type or paste the following text in the annotation box.</span></span>  
  
     <span data-ttu-id="8ab91-118">**El flujo de datos extrae datos de un archivo, busca valores en la columna CurrencyKey de la tabla DimCurrency y la columna DateKey de la tabla DimDate, y escribe los datos en la tabla NewFactCurrencyRate.**</span><span class="sxs-lookup"><span data-stu-id="8ab91-118">**The data flow extracts data from a file, looks up values in the CurrencyKey column in the DimCurrency table and the DateKey column in the DimDate table, and writes the data to the NewFactCurrencyRate table.**</span></span>  
  
     <span data-ttu-id="8ab91-119">Para ajustar el texto en el cuadro de anotación, coloque el cursor donde desee empezar una nueva línea y presione la tecla Intro.</span><span class="sxs-lookup"><span data-stu-id="8ab91-119">To wrap the text in the annotation box, place the cursor where you want to start a new line and press the Enter key.</span></span>  
  
     <span data-ttu-id="8ab91-120">Si no agrega texto al cuadro de anotación, desaparecerá al hacer clic fuera del cuadro.</span><span class="sxs-lookup"><span data-stu-id="8ab91-120">If you do not add text to the annotation box, it disappears when you click outside the box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8ab91-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8ab91-121">Next Steps</span></span>  
 [<span data-ttu-id="8ab91-122">Paso 9: Prueba del paquete del tutorial de la lección 1</span><span class="sxs-lookup"><span data-stu-id="8ab91-122">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](../integration-services/lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
  
