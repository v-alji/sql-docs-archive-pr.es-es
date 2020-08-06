---
title: Reemplazar los parámetros de plantilla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.templates.replaceparameters.f1
helpviewer_keywords:
- template parameters [Template Explorer]
- templates [Transact-SQL], replacing parameters
- Replace (Query) Template Parameters dialog box
- replacing template parameters
ms.assetid: 1234aa14-3464-4a3e-922a-5cfb8fb23627
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d87b17a110efe118f7796487448e4d3bae30375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674510"
---
# <a name="replace-template-parameters"></a><span data-ttu-id="018d9-102">Reemplazar parámetros de plantilla</span><span class="sxs-lookup"><span data-stu-id="018d9-102">Replace Template Parameters</span></span>
  <span data-ttu-id="018d9-103">Las plantillas contienen parámetros que se pueden reemplazar por valores específicos de la implementación cada vez que se use la plantilla.</span><span class="sxs-lookup"><span data-stu-id="018d9-103">Templates contain parameters that can be replaced by implementation-specific values each time the template is used.</span></span> <span data-ttu-id="018d9-104">Después de abrir una plantilla en un editor de código, puede reemplazar los parámetros por valores relevantes para su implementación.</span><span class="sxs-lookup"><span data-stu-id="018d9-104">After opening a template in a code editor, you can replace the parameters with values relevant to your implementation.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="018d9-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="018d9-105">Before You Begin</span></span>  
 <span data-ttu-id="018d9-106">El cuadro de diálogo **Especificar valores para parámetros de plantilla** es una cuadrícula de tres columnas.</span><span class="sxs-lookup"><span data-stu-id="018d9-106">The **Specify Values for Template Parameters** dialog is a grid with three columns.</span></span> <span data-ttu-id="018d9-107">Las columnas **Parámetro** y **Tipo** son de solo lectura y no se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="018d9-107">The **Parameter** and **Type** columns are read-only and cannot be changed.</span></span> <span data-ttu-id="018d9-108">Revise el contenido de la columna **Valor** y cambie cualquiera de los valores predeterminados por los valores adecuados para su implementación.</span><span class="sxs-lookup"><span data-stu-id="018d9-108">Review the contents of the **Value** column, and change any of the defaults to values appropriate for your implementation.</span></span>  
  
 <span data-ttu-id="018d9-109">Para usar este cuadro de diálogo, los parámetros del script deben aparecer entre corchetes angulares (`< >`) in con el formato `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span><span class="sxs-lookup"><span data-stu-id="018d9-109">To use this dialog box, you must have parameters in your script enclosed in angle brackets (`< >`) in the format `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span></span>  
  
## <a name="replace-template-parameters"></a><span data-ttu-id="018d9-110">Reemplazar parámetros de plantilla</span><span class="sxs-lookup"><span data-stu-id="018d9-110">Replace Template Parameters</span></span>  
 <span data-ttu-id="018d9-111">Después de abrir la plantilla en una ventana del editor de código:</span><span class="sxs-lookup"><span data-stu-id="018d9-111">After opening the template in a code editor window:</span></span>  
  
1.  <span data-ttu-id="018d9-112">En el menú **Consulta** , haga clic en **Especificar valores para parámetros de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="018d9-112">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
2.  <span data-ttu-id="018d9-113">En el cuadro de diálogo **Especificar valores para parámetros de plantilla** , la columna **Valores** contiene un valor sugerido para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="018d9-113">In the **Specify Values for Template Parameters** dialog box, the **Values** column contains a suggested value for each parameter.</span></span> <span data-ttu-id="018d9-114">Acepte el valor o reemplácelo por otro nuevo.</span><span class="sxs-lookup"><span data-stu-id="018d9-114">Accept the value or replace it with a new value.</span></span>  
  
3.  <span data-ttu-id="018d9-115">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Reemplazar parámetros de plantilla** y modificar el script en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="018d9-115">Click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the query editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018d9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="018d9-116">See Also</span></span>  
 <span data-ttu-id="018d9-117">[Explorador de plantillas](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="018d9-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="018d9-118">Abrir una plantilla</span><span class="sxs-lookup"><span data-stu-id="018d9-118">Open a Template</span></span>](open-a-template.md)  
  
  
