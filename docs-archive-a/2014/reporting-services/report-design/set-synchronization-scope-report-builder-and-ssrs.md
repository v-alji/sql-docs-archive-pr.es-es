---
title: Establecer el ámbito de sincronización (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6f4a11e6-6151-47be-a43f-e3dbf6c0e737
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3efbb7774d5116c9b3a18457291434f2a05aac7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662550"
---
# <a name="set-synchronization-scope-report-builder-and-ssrs"></a><span data-ttu-id="e6d46-102">Establecer el ámbito de sincronización (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="e6d46-102">Set Synchronization Scope (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e6d46-103">Los indicadores transmiten los valores de datos sincronizando el intervalo de los valores de datos del indicador que están en un ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="e6d46-103">Indicators convey data values by synchronizing across the range of indicator values within a specified scope.</span></span> <span data-ttu-id="e6d46-104">De forma predeterminada, el ámbito es el contenedor primario del indicador, por ejemplo la tabla o matriz que contiene el indicador.</span><span class="sxs-lookup"><span data-stu-id="e6d46-104">By default, the scope is the parent container of the indicator such as the table or matrix that contains the indicator.</span></span> <span data-ttu-id="e6d46-105">Puede cambiar la sincronización del indicador en función del diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="e6d46-105">You can change the synchronization of the indicator depending on the layout of your report.</span></span> <span data-ttu-id="e6d46-106">Por ejemplo, si una región de datos como una tabla tiene un grupo de filas, puede especificar el grupo como el ámbito del indicador.</span><span class="sxs-lookup"><span data-stu-id="e6d46-106">For example, if a data region such as a table has a row group, you can specify the group as the indicator scope.</span></span> <span data-ttu-id="e6d46-107">El indicador también puede omitir la sincronización.</span><span class="sxs-lookup"><span data-stu-id="e6d46-107">The indicator can also omit synchronization.</span></span>  
  
 <span data-ttu-id="e6d46-108">Opciones como las unidades de medida se pueden establecer mediante expresiones.</span><span class="sxs-lookup"><span data-stu-id="e6d46-108">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="e6d46-109">Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e6d46-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e6d46-110">Para obtener información general sobre la descripción y el ámbito de configuración de informes, vea [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="e6d46-110">For general information about understanding and setting scope within reports, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-synchronization-scope-of-an-indicator"></a><span data-ttu-id="e6d46-111">Para cambiar el ámbito de sincronización de un indicador</span><span class="sxs-lookup"><span data-stu-id="e6d46-111">To change the synchronization scope of an indicator</span></span>  
  
1.  <span data-ttu-id="e6d46-112">Haga clic con el botón secundario en el indicador que desea cambiar y seleccione **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="e6d46-112">Right click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="e6d46-113">Haga clic en **Valores y estados** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="e6d46-113">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="e6d46-114">En la lista **Ámbito de sincronización** , haga clic en el ámbito que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="e6d46-114">In the **Synchronization scope** list, click the scope that you want to apply.</span></span>  
  
     <span data-ttu-id="e6d46-115">La opción **(Ninguno)** , que quita el ámbito de sincronización del indicador, siempre está disponible.</span><span class="sxs-lookup"><span data-stu-id="e6d46-115">The **(None)** option, which removes synchronization scope from the indicator, is always available.</span></span> <span data-ttu-id="e6d46-116">Las demás opciones dependen del diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="e6d46-116">Other options depend on the layout of your report.</span></span>  
  
     <span data-ttu-id="e6d46-117">Si quiere, puede hacer clic en el botón **Expresión** (*fx*) para modificar una expresión que establezca el ámbito.</span><span class="sxs-lookup"><span data-stu-id="e6d46-117">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the scope.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6d46-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6d46-118">See Also</span></span>  
 [<span data-ttu-id="e6d46-119">Indicadores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6d46-119">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
