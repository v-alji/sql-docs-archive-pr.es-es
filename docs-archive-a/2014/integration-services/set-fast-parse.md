---
title: Establecer análisis rápido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dcd1dc09-6eaf-440b-9ce6-fef779ff794f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6ff2c6ecd536dd5ecc34dceb358ffcf578ff3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662161"
---
# <a name="set-fast-parse"></a><span data-ttu-id="bdab1-102">Configurar el análisis rápido</span><span class="sxs-lookup"><span data-stu-id="bdab1-102">Set Fast Parse</span></span>
  <span data-ttu-id="bdab1-103">La propiedad de análisis rápido debe configurarse para cada columna del origen o la transformación que utilice el análisis rápido.</span><span class="sxs-lookup"><span data-stu-id="bdab1-103">The fast parse property must be set for each column of the source or transformation that uses fast parse.</span></span> <span data-ttu-id="bdab1-104">Para configurar la propiedad, utilice el Editor avanzado del origen de archivo plano y la transformación Conversión de datos.</span><span class="sxs-lookup"><span data-stu-id="bdab1-104">To set the property, use the Advanced editor of the Flat File source and Data Conversion transformation.</span></span>  
  
### <a name="to-set-fast-parse"></a><span data-ttu-id="bdab1-105">Para configurar el análisis rápido</span><span class="sxs-lookup"><span data-stu-id="bdab1-105">To set fast parse</span></span>  
  
1.  <span data-ttu-id="bdab1-106">Haga clic con el botón derecho en el origen de archivo plano o en la transformación Conversión de datos y, después, haga clic en **Mostrar editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="bdab1-106">Right-click the Flat File source or Data Conversion transformation, and then click **Show Advanced Editor**.</span></span>  
  
2.  <span data-ttu-id="bdab1-107">En el cuadro de diálogo **Editor avanzado** haga clic en la pestaña **Propiedades de entrada y salida** .</span><span class="sxs-lookup"><span data-stu-id="bdab1-107">In the **Advanced Editor** dialog box, click the **Input and Output Properties** tab.</span></span>  
  
3.  <span data-ttu-id="bdab1-108">En el panel **Entradas y salidas** , haga clic en la columna para la cual desee habilitar el análisis rápido.</span><span class="sxs-lookup"><span data-stu-id="bdab1-108">In the **Inputs and Outputs** pane, click the column for which you want to enable fast parse.</span></span>  
  
4.  <span data-ttu-id="bdab1-109">En el ventana Propiedades, expanda el nodo **propiedades personalizadas** y, a continuación, establezca la `FastParse` propiedad en `True` .</span><span class="sxs-lookup"><span data-stu-id="bdab1-109">In the Properties window, expand the **Custom Properties** node, and then set the `FastParse` property to `True`.</span></span>  
  
5.  <span data-ttu-id="bdab1-110">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdab1-110">Click **OK**.</span></span>  
  
  
